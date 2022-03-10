# 钱包

## 获取钱包

```graphql
query test{
    getSelfWallet{
        id
        memberId{
            id
            name
        }
        currency
        balance
        totalPayout
        totalEarning

    }
}
```

```json
{
  "data": {
    "getSelfWallet": {
      "id": 1,
      "memberId": {
        "id": 2,
        "name": "测试"
      },
      "currency": "CNY",
      "balance": 99890,
      "totalPayout": 0,
      "totalEarning": 0
    }
  }
}
```

## 获取账单流水

```graphql
query test($req:GetBillsReq!){
    getBills(req:$req){
        record{
            memberId{
                id
                name
            }
            billId
            billType
            amount
            createdAt
            remark
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
    "getBills": {
      "record": [
        {
          "memberId": {
            "id": 2,
            "name": "测试"
          },
          "billId": "",
          "billType": "PAYOUT",
          "amount": 100,
          "createdAt": "2022-03-10T09:43:08.126271+08:00",
          "remark": null
        }
      ],
      "total": 1
    }
  }
}
```

## 发起提现

```graphql
mutation test($req:AddPayoutReq!){
    addPayout(req:$req){
        id
        state
    }
}
```

```json
{
  "req": {
    "payoutMoney": 100,
    "bankAccountId": 1
  }
}
```

## 获取提现记录

```graphql
query test($req:PayoutRecordReq!){
    payoutRecord(req:$req){
        record{
            payoutMoney
            serviceMoney
            bank
            accountHolder
            accountNumber
            status
            createdAt
            updatedAt
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
    "payoutRecord": {
      "record": [
        {
          "payoutMoney": 100,
          "serviceMoney": 10,
          "bank": "PBC",
          "accountHolder": "108101088616511",
          "accountNumber": "测试",
          "status": "INITIATED",
          "createdAt": "2022-03-10T09:43:08.105796+08:00",
          "updatedAt": "2022-03-10T09:43:08.105796+08:00"
        }
      ],
      "total": 1
    }
  }
}
```

## 获取提现记录详情

```graphql
query test($req:PayoutDetailReq!){
    payoutDetail(req:$req){

        payoutMoney
        serviceMoney
        bank
        accountHolder
        accountNumber
        status
        createdAt
        updatedAt

    }
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
    "payoutDetail": {
      "payoutMoney": 100,
      "serviceMoney": 10,
      "bank": "PBC",
      "accountHolder": "108101088616511",
      "accountNumber": "测试",
      "status": "INITIATED",
      "createdAt": "2022-03-10T09:43:08.105796+08:00",
      "updatedAt": "2022-03-10T09:43:08.105796+08:00"
    }
  }
}
```