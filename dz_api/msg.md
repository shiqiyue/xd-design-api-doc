# 消息

## 获取会员消息
```graphql
query test($req:MemberMessageListReq!){
 memberMessageList(req:$req){
  record{
    id
    createdAt
    updatedAt
    content
    title
    type
    isRead
    readAt
    url
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
    "memberMessageList": {
      "record": [
        {
          "id": 2,
          "createdAt": "2022-02-23T10:09:37.324653+08:00",
          "updatedAt": "2022-02-23T10:09:37.324653+08:00",
          "content": "",
          "title": "",
          "type": 1,
          "isRead": false,
          "readAt": null,
          "url": null
        },
        {
          "id": 4,
          "createdAt": "2022-02-23T10:19:37.628654+08:00",
          "updatedAt": "2022-02-23T10:19:37.628654+08:00",
          "content": "2",
          "title": "1",
          "type": 1,
          "isRead": false,
          "readAt": null,
          "url": null
        },
        {
          "id": 6,
          "createdAt": "2022-02-23T10:28:12.413309+08:00",
          "updatedAt": "2022-02-23T10:28:12.413309+08:00",
          "content": "2",
          "title": "1",
          "type": 1,
          "isRead": false,
          "readAt": null,
          "url": null
        },
        {
          "id": 7,
          "createdAt": "2022-03-22T14:39:24.985822+08:00",
          "updatedAt": "2022-03-22T14:39:24.985822+08:00",
          "content": "test content",
          "title": "test",
          "type": 1,
          "isRead": false,
          "readAt": null,
          "url": "a"
        },
        {
          "id": 8,
          "createdAt": "2022-03-22T14:40:24.949455+08:00",
          "updatedAt": "2022-03-22T14:40:24.949455+08:00",
          "content": "test content",
          "title": "test",
          "type": 1,
          "isRead": false,
          "readAt": null,
          "url": "a"
        }
      ],
      "total": 5
    }
  }
}
```

## 获取会员消息详情
```graphql
query test($req:GetMemberMessageDetailReq!){
 getMemberMessageDetail(req:$req){
  
    id
    createdAt
    updatedAt
    content
    title
    type
    isRead
    readAt
    url
 
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
    "getMemberMessageDetail": {
      "id": 2,
      "createdAt": "2022-02-23T10:09:37.324653+08:00",
      "updatedAt": "2022-02-23T10:09:37.324653+08:00",
      "content": "",
      "title": "",
      "type": 1,
      "isRead": false,
      "readAt": null,
      "url": null
    }
  }
}
```

## 获取公告
```graphql
query test($req:GetNoticeReq!){
 getNotice(req:$req){
  record{
    id
    title
    content
    status
    createdAt
    url
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
    "getNotice": {
      "record": [
        {
          "id": 1,
          "title": "test",
          "content": "test content",
          "status": 1,
          "createdAt": "2022-03-12T14:57:32.569647+08:00",
          "url": "11"
        },
        {
          "id": 2,
          "title": "1",
          "content": "2",
          "status": 1,
          "createdAt": "2022-03-12T16:33:30.846913+08:00",
          "url": null
        },
        {
          "id": 3,
          "title": "1",
          "content": "2",
          "status": 1,
          "createdAt": "2022-03-12T16:44:20.73692+08:00",
          "url": null
        },
        {
          "id": 4,
          "title": "1",
          "content": "2",
          "status": 1,
          "createdAt": "2022-03-12T16:59:48.336007+08:00",
          "url": null
        },
        {
          "id": 5,
          "title": "1",
          "content": "2",
          "status": 1,
          "createdAt": "2022-03-12T17:17:18.42195+08:00",
          "url": null
        },
        {
          "id": 6,
          "title": "1",
          "content": "2",
          "status": 1,
          "createdAt": "2022-03-12T17:17:46.495384+08:00",
          "url": null
        },
        {
          "id": 7,
          "title": "test",
          "content": "test content",
          "status": 1,
          "createdAt": "2022-03-22T14:53:59.765593+08:00",
          "url": "11"
        }
      ],
      "total": 7
    }
  }
}
```

## 获取公告详情
```graphql
query test($req:GetNoticeDetailReq!){
 getNoticeDetail(req:$req){
  
    id
    title
    content
    status
    createdAt
    url
 
 }
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
    "getNoticeDetail": {
      "id": 4,
      "title": "1",
      "content": "2",
      "status": 1,
      "createdAt": "2022-03-12T16:59:48.336007+08:00",
      "url": null
    }
  }
}
```

## 获取系统用户消息
```graphql
query test($req:GetSystemUserMessagesReq!){
 getSystemUserMessages(req:$req){
  record{
    id
    createdAt
    updatedAt
    userId
    title
    content
    type
    isRead
    readAt
    url
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
    "getSystemUserMessages": {
      "record": [
        {
          "id": 1,
          "createdAt": "2022-03-22T15:07:55.73893+08:00",
          "updatedAt": "2022-03-22T15:07:55.73893+08:00",
          "userId": 2,
          "title": "test",
          "content": "test content",
          "type": 1,
          "isRead": false,
          "readAt": null,
          "url": "111"
        }
      ],
      "total": 1
    }
  }
}
```

## 获取系统用户消息详情
```graphql
query test($req:GetSystemUserMessageDetailReq!){
 getSystemUserMessageDetail(req:$req){
		 id
    createdAt
    updatedAt
    userId
    title
    content
    type
    isRead
    readAt
    url

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
    "getSystemUserMessageDetail": {
      "id": 1,
      "createdAt": "2022-03-22T15:07:55.73893+08:00",
      "updatedAt": "2022-03-22T15:07:55.73893+08:00",
      "userId": 2,
      "title": "test",
      "content": "test content",
      "type": 1,
      "isRead": false,
      "readAt": null,
      "url": "111"
    }
  }
}
```