---
title: Frequently-asked questions
layout: page-default
---




## 1: System

### Error codes

{: .table}
| error_code (int) | Message(string) | URI | 备注 |
| ---- | ---- | ---- | ---- |
| 0 | Successful | system.success |   |
| 200 | OK | system.success |   |
| 403 | Unauthorized | system.exception  |   |
| 404 | Not found | system.exception |   |
| 100001 | Internal error | system.common |   |
| 100002 | Unknown error | system.common |   |
| 100003 | Database error | system.common |   |
| 100004 | Validation failed | system.common |   |
| 100005 | Mail sending failed | system.common |   |

## 2: API

### 2.0 API Common

{: .table}
| error_code (int) | Message(string) | URI | 备注 |
| :-: | :-: | :-: | :-: |
| 200001 | POST method required | api.common  | |
| 200002 | Invalid captcha | api.common  | |

### 2.1 Oauth

#### 2.1.1 authorize

OAuth2.0 authorize api

###### Usage

**url:** /api/Oauth/authorize

**method:** GET

{: .table}
| Parameter | Type | REQUIRED | Remarks |
| - | - | - | - |
| response_type | string | true | json OR code |
| client_id | string | true | 申请应用时分配的AppKey |
| redirect_uri  | string | true | 授权回调地址，站外应用需与设置的回调地址一致，站内应用需填写canvas page的地址 |
| scope | string | false | 申请scope权限所需参数，可一次申请多个scope权限，用逗号分隔 |
| state | string | false | 用于保持请求和回调的状态，在回调时，会在Query Parameter中回传该参数。开发者可以用这个参数验证请求有效性，也可以记录用户请求授权页前的位置。这个参数可用于防止跨站请求伪造（CSRF）攻击 |

###### Error codes

{: .table}
| error_code (int) | Message(string) | URI | 备注 |
| :-: | :-: | :-: | :-: |
| 201101 | redirect_uri and client_id are required | api.Oauth.authorize  | |
| 201102 | Invalid response_type | api.Oauth.authorize  | |
| 201103 | Invalid clientid | api.Oauth.authorize  | |
| 201104 | redirect_uri and client_id are not matched | api.Oauth.authorize  | |
| 201105 | Authorization code required | api.Oauth.authorize  | |

###### Example

> 
> 请求
> https://www.upare.com/apis/Oauth/authorize/?client_id=123050457758183&redirect_uri=http://www.example.com/response&response_type=code
> 
> 同意授权后会重定向
> http://www.example.com/response&code=CODE
> 
###### Return

```json
{"error_code":0,"api_uri":"apis/Oauth/authorize","message":"Successful","authorization_code":"a7cbae5f75ea7514ed963182d8ae43f71dcb1e88"}
```

> **authorization_code** (string): 用于提交到access_token接口的code

#### 2.1.2 access token

###### Usage:

**url:** /api/Oauth/accessToken

**method:** POST

{: .table}
| Parameter | Type | REQUIRED | Remarks |
| - | - | - | - |
| client_id | string | true | 申请应用时分配的AppKey |
| client_secret | string | true | 申请应用时分配的AppSecret |
| grant_type | string | true | 请求的类型，填写authorization_code/refresh_token/password |
| redirect_uri | string | true | 回调地址，需需与注册应用里的回调地址一致 |
| code | string | false | grant_type为authorization_code时，调用/apis/Oauth/authorize获得的code值 |
| refresh_token | string | false | grant_type为refresh_token时，通过授权得到的refhresh_token刷新access_token |
| username | string | false | grant_type为password时，系统用户名 |
| password | string | false | grant_type为password时，系统密码 |

###### Error codes

