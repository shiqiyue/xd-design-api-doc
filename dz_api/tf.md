# 举报申诉

## 举报素材
```graphql
mutation test($req:AddIdeaTipOffReq!){
  addIdeaTipOff(req:$req)
}
```
```json
{
  "req": {
    "beTipOffMember": 2,
    "beTipOffIdea": 3,
    "reason": "test",
    "materials": ["test"]
  }
}
```
```json
{
  "data": {
    "addIdeaTipOff": true
  }
}
```
## 获取素材举报
```graphql
query test($req:GetIdeaTipOffReq!){
    getIdeaTipOff(req:$req){
        record{
            id
            createdAt
            updatedAt
            tipOffMember{
                id
                name
            }
            beTipOffMember{
                id
                name
            }
            beTipOffIdea{
                id
                name
            }
            reason
            materials
            dealStatus
            dealResult
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
    "getIdeaTipOff": {
      "record": [
        {
          "id": 1,
          "createdAt": "2022-03-04T15:17:45.406474+08:00",
          "updatedAt": "2022-03-07T14:52:39.094611+08:00",
          "tipOffMember": {
            "id": 2,
            "name": "测试"
          },
          "beTipOffMember": {
            "id": 2,
            "name": "测试"
          },
          "beTipOffIdea": {
            "id": 1,
            "name": "sdasda"
          },
          "reason": "test",
          "materials": [
            ""
          ],
          "dealStatus": "DEAL",
          "dealResult": "jjj"
        },
        {
          "id": 2,
          "createdAt": "2022-03-04T15:17:51.410885+08:00",
          "updatedAt": "2022-03-07T14:52:24.523593+08:00",
          "tipOffMember": {
            "id": 2,
            "name": "测试"
          },
          "beTipOffMember": {
            "id": 2,
            "name": "测试"
          },
          "beTipOffIdea": {
            "id": 1,
            "name": "sdasda"
          },
          "reason": "test",
          "materials": [
            ""
          ],
          "dealStatus": "REJECT",
          "dealResult": "ccc"
        },
        {
          "id": 3,
          "createdAt": "2022-03-09T15:15:32.899782+08:00",
          "updatedAt": "2022-03-09T15:15:32.899782+08:00",
          "tipOffMember": {
            "id": 2,
            "name": "测试"
          },
          "beTipOffMember": {
            "id": 2,
            "name": "测试"
          },
          "beTipOffIdea": {
            "id": 3,
            "name": "素材1"
          },
          "reason": "test",
          "materials": [
            "test"
          ],
          "dealStatus": "NOT_DEAL",
          "dealResult": null
        }
      ],
      "total": 3
    }
  }
}
```

## 素材申诉
```graphql
mutation test($req:AddIdeaAppealReq!){
  addIdeaAppeal(req:$req)
}
```
```json
{
  "req": {
    "ideaId":  3,
    "reason": "test",
    "materials": ["test"]
  }
}
```
```json
{
  "data": {
    "addIdeaAppeal": true
  }
}
```
## 获取素材申诉
```graphql
query test($req:GetIdeaAppealReq!){
  getIdeaAppeal(req:$req){
    record{
      id
      createdAt
      updatedAt
      ideaId{
        id
        name
      }
      reason
      materials
      dealStatus
      dealResult
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
    "getIdeaAppeal": {
      "record": [
        {
          "id": 1,
          "createdAt": "2022-03-04T15:19:05.78028+08:00",
          "updatedAt": "2022-03-04T16:32:52.486682+08:00",
          "ideaId": {
            "id": 2,
            "name": "素材1"
          },
          "reason": "Test",
          "materials": [
            ""
          ],
          "dealStatus": "DEAL",
          "dealResult": "test"
        },
        {
          "id": 2,
          "createdAt": "2022-03-04T15:19:13.053399+08:00",
          "updatedAt": "2022-03-04T16:34:32.080536+08:00",
          "ideaId": {
            "id": 2,
            "name": "素材1"
          },
          "reason": "Test",
          "materials": [
            ""
          ],
          "dealStatus": "REJECT",
          "dealResult": "test"
        },
        {
          "id": 3,
          "createdAt": "2022-03-09T15:17:27.552513+08:00",
          "updatedAt": "2022-03-09T15:17:27.552513+08:00",
          "ideaId": {
            "id": 3,
            "name": "素材1"
          },
          "reason": "test",
          "materials": [
            "test"
          ],
          "dealStatus": "NOT_DEAL",
          "dealResult": null
        }
      ],
      "total": 3
    }
  }
}
```

