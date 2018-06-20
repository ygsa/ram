# DeleteRole {#reference_bpd_l34_xdb .reference}

## 接口描述 {#section_erh_xh4_xdb .section}

删除指定的角色

## 请求参数 {#section_nps_yh4_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：系统规定参数，取值：DeleteRole

**RoleName**

-   类型：String
-   必须：是
-   描述：指定角色名称

## 返回参数 {#section_ldp_zh4_xdb .section}

只有公共返回参数，详见[公共参数](intl.zh-CN/API参考/API 参考（RAM）/调用方式/公共参数.md)

## 需要的权限 {#section_twc_134_xdb .section}

**Action**

```
ram:DeleteRole
```

**Resource**

```
acs:ram:*:${AccountId}:role/${RoleName}
```

## 错误信息 {#section_zp3_c34_xdb .section}

**InvalidParameter.RoleName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - "RoleNam" contains invalid chars.

**InvalidParameter.RoleName.Length**

-   HTTP Status：400
-   Error Message：The parameter - "RoleName" beyond the length limit.

**EntityNotExist.Role**

-   HTTP Status：404
-   Error Message：The role does not exist.

**DeleteConflict.Role.Policy**

-   HTTP Status：409
-   Error Message：The role CAN NOT has any attached policy while deleting the role.

## 请求示例 {#section_knn_d34_xdb .section}

```
https://ram.aliyuncs.com/?Action=DeleteRole
&RoleName=ECSAdmin
&<公共请求参数>
```

## 返回示例 {#section_jy3_f34_xdb .section}

-   XML格式

    ```
    <DeleteRoleResponse>
        <RequestId>898FAB24-7509-43EE-A287-086FE4C44394</RequestId>
    </DeleteRoleResponse>
    ```

-   JOSN格式

    ```
    {
        "RequestId": "898FAB24-7509-43EE-A287-086FE4C44394"
    }
    ```


