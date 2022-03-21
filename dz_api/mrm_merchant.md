# 商家

## 申请个人商家
```graphql
mutation test($req:PersonMerchantRegisterReq!){
  personMerchantRegister(req:$req)
}
```
```json
{
  "req": {
    "name": "test",
    "iDCard": "1111",
    "iDNumber": "12222222",
    "iDType": "one"
  }
}
```
```json
{
  "data": {
    "personMerchantRegister": true
  }
}
```

## 申请商家企业
```graphql
mutation test($req:CompanyMerchantRegisterReq!){
  companyMerchantRegister(req:$req)
}
```
```json
{
  "req": {
    "name": "test",
    "legalPerson": "test",
    "legalPersonPhone": "1111",
    "companyAddress": "aaa",
    "establishTime": "2006-01-02T15:04:05.999999999Z",
    "businessLicense": "aaa",
    "socialCreditCode": "aaa"
  }
}
```
```json
{
  "data": {
    "companyMerchantRegister": true
  }
}
```

## 获取申请记录
```graphql
query test($req:GetSelfMerchantRegisterReq!){
  getSelfMerchantRegister(req:$req){
    record{
      id
      registerType
      createdAt
      status
      reviewTime
      passTime
      remark
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
    "getSelfMerchantRegister": {
      "record": [
        {
          "id": 1,
          "registerType": "PERSON",
          "createdAt": "2022-03-21T17:23:32.506018+08:00",
          "status": "IN_REVIEW",
          "reviewTime": null,
          "passTime": null,
          "remark": null
        },
        {
          "id": 2,
          "registerType": "PERSON",
          "createdAt": "2022-03-21T17:24:58.636231+08:00",
          "status": "IN_REVIEW",
          "reviewTime": null,
          "passTime": null,
          "remark": null
        },
        {
          "id": 3,
          "registerType": "COMPANY",
          "createdAt": "2022-03-21T19:50:28.751911+08:00",
          "status": "IN_REVIEW",
          "reviewTime": null,
          "passTime": null,
          "remark": null
        }
      ],
      "total": 3
    }
  }
}
```