{: .table}
| error_code (int) | Message(string) | URI | 备注 |
| :-: | :-: | :-: | :-: |
| 201201 | Invalid access_token | api.Oauth.accessToken  | |
| 201202 | access_token is required | api.Oauth.accessToken  | |
| 201203 | access_token expires or does not exist | api.Oauth.accessToken  | |
| 201204 | API requests out of rate limit | api.Oauth.accessToken  | |
| 201205 | client_id client_secret grant_type redirect_uri are not matched | api.Oauth.accessToken  | |
| 201206 | Api permission denied | api.Oauth.accessToken  | |
| 201207 | Cache access_token failed | api.Oauth.accessToken  | |
| 201208 | client_id client_secret are not matched | api.Oauth.accessToken  | |
| 201209 | Invalid refresh_token | api.Oauth.accessToken  | |
| 201210 | client_id is required | api.Oauth.accessToken  | |
| 201211 | client_secret is required | api.Oauth.accessToken  | |
| 201212 | Access username and password are required | api.Oauth.accessToken  | |
| 201213 | Invalid client_id | api.Oauth.accessToken  | |
| 201214 | client_id and username are not matched | api.Oauth.accessToken  | |
| 201215 | Invalid authorization code | api.Oauth.accessToken  | |
| 201216 | Invalid grant_type | api.Oauth.accessToken  | |


###### Return

 ```json
 {"error_code":0,"api_uri":"apis/Oauth/accessToken","access_token": "ACCESS_TOKEN","refresh_token": "REFRESH_TOKEN","expires_in": 1234,"remind_in":3600,"uid":12341234}
 ```

>  **access_token** (string): 用户授权的唯一票据，用于调用开放接口，同时也是第三方应用验证用户登录的唯一票据，第三方应用应该用该票据和自己应用内的用户建立唯一影射关系，来识别登录状态，不能使用本返回值里的UID字段来做登录识别。
>
>  **refresh_token** (string): grant_type为refresh_token时可通过refresh_token获得access_token。
>
>  **expires_in** (int): access_token的生命周期，单位是秒数。

#### 2.1.3 access token delete

###### Usage:

**url:** /api/Oauth/delete

**method:** POST

{: .table}
| Parameter | Type | REQUIRED | Remarks |
| - | - | - | - |
| 201301 | Failed to delete access_token | api.Oauth.delete  | |

#### 2.1.4 access token revoke

###### Usage:

**url:** /api/Oauth/revoke

**method:** POST

{: .table}
| Parameter | Type | REQUIRED | Remarks |
| - | - | - | - |
| 201401 | Failed to revoke access_token | api.Oauth.revoke  | |

### 2.2 User

#### 2.2.0 User common

{: .table}
| error_code (int) | Message(string) | URI | 备注 |
| :-: | :-: | :-: | :-: |
| 202001 | Account does not exist | api.User.common  | |
| 202002 | The username already exists | api.User.common  | |
| 202003 | The email already exists | api.User.common  | |
| 202004 | The phone number already exists | api.User.common  | |
| 202005 | The Nick name already exists | api.User.common  | |
| 202006 | Verification code validation failed | api.User.common  | |
| 202007 | The sending interval of verification code is %d seconds | api.User.common  | |

#### 2.2.1 User login

###### Usage:

**url:** /api/User/login

**method:** POST

{: .table}
| Parameter | Type | REQUIRED | Remarks |
| - | - | - | - |
| username | string | true | 用户名 |
| password | string | true | 密码 |
| captcha | string | true | /api/Image/captcha 接口产生的验证码 |
| remember | boolean | false | 是否永久登录 |


###### Error codes

{: .table}
| error_code (int) | Message(string) | URI | 备注 |
| :-: | :-: | :-: | :-: |
| 202101 | Not logged in yet | api.User.login  | |
| 202102 | Username and password are required | api.User.login  | |
| 202103 | Incorrect password | api.User.login  | |

#### 2.2.2 User register

###### Usage:

**url:** /api/User/register

**method:** POST

{: .table}
| Parameter | Type | REQUIRED | Remarks |
| - | - | - | - |
| username | string | true | 用户名 |
| password | string | true | 密码 |
| email | string | true | 邮箱 |


###### Error codes

{: .table}
| error_code (int) | Message(string) | URI | 备注 |
| :-: | :-: | :-: | :-: |
| 202201 | Failed to send verification code | api.User.register  | |
| 202202 | Failed to register | api.User.register  | |


