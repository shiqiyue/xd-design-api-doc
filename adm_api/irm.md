# 素材
## 添加素材
例子
```json
mutation addIdeas($data:AddIdeasInput!){
  addIdeas(data: $data)
}
```
```json
{
  "data":{
    "Ideas": [
      {
        "name": "素材1",
        "description": "素材描述21",
        "url": "dasdad",
        "originName": "dsadasd",
        "originCreator": "cacaca",
        "cc": "CC0",
        "memberId": 1,
        "tags": ["apple", "苹果", "梨子"]
      }
    ]
  }
}
```

## 查询单个素材
例子
```json
query idea{
  idea(id:1){
    tags
    id
    visible
    ideaReview{
      status
      passTime
    }
  }
}
```
## 查询素材
例子
```json
query ideas($data: IdeasInput!) {
  ideas(data: $data) {
    records {
      tags
      id
      visible
      ideaReview {
        status
      }
    }
    total
  }
}
```
```json
{
  "data": {
    "pageSize": 10,
    "pageNum": 1
  }
}
```

## 强制下架
例子
```json
mutation forceOfflineIdea($data:ForceOfflineIdeaInput!){
  forceOfflineIdea(data: $data)
}
```
```json
{
  "data": {
    "id": 1,
    "offlineReason": "www"
  }
}
```


## 素材审核通过
```json
mutation ideaReviewPass($data: IdeaReviewPassInput!){
  ideaReviewPass(data:$data)
}
```
```json
{
  "data":{
   "id": 1
  }
}
```
## 素材审核驳回
```json
mutation ideaReviewReject($data: IdeaReviewRejectInput!){
  ideaReviewReject(data:$data)
}
```
```json
{
  "data":{
   "id": 1,
    "rejectReason": "dsadas"
  }
}
```

## 查询单个审核记录
```json
query {
  ideaReview(id:1){
    status
    passTime
    reviewTime
  }
}
```

## 审核记录列表
```json
query ideaReviews($data:IdeaReviewsInput!){
  ideaReviews(data: $data){
    total
    records{
      status
      passTime
    }
  }
}
```
```json
{
  "data":{
   "pageNum": 1,
    "pageSize": 10
  }
}
```


## 授权范围字典列表
```json
query {
  authScopeDicts{
    id
    pid
    code
    content
  }
}
```
