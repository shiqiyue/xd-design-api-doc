# 版型管理

## 获取品类树
- showCategoryFamily: [CategoryWithSons!]

```
query test{
  showCategoryFamily{
    id
    name
    priority
    sons{
      id
      name
      priority
    }
  }
}
```  

```
{
}
```

```
{
    "data": {
        "showCategoryFamily": [
            {
                "id": 1,
                "name": "nan",
                "priority": 5,
                "sons": [
                    {
                        "id": 3,
                        "name": "wt",
                        "priority": 5
                    },
                    {
                        "id": 4,
                        "name": "wy",
                        "priority": 5
                    },
                    {
                        "id": 2,
                        "name": "tx",
                        "priority": 2
                    }
                ]
            },
            {
                "id": 5,
                "name": "nv",
                "priority": 5,
                "sons": [
                    {
                        "id": 8,
                        "name": "阿发",
                        "priority": 3
                    },
                    {
                        "id": 6,
                        "name": "tx",
                        "priority": 2
                    }
                ]
            }
        ]
    }
}
```

## 获取绘制方式列表
- showDrawingTypes(query: ShowDrawingTypesInput!): ShowDrawingTypesResult!

```
query test($query: ShowDrawingTypesInput!){
  showDrawingTypes(query:$query){
    total
    records{
      id
      name
      priceFactor
      describe
      extraPricePerColor
      extraDescribe
    }
  }
}
```  

```
{
  "query": {
    "pageIndex": 1,
    "pageSize": 10,
    "orderKey": "ID",
    "orderReverse": false,
    "filter": {
      "name": "s",
      "priceFactorMin": 1,
      "priceFactorMax": 3
    }
  }
}
```

```
{
    "data": {
        "showDrawingTypes": {
            "total": 1,
            "records": [
                {
                    "id": 4,
                    "name": "afsd",
                    "priceFactor": 2,
                    "describe": "fsaf",
                    "extraPricePerColor": 1,
                    "extraDescribe": "asfe"
                }
            ]
        }
    }
}
```

## 获取版型
- showModel(id: Bigint!): ModelWithAll

```
query test($id: Bigint!){
  showModel(id: $id){
    id
    name
    coding
    categoryID
    price
    views
    sizeTemplateID
    sizeArea
    sizeCrowd
    brand
    origin
    describe
    category{
      id
      name
      priority
    }
    sizeTemplate{
      id
      name
      picture
      parts{
        id
        sizeTemplateID
        name
        unit
      }
    }
    sizes{
      id
      modelID
      name
      details{
        id
        modelSizeID
        sizeTemplatePartID
        length
      }
    }
    colors{
      id
      modelID
      colorCardID
      details{
        id
        modelColorID
        view
        picture
      }
      colorCard{
        id
        colorSystemID
        name
        picture
        describe
      }
    }
    drawings{
      id
      modelID
      view
      position
      price
      x
      y
      width
      height
      describe
    }
  }
}
```  

```
{
  "id": "1"
}
```

