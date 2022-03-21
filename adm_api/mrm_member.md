# 会员信息

## 获取账号
```graphql
query test($req:AccountReq!){
  accountList(req:$req){
    record{
      id
      phone
      email
      status
      lastLogin
      createdAt
      updatedAt
      memberId{
        id
        name
        avatar
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
    "filter": {
      "memberId": 2
    },
    "reverse": false,
    "sortKey": "ID"
  }
}
```
```json
{
  "data": {
    "accountList": {
      "record": [
        {
          "id": 2,
          "phone": "123465464",
          "email": null,
          "status": 1,
          "lastLogin": "2022-02-11T14:07:12.662121+08:00",
          "createdAt": "2022-02-11T14:07:12.662121+08:00",
          "updatedAt": "2022-02-11T14:07:12.662121+08:00",
          "memberId": {
            "id": 2,
            "name": "测试",
            "avatar": null
          }
        }
      ],
      "total": 1
    }
  }
}
```

## 冻结账号
```graphql
mutation test($req:FreezeAccountReq!){
  freezeAccount(req:$req)
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
    "freezeAccount": true
  }
}
```

## 解除冻结
```graphql
mutation test($req:CancelFreezeAccountReq!){
  cancelFreezeAccount(req:$req)
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
    "cancelFreezeAccount": true
  }
}
```

## 禁止登录
```graphql
mutation test($req:ProhibitLoginAccountReq!){
  prohibitLoginAccount(req:$req)
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
    "prohibitLoginAccount": true
  }
}
```

## 解除禁止登录
```graphql
mutation test($req:CancelProhibitLoginAccountReq!){
  cancelProhibitLoginAccount(req:$req)
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
    "cancelProhibitLoginAccount": true
  }
}
```

## 获取会员
```graphql
query test($req:MemberReq!){
  memberList(req:$req){
    records{
      id
      name
      avatar
      introduction
      designerId{
        id
      }
      merchantId{
        id
      }
      personId{
        id
      }
      companyId{
        id
			}
      createdAt
      updatedAt
    }
    total
  }
}
```
```json
{
  "req":{
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
    "memberList": {
      "records": [
        {
          "id": 1,
          "name": "设计师",
          "avatar": null,
          "introduction": null,
          "designerId": null,
          "merchantId": null,
          "personId": {
            "id": 4
          },
          "companyId": {
            "id": 1
          },
          "createdAt": "2022-01-25T15:29:24.029353+08:00",
          "updatedAt": "2022-01-25T17:12:12.171505+08:00"
        },
        {
          "id": 2,
          "name": "测试",
          "avatar": null,
          "introduction": null,
          "designerId": {
            "id": 1
          },
          "merchantId": null,
          "personId": null,
          "companyId": null,
          "createdAt": "2022-02-11T14:07:12.662121+08:00",
          "updatedAt": "2022-02-11T14:07:12.662121+08:00"
        },
        {
          "id": 3,
          "name": "测试",
          "avatar": null,
          "introduction": null,
          "designerId": null,
          "merchantId": null,
          "personId": null,
          "companyId": null,
          "createdAt": "2022-02-12T10:00:29.131668+08:00",
          "updatedAt": "2022-02-12T10:00:29.131668+08:00"
        },
        {
          "id": 4,
          "name": "测试",
          "avatar": null,
          "introduction": null,
          "designerId": null,
          "merchantId": null,
          "personId": null,
          "companyId": null,
          "createdAt": "2022-02-12T10:02:24.106105+08:00",
          "updatedAt": "2022-02-12T10:02:24.106105+08:00"
        },
        {
          "id": 5,
          "name": "testUser",
          "avatar": null,
          "introduction": null,
          "designerId": null,
          "merchantId": null,
          "personId": null,
          "companyId": null,
          "createdAt": "2022-02-18T10:00:48.443751+08:00",
          "updatedAt": "2022-02-18T10:00:48.443751+08:00"
        }
      ],
      "total": 5
    }
  }
}
```

## 获取银行账户
```graphql
query test($req:GetBankAccountReq!){
  getBankAccount(req:$req){
    records{
      id
      memberId{
        id
        name
      }
      bank
      accountHolder
      accountNumber
      createdAt
      updatedAt
    }
    total
  }
}
```
```json
{
  "req":{
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
    "getBankAccount": {
      "records": [
        {
          "id": 2,
          "memberId": {
            "id": 2,
            "name": "测试"
          },
          "bank": "ABC",
          "accountHolder": "test",
          "accountNumber": "1111111",
          "createdAt": "2022-03-17T11:35:25.13199+08:00",
          "updatedAt": "2022-03-17T11:35:25.161569+08:00"
        }
      ],
      "total": 1
    }
  }
}
```