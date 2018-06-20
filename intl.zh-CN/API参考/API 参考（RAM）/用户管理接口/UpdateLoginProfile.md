# UpdateLoginProfile {#reference_i2g_x1n_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

修改用户的登陆配置

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：操作接口名，系统规定参数，取值：UpdateLoginProfile

**UserName**

-   类型：String
-   必须：是
-   描述：指定用户名

**Password**

-   类型：String
-   必须：否
-   描述：指定密码，密码必须符合主账号的密码强度要求；

**PasswordResetRequired**

-   类型：Boolean
-   必须：否
-   描述：指定用户在登录时是否需要修改密码；

**MFABindRequired**

-   类型：Boolean
-   必须：否
-   描述：指定用户在下次登录时是否必须绑定MFA

## 返回参数 {#section_vnl_h5k_xdb .section}

**LoginProfile**

-   类型：[LoginProfile](intl.zh-CN/API参考/API 参考（RAM）/数据类型/LoginProfile.md)
-   描述：登陆配置信息

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:UpdateLoginProfile
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

**EntityNotExist.User**

-   HTTP Status：404
-   Error Message：The user does not exist.

**EntityNotExist.User.LoginProfile**

-   HTTP Status：404
-   Error Message：The user login profile does not exist.

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=UpdateLoginProfile
&UserName=zhangqiang
&Password=mypassword
&PasswordResetRequired=true
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <UpdateLoginProfile>
        <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
    </UpdateLoginProfile>
    ```

-   JSON格式

    ```
    {
        "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368"
    }
    ```


