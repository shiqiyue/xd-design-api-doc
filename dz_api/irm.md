# 素材
## 添加素材
例子
```json
mutation addIdea($data:AddIdeaInput!){
  addIdea(data: $data)
}
```
```json
{
  "data":{
      
        "name": "素材1",
        "description": "素材描述21",
        "url": "dasdad",
        "originName": "dsadasd",
        "originCreator": "cacaca",
        "cc": "CC0",
        "tags": ["apple", "苹果", "梨子"]
      
  }
}
```

## 修改素材
```json
mutation updateIdea($data:EditIdeaInput!){
  editIdea(data:$data)
}
```
```json
{
  "data":{
   "id": 1,
    "tags": ["西瓜", "香蕉"],
    "description": "adasdad",
    "name": "sdasda",
    "url": "acasca",
    "originName": "dasdasd",
    "originCreator": "dacac",
    "cc": "CC0"
  }
}
```

## 删除素材
```json
mutation {
  removeIdeas(ids:[1])
}
```


## 查询单个素材
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


## 我的素材查询
```json
query myIdeas($data:MyIdeasInput!){
  myIdeas(data:$data){
   total
    records{
      description
    }
  }
}
```
```json
{
  "data":{
   "pageNum": 1,
    "pageSize": 2
  }
}
```

## 公共素材查询
```json
query publicIdeas($data:PublicIdeasInput!){
  publicIdeas(data:$data){
   total
    records{
      description
    }
  }
}
```
```json
{
  "data":{
   "pageNum": 1,
    "pageSize": 2
  }
}
```
