# ListRoles {#reference_z5y_zjn_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

列出角色

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：系统规定参数，取值：ListRoles

## 返回参数 { .section}

**Roles**

-   类型：[Role](intl.zh-CN/API参考/API 参考（RAM）/数据类型/Role.md) Array
-   描述：角色名称列表

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:ListRoles
```

**Resource**

```
acs:ram:*:${AccountId}:role/*
```

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=ListRoles
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <ListRolesResponse>
        <RequestId>7B8A4E7D-6CFF-471D-84DF-195A7A241ECB</RequestId>
        <Roles>
            <Role>
                <RoleId>901234567890123</RoleId>
                <RoleName>ECSAdmin</RoleName>
                <Arn>acs:ram::1234567890123456:role/ECSAdmin</Arn>
                <Description>ECS管理角色</Description>
                <CreateDate>2015-01-23T12:33:18Z</CreateDate>
                <UpdateDate>2015-01-23T12:33:18Z</UpdateDate>
            </Role>
            <Role>
                <RoleId>901234567890456</RoleId>
                <RoleName>OSSReadonlyAccess</RoleName>
                <Arn>acs:ram::1234567890123456:role/OSSReadonlyAccess</Arn>
                <Description>OSS只读访问角色</Description>
                <CreateDate>2015-01-23T12:33:18Z</CreateDate>
                <UpdateDate>2015-01-23T12:33:18Z</UpdateDate>
            </Role>
        </Roles>
    </ListRolesResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "7B8A4E7D-6CFF-471D-84DF-195A7A241ECB",
        "Roles": {
            "Role": [
                {
                    "RoleId": "901234567890123",
                    "RoleName": "ECSAdmin",
                    "Arn": "acs:ram::1234567890123456:role/ECSAdmin",
                    "Description": "ECS管理角色",
                    "CreateDate": "2015-01-23T12:33:18Z",
                    "UpdateDate": "2015-01-23T12:33:18Z"
                },
                {
                    "RoleId": "901234567890456",
                    "RoleName": "OSSReadonlyAccess",
                    "Arn": "acs:ram::1234567890123456:role/OSSReadonlyAccess",
                    "Description": "OSS只读访问角色",
                    "CreateDate": "2015-01-23T12:33:18Z",
                    "UpdateDate": "2015-01-23T12:33:18Z"
                }
            ]
        }
    }
    ```


