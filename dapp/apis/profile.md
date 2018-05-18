# Profile APIS

### 0x0. Changes
* init version - v0.01 at 2018-5-10

### 0x1. Overview

### 0x2. profiles
list all profiles
* **Http Method:** GET
* **NeedMachineTicket:** NO
* **NeedUserTicket:** YES
#### Request Params
NO
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