```
{
    "data": {
        "showModel": {
            "id": 1,
            "name": "wy",
            "coding": "000001",
            "categoryID": 2,
            "price": 999,
            "views": [
                1,
                2,
                3
            ],
            "sizeTemplateID": 1,
            "sizeArea": null,
            "sizeCrowd": null,
            "brand": null,
            "origin": null,
            "describe": null,
            "category": {
                "id": 2,
                "name": "tx",
                "priority": 2
            },
            "sizeTemplate": {
                "id": 1,
                "name": "tx",
                "picture": "ASDADAEFEffefsdf",
                "parts": [
                    {
                        "id": 1,
                        "sizeTemplateID": 1,
                        "name": "yc",
                        "unit": "cm"
                    },
                    {
                        "id": 2,
                        "sizeTemplateID": 1,
                        "name": "xc",
                        "unit": "cm"
                    }
                ]
            },
            "sizes": [
                {
                    "id": 8,
                    "modelID": 1,
                    "name": "s",
                    "details": [
                        {
                            "id": 17,
                            "modelSizeID": 8,
                            "sizeTemplatePartID": 4,
                            "length": 4.9
                        },
                        {
                            "id": 18,
                            "modelSizeID": 8,
                            "sizeTemplatePartID": 6,
                            "length": 6.9
                        }
                    ]
                },
                {
                    "id": 9,
                    "modelID": 1,
                    "name": "m",
                    "details": [
                        {
                            "id": 19,
                            "modelSizeID": 9,
                            "sizeTemplatePartID": 4,
                            "length": 99.9
                        },
                        {
                            "id": 20,
                            "modelSizeID": 9,
                            "sizeTemplatePartID": 6,
                            "length": 99.9
                        }
                    ]
                },
                {
                    "id": 10,
                    "modelID": 1,
                    "name": "l",
                    "details": [
                        {
                            "id": 21,
                            "modelSizeID": 10,
                            "sizeTemplatePartID": 4,
                            "length": 99.9
                        },
                        {
                            "id": 22,
                            "modelSizeID": 10,
                            "sizeTemplatePartID": 6,
                            "length": 99.9
                        }
                    ]
                }
            ],
            "colors": [
                {
                    "id": 1,
                    "modelID": 1,
                    "colorCardID": 1,
                    "details": [
                        {
                            "id": 1,
                            "modelColorID": 1,
                            "view": 1,
                            "picture": "aa"
                        },
                        {
                            "id": 2,
                            "modelColorID": 1,
                            "view": 2,
                            "picture": "bb"
                        },
                        {
                            "id": 3,
                            "modelColorID": 1,
                            "view": 3,
                            "picture": "cc"
                        }
                    ],
                    "colorCard": {
                        "id": 1,
                        "colorSystemID": 1,
                        "name": "bs",
                        "picture": "11111111111",
                        "describe": "2222222222"
                    }
                },
                {
                    "id": 2,
                    "modelID": 1,
                    "colorCardID": 2,
                    "details": [
                        {
                            "id": 4,
                            "modelColorID": 2,
                            "view": 1,
                            "picture": "a"
                        },
                        {
                            "id": 5,
                            "modelColorID": 2,
                            "view": 2,
                            "picture": "b"
                        },
                        {
                            "id": 6,
                            "modelColorID": 2,
                            "view": 3,
                            "picture": "c"
                        }
                    ],
                    "colorCard": {
                        "id": 2,
                        "colorSystemID": 1,
                        "name": "hs",
                        "picture": "11111111111",
                        "describe": "2222222222"
                    }
                }
            ],
            "drawings": [
                {
                    "id": 1,
                    "modelID": 1,
                    "view": 1,
                    "position": 1,
                    "price": 999,
                    "x": 5,
                    "y": 5,
                    "width": 10,
                    "height": 10,
                    "describe": "bbbb"
                },
                {
                    "id": 2,
                    "modelID": 1,
                    "view": 1,
                    "position": 2,
                    "price": 999,
                    "x": 50,
                    "y": 50,
                    "width": 100,
                    "height": 100,
                    "describe": "aaaa"
                },
                {
                    "id": 3,
                    "modelID": 1,
                    "view": 2,
                    "position": 2,
                    "price": 999,
                    "x": 50,
                    "y": 50,
                    "width": 100,
                    "height": 100,
                    "describe": "aaaa"
                }
            ]
        }
    }
}
```

## 获取在售版型列表
- showModelMarkets(query: ShowModelMarketsInput!): ShowModelMarketsResult!

```
query test($query: ShowModelMarketsInput!){
  showModelMarkets(query:$query){
    total
    records{
      id
      modelID
      isOnSell
      view
      modelColorID
      modelDrawingID
      model{
        id
        name
        coding
        categoryID
        price
        views
        sizeTemplateID
        sizeArea
        sizeCrowd
        brand
        origin
        describe
      }
      modelColor{
        id
        modelID
        colorCardID
        details{
          id
          modelColorID
          view
          picture
        }
        colorCard{
          id
          colorSystemID
          name
          picture
          describe
        }
      }
    }
  }
}
```  

```
{
  "query": {
    "pageIndex": 1,
    "pageSize": 10,
    "orderKey": "ID",
    "orderReverse": false,
    "filter": {
      "modelID": 1,
      "isOnSell": true
    }
  }
}
```

```
{
    "data": {
        "showModelMarkets": {
            "total": 1,
            "records": [
                {
                    "id": 1,
                    "modelID": 1,
                    "isOnSell": true,
                    "view": 1,
                    "modelColorID": 2,
                    "modelDrawingID": 1,
                    "model": {
                        "id": 1,
                        "name": "wy",
                        "coding": "000001",
                        "categoryID": 2,
                        "price": 999,
                        "views": [
                            1,
                            2,
                            3
                        ],
                        "sizeTemplateID": 1,
                        "sizeArea": null,
                        "sizeCrowd": null,
                        "brand": null,
                        "origin": null,
                        "describe": null
                    },
                    "modelColor": {
                        "id": 2,
                        "modelID": 1,
                        "colorCardID": 2,
                        "details": [
                            {
                                "id": 4,
                                "modelColorID": 2,
                                "view": 1,
                                "picture": "a"
                            },
                            {
                                "id": 5,
                                "modelColorID": 2,
                                "view": 2,
                                "picture": "b"
                            },
                            {
                                "id": 6,
                                "modelColorID": 2,
                                "view": 3,
                                "picture": "c"
                            }
                        ],
                        "colorCard": {
                            "id": 2,
                            "colorSystemID": 1,
                            "name": "hs",
                            "picture": "11111111111",
                            "describe": "2222222222"
                        }
                    }
                }
            ]
        }
    }
}
```