# DeleteUser {#reference_dbc_bvk_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

删除一个RAM用户

删除用户前，需要保证用户不拥有任何授权策略\(Policy\)，并且不属于任何用户组。

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   名称：Action
-   类型：String
-   必须：是
-   描述：系统规定参数，取值：DeleteUser

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

只有公共返回参数，详见[公共参数](intl.zh-CN/API参考/API 参考（RAM）/调用方式/公共参数.md)

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:DeleteUser
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

**DeleteConflict.User.Group**

-   HTTP Status：409
-   Error Message：The user CAN NOT be in any group while deleting the user.

**DeleteConflict.User.AccessKey**

-   HTTP Status：409
-   Error Message：The user CAN NOT has any access key while deleting the user.

**DeleteConflict.User.LoginProfile**

-   HTTP Status：409
-   Error Message：The user CAN NOT has any login profile while deleting the user.

**DeleteConflict.User.MFADevice**

-   HTTP Status：409
-   Error Message：The user CAN NOT has any mfa device while deleting the user.

**DeleteConflict.User.Policy**

-   HTTP Status：409
-   Error Message：The user CAN NOT has any attached policy while deleting the user.

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=DeleteUser
&UserName=zhangqiang
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <DeleteUserResponse>
        <RequestId>1C488B66-B819-4D14-8711-C4EAAA13AC01</RequestId>
    </DeleteUserResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "1C488B66-B819-4D14-8711-C4EAAA13AC01"
    }
    ```


