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
The after valided user and password, the backend conect with amazon cognite to get token Get Credentials For 
our Identity.

To access other API methods, is necessary the token of amazon cognite.

See on [Amazon doc](http://docs.aws.amazon.com/cognito/devguide/identity/concepts/authentication-flow/), item **Developer Authenticated Identities Authflow**.

<aside class="warning">For more infomation about error type and html code, go to these sections.
</aside>
## Check Update
`eflog-api.aeronauticalsolutions.aero/v1/ios/checkUpdate`

Return if exist a new version of the database, that this device have installed.

HTTP Method	 |  Requiered  Authentication 
--------- | -----------
POST | YES
> ### Data Parameters

```json
  {
    "id": "CREW_PIC_ID",
    "date": "DATE-DATEBASE-INSTALLED"
  }
```
>### Succes Response

```json
{
  "meta": [
    {
      "code": "HTML 1.1 CODE"
      "errorType": ""
    }
  ]
  "response"{
	"need":"boolean"  
  }
}
```
## Update

> ### Data Parameters

```json
  {
    "id": "CREW_PIC_ID",
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
	"Por":"definir"  
  }
}
```
`eflog-api.aeronauticalsolutions.aero/v1/ios/update`

Return a Json-object that contains new data to storage on local database.

HTTP Method	 |  Requiered  Authentication 
--------- | -----------
GET | YES

## Update
> ### Data Parameters

```json
  {
    "id": "CREW_PIC_ID",
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
	"Por":"definir"  
  }
}
```
`eflog-api.aeronauticalsolutions.aero/v1/ios/update`

Return a Json-object that contains new data to storage on local database.

HTTP Method	 |  Requiered  Authentication 
--------- | -----------
GET | YES
## Sen report
> ### Data Parameters

```json
  {
    "Values For report": "",
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
	"status":"ok"  
  }
}
```
`eflog-api.aeronauticalsolutions.aero/v1/ios/sendReport`

Put into the database a new report. 

HTTP Method	 |  Requiered  Authentication 
--------- | -----------
PUT | YES
# Report API 
# Administrator API



