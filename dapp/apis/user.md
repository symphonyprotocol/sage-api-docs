# User APIS

### 0x0. Changes
* init version - v0.01 at 2018-5-10

### 0x1. Overview

### 0x2. user/tasks
tasks that user already done
* **Http Method:** GET
* **NeedMachineTicket:** NO
* **NeedUserTicket:** YES
#### Request Params
NO
#### Return Result
```` javascript
"result": {
    "tasks":[
        [TaskListClass],
    ]
}
````
|Field|Type|Desc|
|----|----|----|
|TaskListClass| class| referer to [tasklist](./task.md)

### 0x3. user/profiles
* **Http Method:** GET/POST/PUT/DELETE
* **NeedMachineTicket:** NO
* **NeedUserTicket:** YES
#### Request Params
````javascript
"result": {
    "profiles":[
        {
            "id":"19s99123123",
            "name": "soft drink",
            "categroy": {
                "id": "9s9s9sd9",
                "name": "drink",
            }
        },
    ]
}
````
#### Return Result
````javascript
"result": {
    "profiles":[
        {
            "id":"19s99123123",
            "name": "soft drink",
            "categroy": {
                "id": "9s9s9sd9",
                "name": "drink",
            }
        },
    ]
}
````
|Field|Type|Desc|
|---|---|---|
|category|Categroy|profile category|

### 0x4. user/info
* **Http Method:** GET/POST/PUT/DELETE
* **NeedMachineTicket:** NO
* **NeedUserTicket:** YES
#### Reqeust & Return JSON
````javascript
{
    "id": "19x99s9s9s",
    "username": "denie1717",
    "displayname": "Denie",
    "gender": "male",
    "birth": "1990-02",
    "avatar": "./bigAvatar.png",
    "mobile": "0124487383",
    "email": "denie@gmail.com"
    "addresses": [ 
        {
            "country": "China",
            "province": "Shanghai",
            "city": "Shanghai",
            "district": "XuHui",
            "detail": "Room 505, #7787 ZhongShan Road"
        }
    ]
}
````

[UserInfo Class]

|Field|Type|Desc|
|----|----|----|
|id|string| user id|
|username| string||
|displayname| string| screen name|
|gender|string||
|birth|string|date|
|avatar|string| avatar url|
|mobile|string||
|email|string||
|address| Address||

[Address Class]

|Field|Type|Desc|
|--|--|---|
|country|string| country|
|province|string||
|city|string||
|district|string||
|detail|string|detail address|
