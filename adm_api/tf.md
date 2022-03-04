# 举报

## 设计师申诉

### 设计师申诉通过

```graphql
mutation test($data:PassDesignerAppealInput!){
    passDesignerAppeal(data:$data)
}
```

```json
{
  "data": {
    "id": 1,
    "dealResult": "test"
  }
}
```

```json
{
  "data": {
    "passDesignerAppeal": true
  }
}
```

### 设计师申诉拒绝

```graphql
mutation test($data:RejectDesignerAppealInput!){
    rejectDesignerAppeal(data:$data)
}
```

```json
{
  "data": {
    "id": 2,
    "dealResult": "test"
  }
}
```

```json
{
  "data": {
    "rejectDesignerAppeal": true
  }
}
```

### 获取设计师申诉列表

```graphql
query test($query:DesignerAppealsInput!){
    designerAppeals(query:$query){
        records{
            id
            createdAt
            updatedAt
            designerId
            reason
            materials
            dealStatus
            dealResult
            dealAt
            dealBy
        }
        total
    }
}
```

```json
{
  "query": {
    "pageNum": 1,
    "pageSize": 10,
    "filter": {
      "designerId": 1
    },
    "reverse": false,
    "sortKey": "ID"
  }
}
```

```json
{
  "data": {
    "designerAppeals": {
      "records": [
        {
          "id": 1,
          "createdAt": "2022-03-04T15:01:54.42354+08:00",
          "updatedAt": "2022-03-04T15:23:54.955225+08:00",
          "designerId": 1,
          "reason": "test",
          "materials": [
            "",
            ""
          ],
          "dealStatus": "DEAL",
          "dealResult": "test",
          "dealAt": "2022-03-04T15:23:54.952226+08:00",
          "dealBy": 2
        },
        {
          "id": 2,
          "createdAt": "2022-03-04T15:02:46.632133+08:00",
          "updatedAt": "2022-03-04T15:28:04.594409+08:00",
          "designerId": 1,
          "reason": "test",
          "materials": [
            "",
            ""
          ],
          "dealStatus": "REJECT",
          "dealResult": "test",
          "dealAt": "2022-03-04T15:28:04.591896+08:00",
          "dealBy": 2
        }
      ],
      "total": 2
    }
  }
}
```

### 获取设计师申诉

```graphql
query test{
    designerAppeal(id:1){

        id
        createdAt
        updatedAt
        designerId
        reason
        materials
        dealStatus
        dealResult
        dealAt
        dealBy


    }
}
```

```json
{
  "data": {
    "designerAppeal": {
      "id": 1,
      "createdAt": "2022-03-04T15:01:54.42354+08:00",
      "updatedAt": "2022-03-04T15:23:54.955225+08:00",
      "designerId": 1,
      "reason": "test",
      "materials": [
        "",
        ""
      ],
      "dealStatus": "DEAL",
      "dealResult": "test",
      "dealAt": "2022-03-04T15:23:54.952226+08:00",
      "dealBy": 2
    }
  }
}
```

## 举报设计师

### 设计师举报通过

```graphql
mutation test($data:PassDesignerTipOffInput!){
    passDesignerTipOff(data:$data)
}
```

```json
{
  "data": {
    "id": 1,
    "dealResult": "test"
  }
}
```

```json
{
  "data": {
    "passDesignerTipOff": true
  }
}
```

### 设计师举报拒绝

```graphql
mutation test($data:RejectDesignerTipOffInput!){
    rejectDesignerTipOff(data:$data)
}
```

```json
{
  "data": {
    "id": 2,
    "dealResult": "test"
  }
}
```

```json
{
  "data": {
    "rejectDesignerTipOff": true
  }
}
```

### 获取设计师举报列表

```graphql
query test($query:DesignerTipOffsInput!){
    designerTipOffs(query:$query){
        records{
            id
            createdAt
            updatedAt
            tipOffMember{
                id
                name
                avatar
            }
            beTipOffMember{
                id
                name
                avatar
            }
            reason
            materials
            dealStatus
            dealResult
            dealAt
            dealBy{
                id
                name
                username
                Role{
                    name
                    code
                }
            }
        }
        total
    }
}
```

```json
{
  "query": {
    "pageNum": 1,
    "pageSize": 10,
    "filter": {
      "tipOffMemberId": 2
    },
    "reverse": false,
    "sortKey": "ID"
  }
}
```

