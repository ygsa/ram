# AddUserToGroup {#reference_y14_shn_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

将子用户添加到指定的用户组

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：操作名称，取值：

    ```
    AddUserToGroup
    ```


**UserName**

-   类型：String
-   必须：是
-   描述：用户名称

**GroupName**

-   类型：String
-   必须：是
-   描述：组名称

## 返回参数 { .section}

　只有公共返回参数，详见[公共参数](intl.zh-CN/API参考/API 参考（RAM）/调用方式/公共参数.md)

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:AddUserToGroup
```

**Resource**

```
acs:ram:*:${AccountId}:user/${UserName}
```

```
acs:ram:*:${AccountId}:group/${GroupName}
```

## 错误信息 {#section_jyq_nhn_xdb .section}

**InvalidParameter.UserName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - "UserName" contains invalid chars.

**InvalidParameter.UserName.Length**

-   HTTP Status：400
-   Error Message：The parameter - "UserName" beyond the length limit.

**InvalidParameter.GroupName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - "GroupName" contains invalid chars.

**InvalidParameter.GroupName.Length**

-   HTTP Status：400
-   Error Message：The parameter - "GroupName" beyond the length limit.

**EntityNotExist.User**

-   HTTP Status：404
-   Error Message：The user does not exist.

**EntityNotExist.Group**

-   HTTP Status：404
-   Error Message：The group does not exist.

**EntityAlreadyExists.User.Group**

-   HTTP Status：409
-   Error Message：The user has already joined the group.

**LimitExceeded.User.Group**

-   HTTP Status：409
-   Error Message：The count of groups the target user joined beyond the current limits.

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=AddUserToGroup
&UserName=zhangqiang
&GroupName=Dev-Team
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <AddUserToGroupResponse>
        <RequestId>1B968853-B423-63A6-FE1F-45E81BC2AD61</RequestId>
    </AddUserToGroupResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "1B968853-B423-63A6-FE1F-45E81BC2AD61"
    }
    ```


