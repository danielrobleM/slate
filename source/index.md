---
title: eFlog API

language_tabs:
  - JavaScript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - HTMLCODE 
  - errors
search: true
---

# Introduction to eFlog API. 

eFlog API is divided into **3** module : 

* IOS AP
* Report API
* Administrator API.

The basic **Endpoint** structure is

`eflog-api.aeronauticalsolutions.aero/VERSION_API/TYPE_API/`.

For example, this url is for a authentication method from the IOS API version 1.0

`eflog-api.aeronauticalsolutions.aero/v1/ios/login`
# iOS API
the iOS API provide access to user authentication,update local datebase and add new reports. 
## Authentication
> ### Data Parameters

```json
  {
    "username": "CREW_PIC_NAME",
    "password": "*********"
  }
```

>### Succes Response

```json
{
  "meta": [
    {
      "code": "HTML 1.1 CODE",
      "errorType": ""
    }
  ]
  "response"{
	"user_profile_Information":""  
  }
}
```
>### Error  Response

```json
{
  "meta": [
    {
      "code": "HTML 1.1 CODES",
      "errorType": ""
    }
  ]
  "response"{
  }
}
```

`eflog-api.aeronauticalsolutions.aero/v1/ios/login`

Returns profile information for a given user.

HTTP Method	 |  Requiered  Authentication 
--------- | -----------
POST | NO

### Understanding authentication through amazon Cognite

<aside class="warning">For more infomation about error type and html code, go to these sections.
</aside>
# Report API 
# Administrator API
# Authentication
eFlog  has **3** types of authentication, **IOS Authentication** , **Report Authentication** and **Administrator Authentication**. 


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

> Make sure to replace `meowmeowmeow` with your API key.



Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

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
    "name": "Isis",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Isis",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">If you're not using an administrator API key, note that some kittens will return 403 Forbidden if they are hidden for admins only.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