```json
{
  "data": {
    "designerTipOffs": {
      "records": [
        {
          "id": 1,
          "createdAt": "2022-03-04T15:12:01.330313+08:00",
          "updatedAt": "2022-03-04T15:47:42.72484+08:00",
          "tipOffMember": {
            "id": 2,
            "name": "测试",
            "avatar": null
          },
          "beTipOffMember": {
            "id": 2,
            "name": "测试",
            "avatar": null
          },
          "reason": "Test",
          "materials": [
            "test"
          ],
          "dealStatus": "DEAL",
          "dealResult": "test",
          "dealAt": "2022-03-04T15:47:42.721312+08:00",
          "dealBy": null
        },
        {
          "id": 2,
          "createdAt": "2022-03-04T15:12:08.241003+08:00",
          "updatedAt": "2022-03-04T15:48:43.29911+08:00",
          "tipOffMember": {
            "id": 2,
            "name": "测试",
            "avatar": null
          },
          "beTipOffMember": {
            "id": 2,
            "name": "测试",
            "avatar": null
          },
          "reason": "Test",
          "materials": [
            "test"
          ],
          "dealStatus": "REJECT",
          "dealResult": "test",
          "dealAt": "2022-03-04T15:48:43.295045+08:00",
          "dealBy": null
        }
      ],
      "total": 2
    }
  }
}
```

### 获取设计师举报
```graphql
query test{
  designerTipOff(id:1){
   
      id
      createdAt
      updatedAt
      tipOffMember{
        id
        name
        avatar
      }
      beTipOffMember{
        id
        name
        avatar
      }
      reason
      materials
      dealStatus
      dealResult
      dealAt
      dealBy{
        id
        name
        username
  			Role{
          name
          code
        }
      }
    }
  
  
}
```
```json
{
  "data": {
    "designerTipOff": {
      "id": 1,
      "createdAt": "2022-03-04T15:12:01.330313+08:00",
      "updatedAt": "2022-03-04T15:47:42.72484+08:00",
      "tipOffMember": {
        "id": 2,
        "name": "测试",
        "avatar": null
      },
      "beTipOffMember": {
        "id": 2,
        "name": "测试",
        "avatar": null
      },
      "reason": "Test",
      "materials": [
        "test"
      ],
      "dealStatus": "DEAL",
      "dealResult": "test",
      "dealAt": "2022-03-04T15:47:42.721312+08:00",
      "dealBy": null
    }
  }
}
```

## 素材申诉

### 通过素材申诉
```graphql
mutation test($data:PassIdeaAppealInput!){
  passIdeaAppeal(data:$data)
}
```
```json
{
  "data": {
    "id": 1,
    "dealResult": "test"
  }
}
```
```json
{
  "data": {
    "passIdeaAppeal": true
  }
}
```