#### 2.2.3 User settings

##### 2.2.3.1 Set avatar

###### Usage:

**url:** /api/User/setAvatar

**method:** POST

{: .table}
| Parameter | Type | REQUIRED | Remarks |
| - | - | - | - |
| response_type | string | true | json OR code |
| avatar | file | true | 头像 |


##### 2.2.3.2 Set user basic information

###### Usage:

**url:** /api/User/modifyBasicInfo

**method:** POST

{: .table}
| Parameter | Type | REQUIRED | Remarks |
| - | - | - | - |
| newpassword | string | false | 新密码 |
| confirm | string | relevance | 新密码确认,输入密码则为必填 |
| nickname | string | false | 昵称 |
| email | string | false | email |
| phone | string | false | phone |
| captcha | string | true | /api/Image/captcha 接口产生的验证码 |


##### 2.2.3.3 Set user detail information

###### Usage:

**url:** /api/User/modifyDetailInfo

**method:** POST

{: .table}
| Parameter | Type | REQUIRED | Remarks |
| - | - | - | - |
| realname | string | false | 真实姓名 |
| idcard | string | false | 身份证号 |
| address | string | false | 地址 |
| gender | string | false | 性别 |
| nation | string | false | 民族 |
| postalcode | string | false | 邮编 |
| departmentcode | string | false | 部门编号 |
| majorcode | string | false | 专业编号 |
| leader | string | false | 领导姓名 |


##### 2.2.3.4 Set sns unbind

###### Usage:

**url:** /api/User/unbind

**method:** POST

{: .table}
| Parameter | Type | REQUIRED | Remarks |
| - | - | - | - |
| channel | string | false | 社会化登录的频道名称，如weibo,qq |

###### Error codes

{: .table}
| error_code (int) | Message(string) | URI | 备注 |
| :-: | :-: | :-: | :-: |
| 202301 | Fail to upload avatar | api.User.setting  | |
| 202302 | Fail to unbind SNS account | api.User.setting  | |
| 202303 | Failed to update user information | api.User.setting  | |
| 202304 | The old and new passwords are the same | api.User.setting  | |


#### 2.2.4 User SNS register

###### Usage:

Register a uid to bind the SNS account. if type=reg register a new user else if type=log bind a exist uid

**url:** /api/User/snsreg

**method:** POST

{: .table}
| Parameter | Type | REQUIRED | Remarks |
| - | - | - | - |
| username | string | true | 用户名 |
| password | string | true | 密码 |
| confirm | string | true | 确认密码 |
| email | string | true | 邮箱 |
| type | string | true | reg/log |

#### 2.2.5 Validate unique username

###### Usage:

**url:** /api/User/validateUniqueUsername

**method:** POST

{: .table}
| Parameter | Type | REQUIRED | Remarks |
| - | - | - | - |
| response_type | string | true | json OR code |
| username | string | true | 用户名 |

###### Error codes

{: .table}
| error_code (int) | Message(string) | URI | 备注 |
| :-: | :-: | :-: | :-: |
| 202002 | The username already registered | api.User.common  | |

#### 2.2.6 Validate unique email

###### Usage:

**url:** /api/User/validateUniqueEmail

**method:** POST

{: .table}
| Parameter | Type | REQUIRED | Remarks |
| - | - | - | - |
| email | string | true | email |

###### Error codes

{: .table}
| error_code (int) | Message(string) | URI | 备注 |
| :-: | :-: | :-: | :-: |
| 202003 | The email already exists | api.User.common  | |


#### 2.2.7 Send email or mobile verification code

###### Usage:

**url:** /api/User/sendcode

**method:** POST

{: .table}
| Parameter | Type | REQUIRED | Remarks |
| - | - | - | - |
| medium | string | false | 邮箱或手机号码 |

###### Error codes

{: .table}
| error_code (int) | Message(string) | URI | 备注 |
| :-: | :-: | :-: | :-: |
| 202007 | The sending interval of verification code is %d seconds | api.User.common  | |
| 202101 | Not logged in yet | api.User.login  | |


