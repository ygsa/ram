# UpdateRole {#reference_pnx_4jn_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

更新角色信息

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：操作接口名，系统规定参数，取值：UpdateRole

**RoleName**

-   类型：String
-   必须：是
-   描述：指定角色名，最多包含64个字符
-   格式：

    ```
    ^[a-zA-Z0-9\.@\-]+$
    ```


**NewAssumeRolePolicyDocument**

-   类型：String
-   必须：否
-   描述：指定可以扮演此角色的身份。

## 返回参数 { .section}

**Role**

-   类型：[Role](intl.zh-CN/API参考/API 参考（RAM）/数据类型/Role.md)
-   描述：角色信息

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:UpdateRole
```

**Resource**

```
acs:ram:*:${AccountId}:role/*
```

## 错误信息 {#section_jyq_nhn_xdb .section}

**InvalidParameter.RoleName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - "RoleName" contains invalid chars.

**InvalidParameter.RoleName.Length**

-   HTTP Status：400
-   Error Message：The parameter - "RoleName" beyond the length limit.

**InvalidParameter.NewAssumeRolePolicyDocument.Length**

-   HTTP Status：400
-   Error Message：The parameter - "NewAssumeRolePolicyDocument" beyond the length limit.

**EntityNotExist.Role**

-   HTTP Status：404
-   Error Message：The role does not exist.

**MalformedPolicyDocument**

-   HTTP Status：400
-   Error Message：\{The error details\}

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=UpdateRole
&RoleName=ECSAdmin
&NewAssumeRolePolicyDocument=xxxx //TODO
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <UpdateRoleResponse>
        <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
        <Role>
            <RoleId>901234567890123</RoleId>
            <RoleName>ECSAdmin</RoleName>
            <Arn>acs:ram::1234567890123456:role/ECSAdmin</Arn>
            <Description>ECS管理角色</Description>
            <AssumeRolePolicyDocument>{ "Statement": [ { "Action": "sts:AssumeRole", "Effect": "Allow", "Principal": { "RAM": "acs:ram::123456789012345678:root" } } ], "Version": "1" }</AssumeRolePolicyDocument>
            <CreateDate>2015-01-23T12:33:18Z</CreateDate>
            <UpdateDate>2015-01-23T12:33:18Z</UpdateDate>
        </Role>
    </UpdateRoleResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368",
        "Role": {
            "RoleId": "901234567890123",
            "RoleName": "ECSAdmin",
            "Arn": "acs:ram::1234567890123456:role/ECSAdmin",
            "Description": "ECS管理角色",
            "AssumeRolePolicyDocument": "{ \"Statement\": [ { \"Action\": \"sts:AssumeRole\", \"Effect\": \"Allow\", \"Principal\": { \"RAM\": \"acs:ram::123456789012345678:root\" } } ], \"Version\": \"1\" }",
            "CreateDate": "2015-01-23T12:33:18Z",
            "UpdateDate": "2015-01-23T12:33:18Z"
        }
    }
    ```