### 拒绝素材申诉
```graphql
mutation test($data:RejectIdeaAppealInput!){
    rejectIdeaAppeal(data:$data)
}
```
```json
{
  "data": {
    "id": 2,
    "dealResult": "test"
  }
}
```
```json
{
  "data": {
    "rejectIdeaAppeal": true
  }
}
```
### 获取素材申诉列表
```graphql
query test($query:IdeaAppealsInput!){
  ideaAppeals(query:$query){
    records{
      id
      createdAt
      updatedAt
      ideaId{
        memberId
        ideaType
        url
        description
        tags
        reviewStatus
        blacklistStatus
        price
        originCreator
        originName
        cc
        isFree
      }
      reason
      materials
      dealStatus
      dealResult
      dealAt
      dealBy{
        id
        Role{
          id
          name
          code
        }
        name
        username
      }
    }
    total
  }
}
```
```json
{
  "query": {
    "pageNum": 1,
    "pageSize": 10,
    "filter": {
      "ideaId": 2
    },
    "reverse": false,
    "sortKey": "ID"
  }
}
```
```graphql
{
  "data": {
    "ideaAppeals": {
      "records": [
        {
          "id": 1,
          "createdAt": "2022-03-04T15:19:05.78028+08:00",
          "updatedAt": "2022-03-04T16:32:52.486682+08:00",
          "ideaId": {
            "memberId": 2,
            "ideaType": "IMAGE",
            "url": "dasdad",
            "description": "素材描述21",
            "tags": [
              "apple",
              "苹果",
              "梨子"
            ],
            "reviewStatus": "REJECT",
            "blacklistStatus": "NORMAL",
            "price": null,
            "originCreator": "cacaca",
            "originName": "dsadasd",
            "cc": "CC0",
            "isFree": true
          },
          "reason": "Test",
          "materials": [
            ""
          ],
          "dealStatus": "DEAL",
          "dealResult": "test",
          "dealAt": "2022-03-04T16:32:52.482655+08:00",
          "dealBy": null
        },
        {
          "id": 2,
          "createdAt": "2022-03-04T15:19:13.053399+08:00",
          "updatedAt": "2022-03-04T16:34:32.080536+08:00",
          "ideaId": {
            "memberId": 2,
            "ideaType": "IMAGE",
            "url": "dasdad",
            "description": "素材描述21",
            "tags": [
              "apple",
              "苹果",
              "梨子"
            ],
            "reviewStatus": "REJECT",
            "blacklistStatus": "NORMAL",
            "price": null,
            "originCreator": "cacaca",
            "originName": "dsadasd",
            "cc": "CC0",
            "isFree": true
          },
          "reason": "Test",
          "materials": [
            ""
          ],
          "dealStatus": "REJECT",
          "dealResult": "test",
          "dealAt": "2022-03-04T16:34:32.07147+08:00",
          "dealBy": null
        }
      ],
      "total": 2
    }
  }
}
```

### 获取素材申诉
```graphql
query test{
  ideaAppeal(id:1){
    id
      createdAt
      updatedAt
      ideaId{
        memberId
        ideaType
        url
        description
        tags
        reviewStatus
        blacklistStatus
        price
        originCreator
        originName
        cc
        isFree
      }
      reason
      materials
      dealStatus
      dealResult
      dealAt
      dealBy{
        id
        Role{
          id
          name
          code
        }
        name
        username
      }
  }
}
```
```json
{
  "data": {
    "ideaAppeal": {
      "id": 1,
      "createdAt": "2022-03-04T15:19:05.78028+08:00",
      "updatedAt": "2022-03-04T16:32:52.486682+08:00",
      "ideaId": {
        "memberId": 2,
        "ideaType": "IMAGE",
        "url": "dasdad",
        "description": "素材描述21",
        "tags": [
          "apple",
          "苹果",
          "梨子"
        ],
        "reviewStatus": "REJECT",
        "blacklistStatus": "NORMAL",
        "price": null,
        "originCreator": "cacaca",
        "originName": "dsadasd",
        "cc": "CC0",
        "isFree": true
      },
      "reason": "Test",
      "materials": [
        ""
      ],
      "dealStatus": "DEAL",
      "dealResult": "test",
      "dealAt": "2022-03-04T16:32:52.482655+08:00",
      "dealBy": null
    }
  }
}
```

## 素材举报

### 通过素材举报
```graphql
mutation test($data:PassIdeaTipOffInput!){
  passIdeaTipOff(data:$data)
}
```
```json
{
  "data": {
  	"id": 1,
    "dealResult": "tst"
  }
}
```
```json
{
  "data": {
    "passIdeaTipOff": true
  }
}
```

### 拒绝素材举报
```graphql
mutation test($data:RejectIdeaTipOffInput!){
  rejectIdeaTipOff(data:$data)
}
```
```json
{
  "data": {
  	"id": 2,
    "dealResult": "tst"
  }
}
```
```json
{
  "data": {
    "rejectIdeaTipOff": true
  }
}
```

