# 文件服务器接口

## 服务器地址
```json
测试环境服务器地址：
http://192.168.3.132:7779
http://10.10.20.132:7779
```
## 注意实现
```json
权限还没有空值，token先不用传
```

## 上传文件
```json
方式 POST
链接 /files/{对象名}
头部 Authorization {TOKEN}

入参:
格式： multipart/form-data
file 文件

说明: 对象名格式为 文件夹/文件名
文件夹格式为  1/2/3/4 ，不能以/开头
```


## 下载文件
```json
方式 GET
链接 /files/{对象名}?token={token}
```
