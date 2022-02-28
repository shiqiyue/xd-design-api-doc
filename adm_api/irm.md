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

# 素材授权模板

## 添加
```json
mutation addIdeaAuthTemplate($data:AddIdeaAuthTemplateInput!){
  addIdeaAuthTemplate(data:$data)
}
```
```json
{
  "data":{
   "name": "授权模板3",
    "isAllowEdit": true,
    "isDefault": true,
    "authScopes": [1,2,3],
    "authTime": "JUST_ONE_TIME",
    "authTimeLimit": 12,
    "authUseNum": "ONE_LIMITED",
    "authUseNumLimit": 1000,
    "authType": "NON_EXCLUSIVE_LICENSE",
    "authRegions": ["CHINA_MAINLAND"],
    "authLimits": []
  }
}
```

## 修改
```json
mutation editIdeaAuthTemplate($data:EditIdeaAuthTemplateInput!){
  editIdeaAuthTemplate(data:$data)
}
```
```json
{
  "data":{
    "id": 1,
    "name": "授权模板4",
    "isAllowEdit": true,
    "isDefault": true,
    "authScopes": [1,2,3],
    "authTime": "JUST_ONE_TIME",
    "authTimeLimit": 12,
    "authUseNum": "ONE_LIMITED",
    "authUseNumLimit": 1000,
    "authType": "NON_EXCLUSIVE_LICENSE",
    "authRegions": ["CHINA_MAINLAND"],
    "authLimits": []
  }
}
```

## 删除
```json
mutation removeIdeaAuthTemplate($data:RemoveIdeaAuthTemplateInput!){
  removeIdeaAuthTemplate(data:$data)
}
```
```json
{
  "data": {
    "ids": [1]
  }
}
```
## 设置默认授权模板
```json
mutation setDefaultIdeaAuthTemplate($data:SetDefaultIdeaAuthTemplateInput!){
  setDefaultIdeaAuthTemplate(data:$data)
}
```
```json
{
  "data": {
    "id": 2
  }
}
```

## 获取单个授权模板信息
```json
query {
  ideaAuthTemplate(id: 2){
  isDefault
  authTime
  authScopes{
  id
  content
}
isAllowEdit
id
}
}
```
## 获取授权模板信息列表
````json
query ideaAuthTemplates($data:IdeaAuthTemplatesInput!){
  ideaAuthTemplates(data: $data){
    total
    records{
      isDefault
      authTime
      authScopes{
        mustCheck
        id
        content
      }
    }
  }
}
````
```json
{
  "data": {
    "pageNum": 1,
		"pageSize": 10
  }
}
```