### 获取素材举报
```graphql
query test($query:IdeaTipOffsInput!){
  ideaTipOffs(query:$query){
    records{
      id
      createdAt
      updatedAt
      tipOffMember{
        id
        name
        avatar
      }
      beTipOffMember{
        id
        name
        avatar
      }
      beTipOffIdea{
        id
        ideaType
        url
        name
        description
        tags
        reviewStatus
        blacklistStatus
        price
        originName
        originCreator
        cc
        isFree
      }
      reason
      materials
      dealStatus
      dealResult
      dealAt
      dealBy{
        id
        name
        username
      }
    }
    total
  }
}
```
```json
{
  "query": {
    "pageNum": 1,
    "pageSize": 10,
    "filter": {
      "tipOffMemberId": 2
    },
    "sortKey": "ID",
    "reverse": false
  }
}
```
```json
{
  "data": {
    "ideaTipOffs": {
      "records": [
        {
          "id": 1,
          "createdAt": "2022-03-04T15:17:45.406474+08:00",
          "updatedAt": "2022-03-04T16:45:24.296626+08:00",
          "tipOffMember": {
            "id": 2,
            "name": "测试",
            "avatar": null
          },
          "beTipOffMember": {
            "id": 2,
            "name": "测试",
            "avatar": null
          },
          "beTipOffIdea": {
            "id": 1,
            "ideaType": "IMAGE",
            "url": "acasca",
            "name": "sdasda",
            "description": "sdasda",
            "tags": [
              "苹果",
              "梨子",
              "西瓜",
              "香蕉"
            ],
            "reviewStatus": "IN_REVIEW",
            "blacklistStatus": "NORMAL",
            "price": null,
            "originName": "dasdasd",
            "originCreator": "dacac",
            "cc": "CC0",
            "isFree": true
          },
          "reason": "test",
          "materials": [
            ""
          ],
          "dealStatus": "DEAL",
          "dealResult": "tst",
          "dealAt": "2022-03-04T16:45:24.284112+08:00",
          "dealBy": null
        },
        {
          "id": 2,
          "createdAt": "2022-03-04T15:17:51.410885+08:00",
          "updatedAt": "2022-03-04T16:46:07.968847+08:00",
          "tipOffMember": {
            "id": 2,
            "name": "测试",
            "avatar": null
          },
          "beTipOffMember": {
            "id": 2,
            "name": "测试",
            "avatar": null
          },
          "beTipOffIdea": {
            "id": 1,
            "ideaType": "IMAGE",
            "url": "acasca",
            "name": "sdasda",
            "description": "sdasda",
            "tags": [
              "苹果",
              "梨子",
              "西瓜",
              "香蕉"
            ],
            "reviewStatus": "IN_REVIEW",
            "blacklistStatus": "NORMAL",
            "price": null,
            "originName": "dasdasd",
            "originCreator": "dacac",
            "cc": "CC0",
            "isFree": true
          },
          "reason": "test",
          "materials": [
            ""
          ],
          "dealStatus": "REJECT",
          "dealResult": "tst",
          "dealAt": "2022-03-04T16:46:07.965304+08:00",
          "dealBy": null
        }
      ],
      "total": 2
    }
  }
}
```

### 获取素材举报
```graphql
query test{
  ideaTipOff(id:1){
 
      id
      createdAt
      updatedAt
      tipOffMember{
        id
        name
        avatar
      }
      beTipOffMember{
        id
        name
        avatar
      }
      beTipOffIdea{
        id
        ideaType
        url
        name
        description
        tags
        reviewStatus
        blacklistStatus
        price
        originName
        originCreator
        cc
        isFree
      }
      reason
      materials
      dealStatus
      dealResult
      dealAt
      dealBy{
        id
        name
        username
      }
    }

  
}
```
```json
{
  "data": {
    "ideaTipOff": {
      "id": 1,
      "createdAt": "2022-03-04T15:17:45.406474+08:00",
      "updatedAt": "2022-03-04T16:45:24.296626+08:00",
      "tipOffMember": {
        "id": 2,
        "name": "测试",
        "avatar": null
      },
      "beTipOffMember": {
        "id": 2,
        "name": "测试",
        "avatar": null
      },
      "beTipOffIdea": {
        "id": 1,
        "ideaType": "IMAGE",
        "url": "acasca",
        "name": "sdasda",
        "description": "sdasda",
        "tags": [
          "苹果",
          "梨子",
          "西瓜",
          "香蕉"
        ],
        "reviewStatus": "IN_REVIEW",
        "blacklistStatus": "NORMAL",
        "price": null,
        "originName": "dasdasd",
        "originCreator": "dacac",
        "cc": "CC0",
        "isFree": true
      },
      "reason": "test",
      "materials": [
        ""
      ],
      "dealStatus": "DEAL",
      "dealResult": "tst",
      "dealAt": "2022-03-04T16:45:24.284112+08:00",
      "dealBy": null
    }
  }
}
```