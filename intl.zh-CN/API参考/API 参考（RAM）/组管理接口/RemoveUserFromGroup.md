# RemoveUserFromGroup {#reference_qv4_zhn_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

将子用户从用户组中移除

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：操作名称，取值：

    ```
    RemoveUserFromGroup
    ```


**UserName**

-   类型：String
-   必须：是
-   描述：子用户名称

**GroupName**

-   类型：String
-   必须：是
-   描述：组名称

## 返回参数 { .section}

只有公共返回参数，详见[公共参数](intl.zh-CN/API参考/API 参考（RAM）/调用方式/公共参数.md)

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:RemoveUserFromGroup
```

**Resource**

```
acs:ram:*:${AccountId}:user/${UserName}

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

**EntityNotExist.User.Group**

-   HTTP Status：404
-   Error Message：The user has not joined the group.

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=RemoveUserFromGroup
&UserName=zhangqiang
&GroupName=Dev-Team
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <RemoveUserFromGroupResponse>
        <RequestId>A07EF215-B9B3-8CB2-2899-3F9575C6E320</RequestId>
    </RemoveUserFromGroupResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "A07EF215-B9B3-8CB2-2899-3F9575C6E320"
    }
    ```


