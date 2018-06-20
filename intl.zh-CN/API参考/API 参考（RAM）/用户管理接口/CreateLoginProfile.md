# CreateLoginProfile {#reference_r3t_lwk_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

为一个RAM子用户启用Web控制台登录

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：操作接口名，系统规定参数，取值：CreateLoginProfile

**UserName**

-   类型：String
-   必须：是
-   描述：指定用户名

**Password**

-   类型：String
-   必须：是
-   描述：指定密码，密码必须符合密码强度要求。关于密码强度设置接口，请参考[GetPasswordPolicy](intl.zh-CN/API参考/API 参考（RAM）/安全设置接口/GetPasswordPolicy.md)。

**PasswordResetRequired**

-   类型：Boolean
-   必须：否
-   默认：False
-   描述：指定用户在登录时是否需要修改密码；

**MFABindRequired**

-   类型：Boolean
-   必须：否
-   默认：False
-   描述：指定用户在下次登录时是否必须绑定多因素认证器

## 返回参数 {#section_vnl_h5k_xdb .section}

**LoginProfile**

-   类型：[LoginProfile](intl.zh-CN/API参考/API 参考（RAM）/数据类型/LoginProfile.md)
-   描述：登陆配置信息

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:CreateLoginProfile
```

**Resource**

```
acs:ram:*:${AccountId}:user/${UserName}
```

## 错误信息 {#section_wyy_rll_xdb .section}

**InvalidParameter.UserName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - “UserName” contains invalid chars.

**InvalidParameter.UserName.Length**

-   HTTP Status：400
-   Error Message：The parameter - “UserName” beyond the length limit.

**InvalidParameter.Password.TooWeak**

-   HTTP Status：400
-   Error Message：The parameter - “Password” is not compliant with the password policy.

**EntityNotExist.User**

-   HTTP Status：404
-   Error Message：The user does not exist.

**EntityAlreadyExists.User.LoginProfile**

-   HTTP Status：409
-   Error Message：The user login profile does already EXIST.

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=CreateLoginProfile
&UserName=zhangqiang
&Password=mypassword
&PasswordResetRequired=true
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <CreateLoginProfile>
        <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
        <LoginProfile>
            <UserName>zhangqiang</UserName>
            <PasswordResetRequired>true</PasswordResetRequired>
            <MFABindRequired>true</MFABindRequired>
            <CreateDate>2015-01-23T12:33:18Z</CreateDate>
        </LoginProfile>
    </CreateLoginProfile>
    ```

-   JSON格式

    ```
    {
        "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368",
        "LoginProfile": {
            "UserName": "zhangqiang",
            "PasswordResetRequired": true,
            "MFABindRequired": true,
            "CreateDate": "2015-01-23T12:33:18Z"
        }
    }
    ```


