# Account API

### 0x0. Changes

- init version -v0.01 as 2018-6-6

### 0x1. Classes

#### [Address Class]

```javascript
{
  	"ID":"ce61b3f5-0e69-4c6a-89a2-2767771aacc9",
    "receiveName":"xiaoming",
    "mobile":"18888888888",
    "cityID":"3783e213-7777-4518-9787-5e7fdc674eae",
    "street":"pudong",
    "zipCode":"201424",
    "isDefault":1,
    "isValid":1
}
```

#### [Trade Class]

```javascript
{
  	"tradeID"
}
```

#### [DissMerchant Class]

```javascript
{
  	"ID": "ce61b3f5-0e69-4c6a-89a2-2767771aacc9",
    "merchantID": "3783e213-7777-4518-9787-5e7fdc674eae",
    "isValid":1
}
```

#### [AccountProfile Class]

```javascript
{
    "ID":"cf0065be-fe23-4824-8c40-ff0e62de1c7f",
    "profileID": "3783e213-7777-4518-9787-5e7fdc674eae",
    "type":0,
    "isValid":1,
}
```

### 0x2. account/:action

Desc: action is "info", "address", "dissmerchant" or "profile"

Get all user account information.

- **Http Method:** GET
- **NeedMachineTicket:** NO
- **NeedUserTicket:** YES

#### Response JSON

```javascript
"result":{
	"mobile": "18314231423",
    "displayName": "xiaoming",
    "avatar": "avatar.jpg",
    "gender": "M",
    "addresses":[
      	{
  			[Address Class],
		}
    ],
    "birth": "1994-11-13",
    "balance": 100,
    "walletAddress": "1hvzSofGwT8cjb8JU7nBsCSfEVQX5u9CL",
    "trades":[
  		{
  			[Trade Class]
		}
	],
    "profiles": [
  			{
              	[AccountProfile Class],
            }
		],
	},
    "dissMerchants":[
		{
  			[DissMerchant Class]
		}  
	]    
}
```

| Field         | Type   | Desc                             |
| ------------- | ------ | -------------------------------- |
| mobile        | string | user mobile                      |
| displayname   | string | user nickname                    |
| avatar        | string | url;storage address              |
| gender        | string | M,F,O                            |
| birth         | string | user birthday;"yyyymmdd"         |
| loginpwd      | string | user login password              |
| paypwd        | string | user payment password            |
| balance       | int    | cryptocurrency balance           |
| walletaddress | string | wallet address                   |
| trades        | list   | transaction record               |
| profiles      | list   | list all profiles                |
| dissmerchant  | list   | the merchant list that user hate |

### 0x3. account

For user modify some information.

- **Http Method:** PUT
- **NeedMachineTicket:** NO
- **NeedUserTicket:** YES

#### Request JSON

```javascript
{	
	"displayName":"mes",
	"walletAddress":"asdasd",
	"action":"address",
	"addresses":[
			{
  				[Address Class]
			}
		]
}
```

### 0x4. account/upload_avatar

For user modify some information.

- **Http Method:** PUT
- **NeedMachineTicket:** NO
- **NeedUserTicket:** YES

```javascript
{
  	"avatar":"avatar.jpg",
}
```

### 0x5. account/ch_loginpwd

For user modify some information.

- **Http Method:** PUT
- **NeedMachineTicket:** NO
- **NeedUserTicket:** YES

```javascript
{
  	"login_pwd":"060077037e418c6909bd8730f769d04fe384e91958f89a03ae6540a639480597"
}
```

### 0x6. account/ch_paypwd

For user modify some information.

- **Http Method:** PUT
- **NeedMachineTicket:** NO
- **NeedUserTicket:** YES

```javascript
{
  	"pay_pwd":"060077037e418c6909bd8730f769d04fe384e91958f89a03ae6540a639480597"
}
```