## 举报设计师
```graphql
mutation test($req:AddDesignerTipOffReq!){
    addDesignerTipOff(req:$req)
}
```
```json
{
  "req": {
    "beTipOffMember": 2,
    "reason": "test",
    "materials": ["test"]
  }
}
```
```json
{
  "data": {
    "addDesignerTipOff": true
  }
}
```
## 获取设计师举报
```graphql
query test($req:GetDesignerTipOffReq!){
  getDesignerTipOff(req:$req){
    record{
      id
      createdAt
      updatedAt
      tipOffMember{
        id
        name
      }
      beTipOffMember{
        id
        name
      }
      reason
      materials
      dealStatus
      dealResult
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
    "getDesignerTipOff": {
      "record": [
        {
          "id": 1,
          "createdAt": "2022-03-04T15:12:01.330313+08:00",
          "updatedAt": "2022-03-06T17:41:56.556197+08:00",
          "tipOffMember": {
            "id": 2,
            "name": "测试"
          },
          "beTipOffMember": {
            "id": 2,
            "name": "测试"
          },
          "reason": "Test",
          "materials": [
            "test"
          ],
          "dealStatus": "DEAL",
          "dealResult": "gg"
        },
        {
          "id": 2,
          "createdAt": "2022-03-04T15:12:08.241003+08:00",
          "updatedAt": "2022-03-06T17:41:30.394548+08:00",
          "tipOffMember": {
            "id": 2,
            "name": "测试"
          },
          "beTipOffMember": {
            "id": 2,
            "name": "测试"
          },
          "reason": "Test",
          "materials": [
            "test"
          ],
          "dealStatus": "REJECT",
          "dealResult": "xv"
        },
        {
          "id": 3,
          "createdAt": "2022-03-09T15:21:09.714741+08:00",
          "updatedAt": "2022-03-09T15:21:09.714741+08:00",
          "tipOffMember": {
            "id": 2,
            "name": "测试"
          },
          "beTipOffMember": {
            "id": 2,
            "name": "测试"
          },
          "reason": "test",
          "materials": [
            "test"
          ],
          "dealStatus": "NOT_DEAL",
          "dealResult": null
        }
      ],
      "total": 3
    }
  }
}
```

## 设计师申诉
```graphql
mutation test($req:AddDesignerAppealReq!){
  addDesignerAppeal(req:$req)
}
```
```json
{
  "req": {
    "reason": "test",
    "materials": ["test"]
  }
}
```
```json
{
  "data": {
    "addDesignerAppeal": true
  }
}
```

## 获取设计师申诉
```graphql
query test($req:GetDesignerAppealReq!){
    getDesignerAppeal(req:$req){
        record{
            id
            createdAt
            updatedAt
            designerId{
                id
                memberId{
                    id
                    name
                }
            }
            reason
            materials
            dealStatus
            dealResult
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
    "getDesignerAppeal": {
      "record": [
        {
          "id": 1,
          "createdAt": "2022-03-04T15:01:54.42354+08:00",
          "updatedAt": "2022-03-07T15:35:49.333105+08:00",
          "designerId": {
            "id": 1,
            "memberId": {
              "id": 2,
              "name": "测试"
            }
          },
          "reason": "test",
          "materials": [
            "",
            ""
          ],
          "dealStatus": "DEAL",
          "dealResult": "ggg"
        },
        {
          "id": 2,
          "createdAt": "2022-03-04T15:02:46.632133+08:00",
          "updatedAt": "2022-03-07T15:35:59.225533+08:00",
          "designerId": {
            "id": 1,
            "memberId": {
              "id": 2,
              "name": "测试"
            }
          },
          "reason": "test",
          "materials": [
            "",
            ""
          ],
          "dealStatus": "REJECT",
          "dealResult": "vvv"
        },
        {
          "id": 3,
          "createdAt": "2022-03-09T15:20:11.290774+08:00",
          "updatedAt": "2022-03-09T15:20:11.290774+08:00",
          "designerId": {
            "id": 1,
            "memberId": {
              "id": 2,
              "name": "测试"
            }
          },
          "reason": "test",
          "materials": [
            "test"
          ],
          "dealStatus": "NOT_DEAL",
          "dealResult": null
        }
      ],
      "total": 3
    }
  }
}
```