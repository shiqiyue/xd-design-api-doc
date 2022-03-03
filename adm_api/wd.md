
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

# 热门素材

## 添加热门素材
```graphql
mutation test($req:AddHotIdeaReq!){
    addHotIdea(req:$req)
}
```
```json
{
  "req": {
    "ideaId": [1,2]
  }
}
```
```json
{
  "data": {
    "addHotIdea": true
  }
}
```

## 获取热门素材
```graphql
query test{
    getHotIdea{
        id
        idea{
            id
            memberId
            ideaType
            url
            name
            description
            tags
            isFree
            cc
        }
    }
}
```
```json
{
  "data": {
    "getHotIdea": [
      {
        "id": 3,
        "idea": {
          "id": 1,
          "memberId": 1,
          "ideaType": "IMAGE",
          "url": "acasca",
          "name": "sdasda",
          "description": "sdasda",
          "tags": [
            "西瓜",
            "香蕉"
          ],
          "isFree": true,
          "cc": "CC0"
        }
      },
      {
        "id": 4,
        "idea": {
          "id": 2,
          "memberId": 2,
          "ideaType": "IMAGE",
          "url": "dasdad",
          "name": "素材1",
          "description": "素材描述21",
          "tags": [
            "apple",
            "苹果",
            "梨子"
          ],
          "isFree": true,
          "cc": "CC0"
        }
      }
    ]
  }
}
```

## 删除热门素材
```graphql
mutation test1($req:DelHotIdeaReq!) {
    delHotIdea(req:$req)
}
```
```json
{
  "req": {
    "id": [3,4]
  }
}
```
```json
{
  "data": {
    "delHotIdea": true
  }
}
```

# 热门版型

## 添加热门版型
```graphql
mutation test1($req:AddHotModelReq!) {
    addHotModel(req:$req)
}
```
```json
{
  "req": {
    "modelId": [1,2,3]
  }
}
```
```json
{
  "data": {
    "addHotModel": true
  }
}
```

## 获取热门版型
```graphql
query test{
    getHotModel{
        id
        model{
            id
            createdAt
            updatedAt
            name
            coding
            categoryID
            price
            views
            sizeTemplateID
            sizeArea
            sizeCrowd
            brand
            origin
            describe
            category{
                name
            }
        }
    }
}
```
```json
{
  "data": {
    "getHotModel": [
      {
        "id": 1,
        "model": {
          "id": 1,
          "createdAt": "2022-02-16T16:49:51.143488+08:00",
          "updatedAt": "2022-02-25T10:04:17.867957+08:00",
          "name": "wy",
          "coding": "000001",
          "categoryID": 2,
          "price": 999,
          "views": [
            1,
            2,
            3
          ],
          "sizeTemplateID": 1,
          "sizeArea": null,
          "sizeCrowd": null,
          "brand": null,
          "origin": null,
          "describe": null,
          "category": {
            "name": "tx"
          }
        }
      },
      {
        "id": 2,
        "model": {
          "id": 2,
          "createdAt": "2022-02-16T16:58:45.896704+08:00",
          "updatedAt": "2022-02-25T10:04:33.684807+08:00",
          "name": "tx",
          "coding": "000002",
          "categoryID": 2,
          "price": 999,
          "views": [
            1,
            2,
            3
          ],
          "sizeTemplateID": 1,
          "sizeArea": null,
          "sizeCrowd": null,
          "brand": null,
          "origin": null,
          "describe": null,
          "category": {
            "name": "tx"
          }
        }
      },
      {
        "id": 3,
        "model": {
          "id": 3,
          "createdAt": "2022-02-25T14:14:31.426687+08:00",
          "updatedAt": "2022-02-25T14:15:38.420006+08:00",
          "name": "wt",
          "coding": "000003",
          "categoryID": 2,
          "price": 999,
          "views": [
            4,
            5,
            6
          ],
          "sizeTemplateID": 1,
          "sizeArea": null,
          "sizeCrowd": null,
          "brand": null,
          "origin": null,
          "describe": null,
          "category": {
            "name": "tx"
          }
        }
      }
    ]
  }
}
```

## 删除热门版型
```graphql
mutation test1($req:DelHotModelReq!) {
    delHotModel(req:$req)
}
```
```json
{
  "req": {
    "id":  [1,2,3]
  }
}
```
```json
{
  "data": {
    "delHotModel": true
  }
}
```