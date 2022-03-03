
#banner

## 添加banner

### 例子
```graphql
mutation test1($req:AddBannerReq!){
  addBanner(req:$req){
    id
  }
}
```
```json
{
"req": {
"picture": "123",
"url": "1111"
}
}
```
```json
{
"data": {
"addBanner": {
"id": 3
}
}
}
```

## 修改banner显示状态
```graphql
mutation test1($req:EditBannerShowReq!){
    editBannerShow(req:$req)
}
```
```json
{
  "req": {
    "id": 3,
    "isShow": true
  }
}
```
```json
{
  "data": {
    "editBannerShow": true
  }
}
```

## 修改banner信息
```graphql
mutation test1($req:EditBannerReq!){
    editBanner(req:$req)
}
```
```json
{
  "req": {
    "id": 3,
    "picture": "1231",
    "url": "2124"
  }
}
```
```json
{
  "data": {
    "editBanner": true
  }
}
```

## 删除banner
```graphql

mutation test1($req:DelBannerReq!){
    delBanner(req:$req)
}
```
```json
{
  "req": {
    "id": 3
  }
}
```
```json
{
  "data": {
    "delBanner": true
  }
}
```

## 获取banner
```graphql
query test{
    getBanner{
        id
        createdAt
        createdBy
        updatedAt
        picture
        jumpUrl
        isShow
    }
}
```
```json
{
  "data": {
    "getBanner": [
      {
        "id": 1,
        "createdAt": "2022-03-02T16:02:15.478311+08:00",
        "createdBy": 2,
        "updatedAt": "2022-03-02T17:05:29.033049+08:00",
        "picture": "",
        "jumpUrl": "",
        "isShow": false
      },
      {
        "id": 3,
        "createdAt": "2022-03-03T11:00:49.883158+08:00",
        "createdBy": 2,
        "updatedAt": "2022-03-03T11:06:50.661838+08:00",
        "picture": "1231",
        "jumpUrl": "2124",
        "isShow": true
      }
    ]
  }
}
```
