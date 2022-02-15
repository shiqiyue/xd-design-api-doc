# 标签
## 添加标签
例子:
```graphql
mutation addTag($data:AddTagInput!){
  addTag(data:$data)
}

```
```json
{
  "data":{
     "name": "apple",
    "aliases": ["苹果"]
  }
}
```

## 修改标签
例子:
```graphql
mutation editTag($data:EditTagInput!){
    editTag(data:$data)
}

```
```json
{
  "data":{
    "id": 1,
    "name": "apple",
    "aliases": ["苹果12"]
  }
}
```

## 禁用标签
例子
```graphql
mutation disableTag($data:DisableTagInput!){
    disableTag(data:$data)
}

```
```json
{
  "data":{
    "id": 1,
    "reason": "涉黄"
  }
}
```

## 启用标签
例子
```graphql
mutation enableTag($data:EnableTagInput!){
    enableTag(data:$data)
}

```
```json
{
  "data":{
    "id": 1
  }
}
```

## 通过ID查询单个标签
例子
```graphql
query tag{
    tag(id:1){
        aliases
        disabled
        disabledReason
        id
        name
    }
}
```

## 标签列表查询
例子
```graphql
query tags($data:TagsQuery!){
    tags(query:$data){
        total
        records{
            createdAt
            id
            aliases
            name
        }
    }
}
```
```json
{
  "data":{
    "pageNum": 1,
    "pageSize": 10,
    "filter": {
      "disabled": true
    }
  }
}
```

# 敏感词

## 添加敏感词
例子
```graphql
mutation addSensitiveWord($data:AddSensitiveWordInput!){
    addSensitiveWord(data:$data)
}
```
```json
{
  "data":{
    "name": "apple",
    "aliases": ["苹果"],
    "type": 1
  }
}
```

## 修改敏感词
例子
```graphql
mutation editSensitiveWord($data:EditSensitiveWordInput!){
    editSensitiveWord(data:$data)
}
```
```json
{
  "data":{
    "id": 1,
    "name": "apple",
    "aliases": ["苹果2"],
    "type": 1
  }
}
```

## 删除敏感词
例子
```graphql
mutation removeSensitiveWord($data:RemoveSensitiveWordInput!){
    removeSensitiveWord(data:$data)
}
```
```json
{
  "data":{
    "id": 1
  }
}
```
## 通过ID查询单个敏感词
```graphql
query {
    sensitiveWord(id:1){
        id
        createdAt
        createdBy
        name
        aliases
    }
}
```
## 敏感词列表查询
```graphql
query sensitiveWords($data:SensitiveWordsInput!){
    sensitiveWords(query:$data){
        total
        records{
            createdAt
            id
            aliases
            name
        }
    }
}
```
```json
{
  "data":{
    "pageNum": 1,
    "pageSize": 10,
    "filter": {
      "type":  1
    }
  }
}
```
