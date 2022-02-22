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
