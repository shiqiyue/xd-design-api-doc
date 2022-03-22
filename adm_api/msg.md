# 消息

## 添加会员消息
```graphql
mutation test($req:AddMemberMessageReq!){
 addMemberMessage(req:$req)
}
```
```json
{
  "req": {
   "memberId": [2],
    "title": "test",
    "content": "test content",
    "type": 1
  }
}
```
```json
{
  "data": {
    "addMemberMessage": true
  }
}
```

## 获取会员消息
```graphql
query test($req:GetMemberMessagesReq!){
 getMemberMessages(req:$req){
  record{
    id
    memberId{
      id
      name
    }
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
    "getMemberMessages": {
      "record": [
        {
          "id": 1,
          "memberId": {
            "id": 1,
            "name": "设计师"
          },
          "createdAt": "2022-02-23T10:09:37.324653+08:00",
          "updatedAt": "2022-02-23T10:18:18.672938+08:00",
          "content": "",
          "title": "",
          "type": 1,
          "isRead": true,
          "readAt": "2022-02-23T10:18:18.670918+08:00",
          "url": null
        },
        {
          "id": 2,
          "memberId": {
            "id": 2,
            "name": "测试"
          },
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
          "id": 3,
          "memberId": {
            "id": 1,
            "name": "设计师"
          },
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
          "id": 4,
          "memberId": {
            "id": 2,
            "name": "测试"
          },
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
          "id": 5,
          "memberId": {
            "id": 1,
            "name": "设计师"
          },
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
          "id": 6,
          "memberId": {
            "id": 2,
            "name": "测试"
          },
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
          "memberId": {
            "id": 2,
            "name": "测试"
          },
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
          "memberId": {
            "id": 2,
            "name": "测试"
          },
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
      "total": 8
    }
  }
}
```

## 添加公告
```graphql
mutation test($req:AddNoticeReq!){
 addNotice(req:$req)
}
```
```json
{
  "req": {
   "title": "test",
    "content": "test content",
    "status": 1,
    "url": "11"
  }
}
```
```json
{
  "data": {
    "addNotice": true
  }
}
```

## 修改公告
```graphql
mutation test($req:EditNoticeReq!){
 editNotice(req:$req)
}
```
```json
{
  "req": {
    "id": 1,
   "title": "test",
    "content": "test content",
    "status": 1,
    "url": "11"
  }
}
```
```json
{
  "data": {
    "editNotice": true
  }
}
```

## 获取公告
```graphql
query test($req:GetNoticeReq!){
 getNotice(req:$req){
  record{
    id
    content
    title
    status
    url
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
    "getNotice": {
      "record": [
        {
          "id": 1,
          "content": "test content",
          "title": "test",
          "status": 1,
          "url": "11",
          "createdAt": "2022-03-12T14:57:32.569647+08:00",
          "updatedAt": "2022-03-22T14:56:33.078796+08:00"
        },
        {
          "id": 2,
          "content": "2",
          "title": "1",
          "status": 1,
          "url": null,
          "createdAt": "2022-03-12T16:33:30.846913+08:00",
          "updatedAt": "2022-03-12T16:33:30.846913+08:00"
        },
        {
          "id": 3,
          "content": "2",
          "title": "1",
          "status": 1,
          "url": null,
          "createdAt": "2022-03-12T16:44:20.73692+08:00",
          "updatedAt": "2022-03-12T16:44:20.73692+08:00"
        },
        {
          "id": 4,
          "content": "2",
          "title": "1",
          "status": 1,
          "url": null,
          "createdAt": "2022-03-12T16:59:48.336007+08:00",
          "updatedAt": "2022-03-12T16:59:48.336007+08:00"
        },
        {
          "id": 5,
          "content": "2",
          "title": "1",
          "status": 1,
          "url": null,
          "createdAt": "2022-03-12T17:17:18.42195+08:00",
          "updatedAt": "2022-03-12T17:17:18.42195+08:00"
        },
        {
          "id": 6,
          "content": "2",
          "title": "1",
          "status": 1,
          "url": null,
          "createdAt": "2022-03-12T17:17:46.495384+08:00",
          "updatedAt": "2022-03-12T17:17:46.495384+08:00"
        },
        {
          "id": 7,
          "content": "test content",
          "title": "test",
          "status": 1,
          "url": "11",
          "createdAt": "2022-03-22T14:53:59.765593+08:00",
          "updatedAt": "2022-03-22T14:53:59.765593+08:00"
        }
      ],
      "total": 7
    }
  }
}
```

## 获取公告已读
```graphql
query test($req:GetNoticeFlagReq!){
 getNoticeFlag(req:$req){
  record{
    id
    memberId{
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
      "id": 1
    },
    "reverse": false,
    "sortKey": "ID"
  }
}
```
```json
{
  "data": {
    "getNoticeFlag": {
      "record": [],
      "total": 0
    }
  }
}
```

## 添加系统用户消息
```graphql
mutation test($req:AddSystemUserMessageReq!){
 addSystemUserMessage(req:$req)
}
```
```json
{
  "req": {
   "userId": [2],
    "title": "test",
    "content": "test content",
    "type": 1,
    "url": "111"
  }
}
```
```json
{
  "data": {
    "addSystemUserMessage": true
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