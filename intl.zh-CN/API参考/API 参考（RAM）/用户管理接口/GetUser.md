# GetUser {#reference_lcm_25k_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

获取用户的详细信息

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   名称：Action
-   类型：String
-   必须：是
-   描述：操作接口名，系统规定参数，取值：GetUser

**UserName**

-   名称：UserName
-   类型：String
-   必须：是
-   描述：指定用户名。例:zhangqiang
-   格式：

    ```
    ^[a-zA-Z0-9\.@\-_]+$
    ```


## 返回参数 {#section_vnl_h5k_xdb .section}

**User**

-   类型：[User](intl.zh-CN/API参考/API 参考（RAM）/数据类型/User.md)
-   描述：用户信息

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:GetUser
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

**EntityNotExist.User**

-   HTTP Status：404
-   Error Message：The user does not exist.

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=GetUser
&UserName=zhangqiang
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <GetUserResponse>
        <RequestId>2D69A58F-345C-4FDE-88E4-BF5189484043</RequestId>
        <User>
            <UserId>1227489245380721</UserId>
            <UserName>zhangqiang</UserName>
            <DisplayName>张强</DisplayName>
            <MobilePhone>86-18600008888</MobilePhone>
            <Email>zhangqiang@example.com</Email>
            <Comments>这是一位云计算工程师</Comments>
            <CreateDate>2015-01-23T12:33:18Z</CreateDate>
            <UpdateDate>2015-02-11T03:15:21Z</UpdateDate>
            <LastLoginDate>2015-01-23T12:33:18Z</LastLoginDate>
        </User>
        <UserId>1227489245380721</UserId>
    </GetUserResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "2D69A58F-345C-4FDE-88E4-BF5189484043",
        "User": {
            "UserId": "1227489245380721",
            "UserName": "zhangqiang",
            "DisplayName": "张强",
            "MobilePhone": "86-18600008888",
            "Email": "zhangqiang@example.com",
            "Comments": "这是一位云计算工程师",
            "CreateDate": "2015-01-23T12:33:18Z",
            "UpdateDate": "2015-02-11T03:15:21Z",
            "LastLoginDate": "2015-01-23T12:33:18Z"
        }
    }
    ```


