# 商家

## 商家申请通过
```graphql
mutation test($req:MerchantRegisterSuccessfulReq!){
 merchantRegisterSuccessful(req:$req)
}
```
```json
{
  "req": {
   "id": 1
  }
}
```
```json
{
  "data": {
    "merchantRegisterSuccessful": true
  }
}
```

## 商家申请驳回
```graphql
mutation test($req:MerchantRegisterFailedReq!){
 merchantRegisterFailed(req:$req)
}
```
```json
{
  "req": {
   "id": 1,
    "remark": "test"
  }
}
```
```json
{
  "data": {
    "merchantRegisterFailed": true
  }
}
```

## 获取商家申请
```graphql
query test($req:GetMerchantRegisterReq!){
 getMerchantRegister(req:$req){
  	record{
  	  id
      memberId{
        id
        name
      }
      registerType
      reviewTime
      reviewerId{
        id
        name
      }
      createdAt
      passTime
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
    "getMerchantRegister": {
      "record": [
        {
          "id": 1,
          "memberId": {
            "id": 2,
            "name": "测试"
          },
          "registerType": "PERSON",
          "reviewTime": null,
          "reviewerId": null,
          "createdAt": "2022-03-21T17:23:32.506018+08:00",
          "passTime": null
        },
        {
          "id": 2,
          "memberId": {
            "id": 2,
            "name": "测试"
          },
          "registerType": "PERSON",
          "reviewTime": null,
          "reviewerId": null,
          "createdAt": "2022-03-21T17:24:58.636231+08:00",
          "passTime": null
        },
        {
          "id": 3,
          "memberId": {
            "id": 2,
            "name": "测试"
          },
          "registerType": "COMPANY",
          "reviewTime": null,
          "reviewerId": null,
          "createdAt": "2022-03-21T19:50:28.751911+08:00",
          "passTime": null
        }
      ],
      "total": 3
    }
  }
}
```