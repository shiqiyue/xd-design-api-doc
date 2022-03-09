# 收藏夹

## 创建收藏夹
```graphql
mutation test($req:AddFavoritesReq!){
  addFavorites(req:$req)
}
```
```json
{
  "req": {
    "fileType": "IDEA",
    "name": "test"
  }
}
```
```json
{
  "data": {
    "addFavorites": true
  }
}
```

## 修改收藏夹
```graphql
mutation test($req:EditFavoritesReq!){
  editFavorites(req:$req)
}
```
```json
{
  "req": {
   "id": "4",
    "name": "test4"
  }
}
```
```json
{
  "data": {
    "editFavorites": true
  }
}
```

## 删除收藏夹 
```graphql
mutation test($req:DelFavoritesReq!){
  delFavorites(req:$req)
}
```
```json
{
  "req": {
  	"id": 4
  }
}
```
```json
{
  "data": {
    "delFavorites": true
  }
}
```

## 获取素材收藏夹
```graphql
query test($req:GetFavoritesReq!){
  getIdeaFavorites(req:$req){
    record{
      id
      name
      fileType
      memberId{
        id
        name
        createdAt
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
      "name": "test"
    },
   	"reverse": false,
    "sortKey": "ID"
  }
}
```
```json
{
  "data": {
    "getIdeaFavorites": {
      "record": [
        {
          "id": 5,
          "name": "test",
          "fileType": "IDEA",
          "memberId": {
            "id": 2,
            "name": "测试",
            "createdAt": "2022-02-11T14:07:12.662121+08:00"
          },
          "createdAt": "2022-03-08T16:50:36.459937+08:00",
          "updatedAt": "2022-03-08T16:50:36.459937+08:00"
        }
      ],
      "total": 1
    }
  }
}
```

## 获取设计收藏夹
```graphql
query test($req:GetFavoritesReq!){
  getDesignFavorites(req:$req){
    record{
      id
      name
      fileType
      memberId{
        id
        name
        createdAt
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
   	"reverse": false,
    "sortKey": "ID"
  }
}
```
```json
{
  "data": {
    "getDesignFavorites": {
      "record": [
        {
          "id": 1,
          "name": "素材1",
          "fileType": "DESIGN",
          "memberId": {
            "id": 2,
            "name": "测试",
            "createdAt": "2022-02-11T14:07:12.662121+08:00"
          },
          "createdAt": "2022-02-26T14:58:40.021519+08:00",
          "updatedAt": "2022-02-26T14:58:40.021519+08:00"
        },
        {
          "id": 2,
          "name": "素材2",
          "fileType": "DESIGN",
          "memberId": {
            "id": 2,
            "name": "测试",
            "createdAt": "2022-02-11T14:07:12.662121+08:00"
          },
          "createdAt": "2022-02-26T15:00:18.921765+08:00",
          "updatedAt": "2022-02-26T15:00:18.921765+08:00"
        }
      ],
      "total": 2
    }
  }
}
```

## 收藏素材
```graphql
mutation test($req:FavoriteIdeaReq!){
  favoriteIdea(req:$req)
}
```
```json
{
  "req": {
    "ideaId": 2,
    "favoriteId": 1
  }
}
```
```json
{
  "data": {
    "favoriteIdea": true
  }
}
```
## 移除收藏素材
```graphql
mutation test($req:RemoveFavoriteIdeaReq!){
  removeFavoriteIdea(req:$req)
}
```
```json
{
  "req": {
  	"id": [1]
  }
}
```
```json
{
  "data": {
    "removeFavoriteIdea": true
  }
}
```

## 收藏设计
```graphql
mutation test($req:FavoriteDesignReq!){
  favoriteDesign(req:$req)
}
```
```json
{
  "req": {
  	"designId": 1
  }
}
```
```json
{
  "data": {
    "favoriteDesign": true
  }
}
```

## 移除收藏设计
```graphql
mutation test($req:RemoveFavoriteDesignReq!){
  removeFavoriteDesign(req:$req)
}
```
```json
{
  "req": {
  	"id": [1]
  }
}
```
```json
{
  "data": {
    "removeFavoriteDesign": true
  }
}
```