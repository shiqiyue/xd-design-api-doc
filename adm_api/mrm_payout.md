# 提现

## 提现成功
```graphql

mutation test($req:PayoutSuccessfulReq!){
  payoutSuccessful(req:$req)
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
    "payoutSuccessful": true
  }
}
```
## 提现失败
```graphql
mutation test($req:PayoutFailedReq!){
  payoutFailed(req:$req)
}
```
```json
{
  "req": {
    "id": 1,
    "remark": "不允许"
  }
}
```
```json
{
  "data": {
    "payoutFailed": true
  }
}
```

## 获取提现记录
```graphql

query test($req:PayoutApplicationsReq!){
  payoutApplications(req:$req){
    record{
      id
      memberId{
        id
        name
      }
      payoutMoney
      serviceMoney
      bank
      accountHolder
      accountNumber
      status
      reviewTime
      reviewerId{
        id
        name
      }
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
    "reverse": false,
    "sortKey": "ID"
  }
}
```
```json
{
  "data": {
    "payoutApplications": {
      "record": [
        {
          "id": 1,
          "memberId": {
            "id": 2,
            "name": "测试"
          },
          "payoutMoney": 100,
          "serviceMoney": 10,
          "bank": "PBC",
          "accountHolder": "108101088616511",
          "accountNumber": "测试",
          "status": "FAILED",
          "reviewTime": "2022-03-10T14:31:52.702229+08:00",
          "reviewerId": null,
          "createdAt": "2022-03-10T09:43:08.105796+08:00"
        },
        {
          "id": 2,
          "memberId": {
            "id": 2,
            "name": "测试"
          },
          "payoutMoney": 100,
          "serviceMoney": 10,
          "bank": "PBC",
          "accountHolder": "108101088616511",
          "accountNumber": "测试",
          "status": "SUCCESSFUL",
          "reviewTime": "2022-03-10T14:46:00.694866+08:00",
          "reviewerId": null,
          "createdAt": "2022-03-10T14:42:56.918858+08:00"
        }
      ],
      "total": 2
    }
  }
}
```

## 获取提现记录详情
```graphql

query test($req:PayoutDetailReq!){
  payoutDetail(req:$req){
      id
      memberId{
        id
        name
      }
      payoutMoney
      serviceMoney
      bank
      accountHolder
      accountNumber
      status
      reviewTime
      reviewerId{
        id
        name
      }
      createdAt
  
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
      "id": 1,
      "memberId": {
        "id": 2,
        "name": "测试"
      },
      "payoutMoney": 100,
      "serviceMoney": 10,
      "bank": "PBC",
      "accountHolder": "108101088616511",
      "accountNumber": "测试",
      "status": "FAILED",
      "reviewTime": "2022-03-10T14:31:52.702229+08:00",
      "reviewerId": null,
      "createdAt": "2022-03-10T09:43:08.105796+08:00"
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
        },
        {
          "memberId": {
            "id": 2,
            "name": "测试"
          },
          "billId": "c12e8479-0bf6-42a5-9d86-d938e79b0015",
          "billType": "SEND_BACK",
          "amount": 110,
          "createdAt": "2022-03-10T14:31:52.774402+08:00",
          "remark": "不允许"
        },
        {
          "memberId": {
            "id": 2,
            "name": "测试"
          },
          "billId": "5999e5b1-f334-45bc-92fd-d87af6415169",
          "billType": "PAYOUT",
          "amount": 100,
          "createdAt": "2022-03-10T14:42:56.938037+08:00",
          "remark": null
        }
      ],
      "total": 3
    }
  }
}
```
## 账单流水详情
```graphql

query test($req:GetBillReq!){
  getBill(req:$req){

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
    "getBill": {
      "memberId": {
        "id": 2,
        "name": "测试"
      },
      "billId": "c12e8479-0bf6-42a5-9d86-d938e79b0015",
      "billType": "SEND_BACK",
      "amount": 110,
      "createdAt": "2022-03-10T14:31:52.774402+08:00",
      "remark": "不允许"
    }
  }
}
```
## 获取会员钱包
```graphql

query test($req:GetWalletsReq!){
  getWallets(req:$req){
    record{
      id
      memberId{
        id
        name
      }
      balance
      totalPayout
      totalEarning
      totalPayout
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
    "pageSize": 10
  }
}
```
```json
{
  "data": {
    "getWallets": {
      "record": [
        {
          "id": 1,
          "memberId": {
            "id": 2,
            "name": "测试"
          },
          "balance": 99890,
          "totalPayout": 0,
          "totalEarning": 0,
          "createdAt": "2022-03-10T09:42:12+08:00",
          "updatedAt": "2022-03-10T14:42:56.882267+08:00"
        }
      ],
      "total": 1
    }
  }
}
```