#### 2.2.8 Validate communication code

###### Usage:

**url:** /api/User/validateCommunicationCode

**method:** POST

{: .table}
| Parameter | Type | REQUIRED | Remarks |
| - | - | - | - |
| code | int | true | 邮箱或手机验证码 |
| medium | string | false | 邮箱或手机号码 |

#### 2.2.9 User messages

###### Usage:

If id=null list all the messages else read the message of the id

**url:** /api/User/message

**method:** POST

{: .table}
| Parameter | Type | REQUIRED | Remarks |
| - | - | - | - |
| id | int | false | 消息id |

###### Error codes

{: .table}
| error_code (int) | Message(string) | URI | 备注 |
| :-: | :-: | :-: | :-: |
| 202006 | Medium code validation failed | api.User.common  | |

### 2.3 Calendar

#### 2.3.1 Calendar events

{: .table}
| error_code (int) | Message(string) | URI | 备注 |
| :-: | :-: | :-: | :-: |
| 203101 | No to-do events | api.Calendar.events  | |

#### 2.3.2 Calendar add event

{: .table}
| error_code (int) | Message(string) | URI | 备注 |
| :-: | :-: | :-: | :-: |
| 203201 | Fail to add a event | api.Calendar.add  | |

#### 2.3.3 Calendar update event

{: .table}
| error_code (int) | Message(string) | URI | 备注 |
| :-: | :-: | :-: | :-: |
| 203301 | Event id not specified | api.Calendar.update  | |


### 2.4 Intercourse

#### 2.4.1 Friends

##### 2.4.1.1 List friends

###### Usage:

Get friends of logged uid

**url:** /api/User/friends

**method:** POST


##### 2.4.1.2 Make a friend

###### Usage:

Become friend to the uid input

**url:** /api/User/friendmake

**method:** POST

{: .table}
| Parameter | Type | REQUIRED | Remarks |
| - | - | - | - |
| fid | int | true | 朋友id |


##### 2.4.1.3 Delete a friend

###### Usage:

Remove friend to the uid input

**url:** /api/User/frienddel

**method:** POST

{: .table}
| Parameter | Type | REQUIRED | Remarks |
| - | - | - | - |
| fid | int | true | 朋友id |

##### 2.4.1.4 Friends recommend

###### Usage:

Recommend friends for logged user

**url:** /api/User/friendsrecommend

**method:** POST


###### Error codes

{: .table}
| error_code (int) | Message(string) | URI | 备注 |
| :-: | :-: | :-: | :-: |
| 204101 | No friends found | api.Intercourse.friend  | |
| 204102 | Failed to make friends | api.Intercourse.friend  | |
| 204103 | Failed to delete a friend | api.Intercourse.friend  | |
| 204104 | Failed to notify your friend | api.Intercourse.friend  | |


### 2.5 Image

#### 2.5.1 Captcha

###### Usage:

**url:** /api/Image/captcha

**method:** GET/POST

{: .table}
| Parameter | Type | REQUIRED | Remarks |
| - | - | - | - |
| type | string | false | png/jpg/bmp |
| id | string | false | Captcha id for different scenarios  |




#### 2.5.2 Captcha

###### Usage:

**url:** /api/Image/captchaVerify

**method:** GET/POST

{: .table}
| Parameter | Type | REQUIRED | Remarks |
| - | - | - | - |
| captcha | string | false | Captcha |
| id | string | false | Captcha id for different scenarios |
| flush | string | false | Default is yes. if yes generate new code after each verification |

###### Error codes

{: .table}
| error_code (int) | Message(string) | URI | 备注 |
| :-: | :-: | :-: | :-: |
| 200002 | Captcha verification failed | api.common  | |


#### 2.5.3 Encrypt a picture

###### Usage:

**url:** /api/Image/disorder

**method:** GET/POST

{: .table}
| Parameter | Type | REQUIRED | Remarks |
| - | - | - | - |
