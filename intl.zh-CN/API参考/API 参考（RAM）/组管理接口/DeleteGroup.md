# DeleteGroup {#reference_gjh_khn_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

删除指定的组

-   删除组前，需要保证组不拥有任何授权策略\(Policy\)
-   删除组前，需要保证组不拥有任何用户\(User\)

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：操作名称，取值：

    ```
    DeleteGroup
    ```


**GroupName**

-   类型：String
-   必须：是
-   描述：指定组名。例:dev
-   格式：

    ```
    ^[a-zA-Z0-9\-]+$
    ```


## 返回参数 { .section}

只有公共返回参数，详见[公共参数](intl.zh-CN/API参考/API 参考（RAM）/调用方式/公共参数.md)

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:DeleteGroup
```

**Resource**

```
acs:ram:*:${AccountId}:group/${GroupName}
```

## 错误信息 {#section_jyq_nhn_xdb .section}

**InvalidParameter.GroupName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - "GroupName" contains invalid chars.

**InvalidParameter.GroupName.Length**

-   HTTP Status：400
-   Error Message：The parameter - "GroupName" beyond the length limit.

**EntityNotExist.Group**

-   HTTP Status：404
-   Error Message：The group does not exist.

**DeleteConflict.Group.User**

-   HTTP Status：409
-   Error Message：The group CAN NOT has any user member while deleting the group.

**DeleteConflict.Group.Policy**

-   HTTP Status：409
-   Error Message：The entity CAN NOT has any attached policy while deleting the group.

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=DeleteGroup
&GroupName=Dev-Team
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <DeleteGroupResponse>
        <RequestId>FCF40AB5-881C-A0F9-334C-B0AD423AA69D</RequestId>
    </DeleteGroupResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "FCF40AB5-881C-A0F9-334C-B0AD423AA69D"
    }
    ```


