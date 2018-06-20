# GetLoginProfile {#reference_vm3_xll_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

查看一个RAM用户的登录配置

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：操作接口名，系统规定参数，取值：GetLoginProfile

**UserName**

-   类型：String
-   必须：是
-   描述：指定用户名

## 返回参数 {#section_vnl_h5k_xdb .section}

**LoginProfile**

-   类型：[LoginProfile](intl.zh-CN/API参考/API 参考（RAM）/数据类型/LoginProfile.md)
-   描述：登陆配置信息

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:GetLoginProfile
```

**Resource**

```
acs:ram:*:${AccountId}:user/${UserName}
```

## 错误信息 {#section_wyy_rll_xdb .section}

**InvalidParameter.UserName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - "UserName" contains invalid chars.

**InvalidParameter.UserName.Length**

-   HTTP Status：400
-   Error Message：The parameter - "UserName" beyond the length limit.

**EntityNotExist.User**

-   HTTP Status：404
-   Error Message：The user does not exist.

**EntityNotExist.User.LoginProfile**

-   HTTP Status：404
-   Error Message：The user login profile does not exist.

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=GetLoginProfile
&UserName=zhangqiang
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <GetLoginProfile>
        <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
        <LoginProfile>
            <UserName>zhangqiang</UserName>
            <PasswordResetRequired>true</PasswordResetRequired>
            <MFABindRequired>true</MFABindRequired>
            <CreateDate>2015-01-23T12:33:18Z</CreateDate>
        </LoginProfile>
    </GetLoginProfile>
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


