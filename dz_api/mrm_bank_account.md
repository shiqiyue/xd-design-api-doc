# 银行账户

## 添加
```graphql
mutation test($req:AddBankAccountReq!){
  addBankAccount(req:$req)
}

```
```json
{
  "req": {
    "bank": "ABC",
    "accountHolder": "test",
    "accountNumber": "1111111"
  }
}
```
```json
{
  "data": {
    "addBankAccount": true
  }
}
```

## 修改
```graphql
mutation test($req:EditBankAccountReq!){
  editBankAccount(req:$req)
}


```
```json
{
  "req": {
    "id": 1,
    "bank": "BANKCOMM",
    "accountHolder": "test",
    "accountNumber": "1111111"
  }
}
```
```json
{
  "data": {
    "editBankAccount": true
  }
}
```

## 删除
```graphql
mutation test($req:DelBankAccountReq!){
  delBankAccount(req:$req)
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
    "delBankAccount": true
  }
}
```

## 查询
```graphql
query test1{
  getSelfBankAccount{
    id
    bank
    accountHolder
    accountNumber
  }
}
```
```json
{
  "data": {
    "getSelfBankAccount": [
      {
        "id": 1,
        "bank": "BANKCOMM",
        "accountHolder": "test",
        "accountNumber": "1111111"
      },
      {
        "id": 2,
        "bank": "ABC",
        "accountHolder": "test",
        "accountNumber": "1111111"
      }
    ]
  }
}
```