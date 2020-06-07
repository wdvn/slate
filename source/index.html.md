---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Giới thiệu API 

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

``

<aside class="notice">
Authorization: <span>your token</span>
</aside>

# Products 

## Lấy toàn bộ danh sách san phẩm 


```python
import http.client

conn = http.client.HTTPConnection("localhost:3000")

payload = "{\"username\":\"xyz\",\"password\":\"xyz\"}"

headers = { 'content-type': "application/json" }

conn.request("POST", "/api/login", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> Dữ liệu trả về có dạng sau 

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Mô tả cho API 

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Type | Description
--------- | ------- | -----------
param1 | int | Mô tả thông tin cho tham số .
param2 | string | Mô tả thông tin cho tham số 

<aside class="success">
API có yêu cầu Authorization
</aside>
