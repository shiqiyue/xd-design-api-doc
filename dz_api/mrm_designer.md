# 设计师

## 个人设计申请
```graphql
mutation test($req:PersonDesignerRegisterReq!){
  personDesignerRegister(req:$req)
}
```
```json
{
  "req": {
    "ideaId": [1,1,2,2,3,4,5,4,7,8]
  }
}
```
```json
{
  "data": {
    "personDesignerRegister": true
  }
}
```

## 设计团队申请
```graphql
mutation test($req:CompanyDesignerRegisterReq!){
  companyDesignerRegister(req:$req)
}
```
```json
{
  "req": {
    "ideaId": [1,1,2,2,3,4,5,4,7,8,1,1,2,2,3,4,5,4,7,8]
  }
}
```
```json
{
  "data": {
    "companyDesignerRegister": true
  }
}
```

## 获取申请记录
```graphql
query test($req:GetSelfDesignerRegisterReq!){
  getSelfDesignerRegister(req:$req){
    record{
      id
      memberId{
        id
        name
      }
      registerType
      createdAt
      status
      reviewTime
      
    }
    total
  }
}
```
```json
{
  "req": {
    "reverse": false,
    "sortKey": "ID"
  }
}
```
```json
{
  "data": {
    "getSelfDesignerRegister": {
      "record": [
        {
          "id": 2,
          "memberId": {
            "id": 2,
            "name": "测试"
          },
          "registerType": "PERSON",
          "createdAt": "2022-03-21T16:58:40.876478+08:00",
          "status": "IN_REVIEW",
          "reviewTime": null
        },
        {
          "id": 3,
          "memberId": {
            "id": 2,
            "name": "测试"
          },
          "registerType": "COMPANY",
          "createdAt": "2022-03-21T17:03:15.876319+08:00",
          "status": "IN_REVIEW",
          "reviewTime": null
        }
      ],
      "total": 2
    }
  }
}
```

## 获取设计师
```graphql
query test($req:GetDesignersReq!){
  getDesigners(req:$req){
    record{
      id
      memberId{
        id
        name
      }
      starCount
      designLevel
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
    "getDesigners": {
      "record": [
        {
          "id": 1,
          "memberId": {
            "id": 2,
            "name": "测试"
          },
          "starCount": 0,
          "designLevel": 1
        }
      ],
      "total": 1
    }
  }
}
```