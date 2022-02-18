# 会员/设计师/商家

## 获取注册验证码
- sendCaptcha(req:SendCaptchaReq!):SendCaptchaResp!

```
query test($req:SendCaptchaReq!){
    sendCaptcha(req:$req){
        status
        captchaId
    }    
}
```  

```
{
  "req": {"phone": "15546208763"}
}
```

```
{
  "data": {
    "sendCaptcha": {
      "status": true,
      "captchaId": "414720682948132864"
    }
  }
}
```

## 获取登录验证码
- loginCaptcha:LoginCaptcha

```
query test{
   loginCaptcha{
    captcha_id
    data
  }
}
```

```
{
  "data": {
    "loginCaptcha": {
      "captcha_id": "FYje2n7jkNMB4c8DUOGK",
      "data": "data:image/png;base64,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"
    }
  }
}
```

## 注册
- createAccount(req:CreateAccountReq!):Boolean!

```
mutation test($req:CreateAccountReq!){
  createAccount(req:$req)
}
```

```
{
  "req": {
    "phone": "15546208763",
    "captchaId": "414720682948132864",
    "captcha": "7201600",
    "password": "123456",
    "nickname": "testUser"
  }
}
```

```
{
  "data": {
    "createAccount": true
  }
}
```

## 账号密码登录
- passwordLogin(req:PasswordLoginReq!):LoginInfo!

```
mutation test($req:PasswordLoginReq!){
  passwordLogin(req:$req){
    token
    refreshToken
  }
}
```
```
{
  "req": {
    "phone": "15546208763",
    "password": "123456",
    "captchaId": "YQ8Tvk4uKsEarUE4vmsn",
    "captcha": "objr"
  }
}
```
```
{
  "data": {
    "passwordLogin": {
      "token": "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE2NDUxNTc3NTAsImlhdCI6MTY0NTE1MDU1MCwiaXNzIjoieGQtZGVzaWduIiwiSUQiOjUsIlJvbGVJZCI6bnVsbCwiVXNlcm5hbWUiOiIiLCJOYW1lIjoidGVzdFVzZXIiLCJEZXNpZ25lcklkIjpudWxsLCJNZXJjaGFudElkIjpudWxsLCJQbGF0Rm9ybSI6Mn0.SY9QR-LDS0RipGZ63-68K6RIFpz4ZEJHOwp10YmcVIJZpDJDGeCHh1P2U72deGzdIKr9Z-J1VgRJjymkVyoMC16QKB07Plq8ySlh5FMf7O-DaNe9_hNS5XT-CkefEBrbO8BAqBTqY5A87oXXS172KMZZ1GQC-mtGHfrYPbYwcrE",
      "refreshToken": "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE2NDU2Njg5NTAsImlhdCI6MTY0NTE1MDU1MCwiaXNzIjoieGQtZGVzaWduIiwiSUQiOjV9.IwYgxC_5Fhd6Rhyde94BF6JO_wVJgeLP_Is1FtdMHJaPn_r0BGuZom2swf7d_HwhHjw6bCejFZdDNHO_ltvTG1XiCKx8u1WT2IvA_uIk5fKWFFgICJtF1cbEIoFQTeRrgHLOSFPzSm4AgVOKMnH7UKp65CgB_ePwivt_0Nklaeg"
    }
  }
}
```

## 手机验证码登录
- captchaLogin(req:CaptchaLoginReq!):LoginInfo!

```
mutation test($req:CaptchaLoginReq!){
  captchaLogin(req:$req){
    token
    refreshToken
  }
}
```

```
{
  "req": {
    "phone": "15546208763",
    "captchaId": "414728228476678144",
    "captcha": "7755855"
  }
}
```

```
{
  "data": {
    "captchaLogin": {
      "token": "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE2NDUxNTgxMjIsImlhdCI6MTY0NTE1MDkyMiwiaXNzIjoieGQtZGVzaWduIiwiSUQiOjUsIlJvbGVJZCI6bnVsbCwiVXNlcm5hbWUiOiIiLCJOYW1lIjoidGVzdFVzZXIiLCJEZXNpZ25lcklkIjpudWxsLCJNZXJjaGFudElkIjpudWxsLCJQbGF0Rm9ybSI6Mn0.WfPZ1FH1qhn6cV8RBl_MH3d3SVnBLF3JbX88u83x2t8SyZoTWHnD5-yUeDceOscY3dT252xsKNzUarcu3Lz6cRrBB-VivbLoaz3tqCkBTNQPB88iCfmotswp5xMLlyz31yyd4MKeFy4nG6SL1UrW_t5FwgOrB7v3Dn_x1NWuBJ8",
      "refreshToken": "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE2NDU2NjkzMjIsImlhdCI6MTY0NTE1MDkyMiwiaXNzIjoieGQtZGVzaWduIiwiSUQiOjV9.CY-XOiqEiexo_y7VdXltK9iI56XVyLQppDWIYYXF0eqjp8IaqBf1c0dUcZZkn0uRtYrU0ysntrP5XTRGCVMSqFjEKAARuz856vmnknu0hZ0-vy_qGzR8jfvnHM5H_yQ_d6lJMnbzcqFlgo0KXASU194nV3GpPQPbDceencz0cbY"
    }
  }
}
```

## 登出
- accountLogout:Boolean!

```
mutation test{
 accountLogout
}
```

```
{
  "Authorization" : "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE2NDUxNTgxMjIsImlhdCI6MTY0NTE1MDkyMiwiaXNzIjoieGQtZGVzaWduIiwiSUQiOjUsIlJvbGVJZCI6bnVsbCwiVXNlcm5hbWUiOiIiLCJOYW1lIjoidGVzdFVzZXIiLCJEZXNpZ25lcklkIjpudWxsLCJNZXJjaGFudElkIjpudWxsLCJQbGF0Rm9ybSI6Mn0.WfPZ1FH1qhn6cV8RBl_MH3d3SVnBLF3JbX88u83x2t8SyZoTWHnD5-yUeDceOscY3dT252xsKNzUarcu3Lz6cRrBB-VivbLoaz3tqCkBTNQPB88iCfmotswp5xMLlyz31yyd4MKeFy4nG6SL1UrW_t5FwgOrB7v3Dn_x1NWuBJ8"
}
```

```
{
  "data": {
    "accountLogout": true
  }
}
```