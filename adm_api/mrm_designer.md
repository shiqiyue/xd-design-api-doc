# 设计师

## 申请通过
```graphql
mutation test($req:DesignerRegisterSuccessfulReq!){
 designerRegisterSuccessful(req:$req)
}
```
```json
{
  "req": {
   "id": 2
  }
}
```
```json
{
  "data": {
    "designerRegisterSuccessful": true
  }
}
```

## 申请驳回
```graphql
mutation test($req:DesignerRegisterFailedReq!){
 designerRegisterFailed(req:$req)
}
```
```json
{
  "req": {
   "id": 2,
    "remark": "test"
  }
}
```
```json
{
  "data": {
    "designerRegisterFailed": true
  }
}
```

## 获取设计师申请记录

```graphql
query test($req:GetDesignerRegisterReq!){
    getDesignerRegister(req:$req){
        record{
            id
            memberId{
                id
                name
                createdAt
                updatedAt
            }
            status
            reviewTime
            reviewerId{
                id
                name
            }
            registerType
            createdAt
        }
        total
    }
}
```
```json
{
  "req": {
    "pageNum": 1,
    "pageSize": 10,
    "filter": {
      "designerRegisterStatus": "IN_REVIEW"
    },
    "reverse": false,
    "sortKey": "ID"
  }
}
```
```json
{
  "data": {
    "getDesignerRegister": {
      "record": [
        {
          "id": 2,
          "memberId": {
            "id": 2,
            "name": "测试",
            "createdAt": "2022-02-11T14:07:12.662121+08:00",
            "updatedAt": "2022-02-11T14:07:12.662121+08:00"
          },
          "status": "IN_REVIEW",
          "reviewTime": null,
          "reviewerId": null,
          "registerType": "PERSON",
          "createdAt": "2022-03-21T16:58:40.876478+08:00"
        },
        {
          "id": 3,
          "memberId": {
            "id": 2,
            "name": "测试",
            "createdAt": "2022-02-11T14:07:12.662121+08:00",
            "updatedAt": "2022-02-11T14:07:12.662121+08:00"
          },
          "status": "IN_REVIEW",
          "reviewTime": null,
          "reviewerId": null,
          "registerType": "COMPANY",
          "createdAt": "2022-03-21T17:03:15.876319+08:00"
        }
      ],
      "total": 2
    }
  }
}
```

## 获取设计师
```graphql
query test($req:GetDesignerReq!){
  getDesigner(req:$req){
    record{
      id
     	memberId{
        id
        name
      }
      publishLimit
      designLevel
      starCount
      templateLimit
      tagId{
        id
        name
      }
    }
    total
  }
}
```
```json
{
  "req": {
    "pageNum": 1,
    "pageSize": 10,
    "reverse": false,
    "sortKey": "ID"
  }
}
```
```json
{
  "data": {
    "getDesigner": {
      "record": [
        {
          "id": 1,
          "memberId": {
            "id": 2,
            "name": "测试"
          },
          "publishLimit": 20,
          "designLevel": 1,
          "starCount": 0,
          "templateLimit": 20,
          "tagId": [
            {
              "id": 22,
              "name": "dddddd2"
            },
            {
              "id": 24,
              "name": "梨子22"
            },
            {
              "id": 23,
              "name": "苹果12"
            },
            {
              "id": 26,
              "name": "香蕉s"
            },
            {
              "id": 21,
              "name": "gggggg2"
            },
            {
              "id": 20,
              "name": "ggg2"
            },
            {
              "id": 19,
              "name": "helloworld3"
            },
            {
              "id": 1,
              "name": "apple"
            },
            {
              "id": 2,
              "name": "小说"
            },
            {
              "id": 16,
              "name": "world222"
            },
            {
              "id": 18,
              "name": "world32"
            },
            {
              "id": 17,
              "name": "hello34"
            },
            {
              "id": 25,
              "name": "西瓜226"
            },
            {
              "id": 3,
              "name": "xixixi"
            },
            {
              "id": 13,
              "name": "覅积分234"
            },
            {
              "id": 12,
              "name": "佛教5"
            },
            {
              "id": 11,
              "name": "tfgwaetfg2"
            },
            {
              "id": 10,
              "name": "fga1"
            },
            {
              "id": 9,
              "name": "rfewf3"
            },
            {
              "id": 7,
              "name": "ABE5"
            },
            {
              "id": 6,
              "name": "abc6"
            },
            {
              "id": 8,
              "name": "ccc3"
            },
            {
              "id": 15,
              "name": "hello2"
            }
          ]
        }
      ],
      "total": 1
    }
  }
}
```