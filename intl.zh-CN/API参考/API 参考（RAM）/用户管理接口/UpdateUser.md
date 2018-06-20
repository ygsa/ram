# UpdateUser {#reference_g5m_y5k_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

更新用户的基本信息

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：操作接口名，系统规定参数，取值：UpdateUser

**UserName**

-   类型：String
-   必须：是
-   描述：指定用户名
-   格式：

    ```
    ^[a-zA-Z0-9\.@\-_]+$
    ```


**NewUserName**

-   类型：String
-   必须：否
-   描述：指定新用户名
-   格式：

    ```
    ^[a-zA-Z0-9\.@\-_]+$
    ```


**NewDisplayName**

-   类型：String
-   必须：否
-   描述：指定新显示名称

**NewMobilePhone**

-   类型：String
-   必须：否
-   描述：指定RAM用户新手机号
-   格式：国际区号-号码；例如：86-18600008888

**NewEmail**

-   类型：String
-   必须：否
-   描述：指定RAM用户的新邮箱

**NewComments**

-   类型：String
-   必须：否
-   描述：指定新备注, 最大长度128个字符。

## 返回参数 {#section_vnl_h5k_xdb .section}

**User**

-   类型：[User](intl.zh-CN/API参考/API 参考（RAM）/数据类型/User.md)
-   描述：用户信息

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:UpdateUser
```

**Resource**

```
acs:ram:*:${AccountId}:user/${UserName}
```

## 错误信息 {#section_zjv_5tk_xdb .section}

**InvalidParameter.UserName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - "UserName" contains invalid chars.

**InvalidParameter.UserName.Length**

-   HTTP Status：400
-   Error Message：The parameter - "UserName" beyond the length limit.

**InvalidParameter.NewUserName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - "NewUserName" contains invalid chars.

**InvalidParameter.NewUserName.Length**

-   HTTP Status：400
-   Error Message：The parameter - "NewUserName" beyond the length limit.

**InvalidParameter.NewDisplayName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - "NewDisplayName" contains invalid chars.

**InvalidParameter.NewDisplayName.Length**

-   HTTP Status：400
-   Error Message：The parameter - "NewDisplayName" beyond the length limit.

**InvalidParameter.NewComments.Length**

-   HTTP Status：400
-   Error Message：The parameter - "NewComments" beyond the length limit.

**InvalidParameter.NewMobilePhone.Format**

-   HTTP Status：400
-   Error Message：The format of the parameter - "NewMobilePhone" is incorrect.

**InvalidParameter.NewEmail.Format**

-   HTTP Status：400
-   Error Message：The format of the parameter - "NewEmail" is incorrect.

**EntityNotExist.User**

-   HTTP Status：404
-   Error Message：The user does not exist.

**EntityAlreadyExists.User**

-   HTTP Status：409
-   Error Message：The user does already EXIST.

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=UpdateUser
&UserName=zhangqiang
&NewUserName=xiaoqiang
&NewMobilePhone=86-18600008888
&NewEmail=zhangqiang@example.com
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <CreateUserResponse>
        <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
        <User>
            <UserId>1227489245380721</UserId>
            <UserName>xiaoqiang</UserName>
            <DisplayName>张强</DisplayName>
            <MobilePhone>86-18600008888</MobilePhone>
            <Email>zhangqiang@example.com</Email>
            <Comments>这是一位云计算工程师</Comments>
            <CreateDate>2015-01-23T12:33:18Z</CreateDate>
            <UpdateDate>2015-02-11T03:15:21Z</UpdateDate>
        </User>
    </CreateUserResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368",
        "User": {
            "UserId": "1227489245380721",
            "UserName": "xiaoqiang",
            "DisplayName": "张强",
            "MobilePhone": "86-18600008888",
            "Email": "zhangqiang@example.com",
            "Comments": "这是一位云计算工程师",
            "CreateDate": "2015-01-23T12:33:18Z",
            "UpdateDate": "2015-02-11T03:15:21Z"
        }
    }
    ```


