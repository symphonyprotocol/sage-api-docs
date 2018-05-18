# Task APIs

### 0x0. Changes
* init version - v0.01 at 2018-5-10

### 0x1. Overview
Tasks are user based action to earn SAGE coin from doing activities such as AD video watching, questionnaire filling, location marking etc. Tasks are published by merchants who want to do brand development with target customers or precision marketing.
Currently in our sysetm, we support 2 kind of tasks, video and questionnaire. End users can earn SAGE coin from it.

### 0x2. task/{task_id}
* **Http Method:** GET/POST/PUT/DELETE
* **NeedMachineTicket:** NO
* **NeedUserTicket:** YES
#### Task JSON
````javascript
{
    "id": "18xks9131232xs",
    "name": "LOL Vedio",
    "description": "LOL game hunting",
    "start_date": "2018-01-23",
    "end_date": "2018-03-04",
    "display_images":[
        {
            "url": "/lol01.png",
        },
    ],
    "merchant": {
        "id": "18x8s8sd8f39",
        "name": "GamePlay LTD",
        "logo": "/gameplay.png",
    },
    "profile": [Profile Class],
    "task_config": {
        "total_sage": 100000,
        "per_sage": 20,
    },
    "status": {
        "task_click": 100,
        "task_done": 81
    },
    "type": "video",
    "video": {
        "url": "/lol.mpeg",
        "content": "<div>this is the main content shows in </div>",
    },
    "questionnaire": {
        "questions":[
            {
                "question": "your age?",
                "answer_type": "choice",
                "answers": [
                    {
                        "display_value": "10-16",
                        "value": "youngth"
                    }
                ]
            }
        ]
    }
}
````
#### Task Class
|Field|Type|Desc|
|----|----|----|
|id| string| task id|
|name| string| task name|
|description| string| task description, can be HTML format|
|start_date|string|task start date|
|end_date|string|task end date|
|display_images| list | images list|
|merchant| Merchant| publish merchant|
|profile|Profile class|referer to [profile class](./profile.md)|
|task_config| TaskConfig| task configuration|
|status| Status| task status|
|type| string| "video" for video type, "questionnaire" for questionnaire type|
|video|Video|optional|
|questionnaire|Questionnaire|optional|

#### Merchant Class
|Field|Type|Desc|
|----|----|----|
|id| string| merchant id|
|name| string| merchant name|
|logo| string| merchant log url|

#### TaskConfig Class
|Field|Type|Desc|
|----|----|----|
|total_sage|int64|total sage asgin to task|
|per_sage|int64|every task finish can get reward amount|

#### Status Class
|Field|Type|Desc|
|----|----|----|
|task_click|int|user click task amount|
|task_done|int|total task finish amount|

#### Video Class
|Field|Type|Desc|
|----|----|----|
|url|string|video url|
|content|string| videon content, can be HTML format|

#### Questionnaire Class
|Field|Type|Desc|
|----|----|----|
|question|string| question content, can be HTML format|
|answer_type|string| "choice","text"|
|answers| Answer list||

#### Answer Class
|Field|Type|Desc|
|----|----|----|
|display_value|string|display content, can be HTML format|
|value|string|real backend value|

### 0x3. tasks/{user_id}/{task_id}
Get task list for specific user
* **Http Method:** GET
* **NeedMachineTicket:** NO
* **NeedUserTicket:** YES

#### Request Params
|Field|Type|Desc|
|----|----|----|
|user_id|string| user id|
|task_id|string|latest task id user get, if not, set to "0"|

#### Return Result 
````javascript
"result": {
    "tasks":[
        {
            [Task Class],
            "status": {
                "action": "finish",
                "action_date": "2018-02-03"
            }
        },
    ]
}
````
|Field|Type|Desc|
|----|----|----|
|[Task class]|Task| task items in 0x1|
|action|string|"finish":already done, "no": no action|
|action_date|string|finish date|

