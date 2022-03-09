# 收藏

## 获取素材收藏
```graphql
query test($req:GetIdeaFavoriteReq!){
  getIdeaFavorite(req:$req){
    record{
      id
      ideaId{
        id
      	memberId
        ideaType
        url
        name
        description
      }
      memberId{
        id
        name
        avatar
      }
      favoriteId{
        id
        name
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
  "req": {
    "pageNum": 1,
    "pageSize": 10,
    "filter": {
      "ideaId": 1
    },
    "reverse": false,
    "sortKey": "ID"
  }
}
```
```json
{
  "data": {
    "getIdeaFavorite": {
      "record": [
        {
          "id": 2,
          "ideaId": {
            "id": 1,
            "memberId": 1,
            "ideaType": "IMAGE",
            "url": "acasca",
            "name": "sdasda",
            "description": "sdasda"
          },
          "memberId": {
            "id": 2,
            "name": "测试",
            "avatar": null
          },
          "favoriteId": {
            "id": 5,
            "name": "素材1"
          },
          "createdAt": "2022-03-09T09:54:02.490504+08:00",
          "updatedAt": "2022-03-09T09:54:02.490504+08:00"
        }
      ],
      "total": 1
    }
  }
}
```

## 获取收藏素材
```graphql
query test($req:GetDesignFavoriteReq!){
  getDesignFavorite(req:$req){
    record{
      id
      designId{
        id
        name
        modelID
        price
      }
      memberId{
        id
        name
        avatar
      }
      favoriteId{
        id
        name
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
  "req": {
    "pageNum": 1,
    "pageSize": 10,
    "filter": {
      "designId":  2
    },
    "reverse": false,
    "sortKey": "ID"
  }
}
```
```json
{
  "data": {
    "getDesignFavorite": {
      "record": [
        {
          "id": 3,
          "designId": {
            "id": 2,
            "name": "wt",
            "modelID": 1,
            "price": 3700
          },
          "memberId": {
            "id": 2,
            "name": "测试",
            "avatar": null
          },
          "favoriteId": {
            "id": 1,
            "name": "设计1"
          },
          "createdAt": "2022-03-09T10:05:18.652683+08:00",
          "updatedAt": "2022-03-09T10:05:18.652683+08:00"
        }
      ],
      "total": 1
    }
  }
}
```