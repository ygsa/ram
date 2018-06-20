# CreateRole {#reference_n1t_y3n_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

创建角色

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：操作接口名，系统规定参数，取值：CreateRole

**RoleName**

-   类型：String
-   必须：是
-   描述：指定角色名，最多包含64个字符
-   格式：

    ```
    ^[a-zA-Z0-9\.@\-]+$
    ```


**Description**

-   类型：String
-   必须：否
-   描述：角色描述，最大长度1024字字符

**AssumeRolePolicyDocument**

-   类型：String
-   必须：是
-   描述：一个策略文本，指定受信任的允许扮演该角色的一个或多个主体\(Principal\)，这个主体可以是RAM用户或阿里云服务。
-   样例说明：
    -   如下策略表示允许扮演该角色的受信主体为云账号\(AccountID=123456789012345678\)下被授权的RAM用户:

        ```
        {
        "Statement": [
        {
          "Action": "sts:AssumeRole",
          "Effect": "Allow",
          "Principal": {
            "RAM": [
              "acs:ram::123456789012345678:root"
            ]
          }
        }
        ],
        "Version": "1"
        }
        ```

    -   如下策略表示允许扮演该角色的受信主体为当前租户下的ECS实例（用户创建ECS实例时可以指定使用该RAM角色，实例启动后将能获得该RAM角色的STS-Token）:

        ```
        {
        "Statement": [
        {
          "Action": "sts:AssumeRole",
          "Effect": "Allow",
          "Principal": {
            "Service": [
              "ecs.aliyuncs.com"
            ]
          }
        }
        ],
        "Version": "1"
        }
        ```


## 返回参数 { .section}

**Role**

-   类型：[Role](intl.zh-CN/API参考/API 参考（RAM）/数据类型/Role.md)
-   描述：角色信息

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:CreateRole
```

**Resource**

```
acs:ram:*:${AccountId}:role/*
```

## 错误信息 {#section_jyq_nhn_xdb .section}

**InvalidParameter.RoleName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - “RoleName” contains invalid chars.

**InvalidParameter.RoleName.Length**

-   HTTP Status：400
-   Error Message：The parameter - “RoleName” beyond the length limit.

**InvalidParameter.AssumeRolePolicyDocument.Length**

-   HTTP Status：400
-   Error Message：The parameter - “AssumeRolePolicyDocument” beyond the length limit.

**EntityAlreadyExists.Role**

-   HTTP Status：409
-   Error Message：The role does already EXIST.

**MalformedPolicyDocument**

-   HTTP Status：400
-   Error Message：\{The error details\}

**LimitExceeded.Role**

-   HTTP Status：409
-   Error Message：The count of roles beyond the current limits.

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=CreateRole
&RoleName=ECSAdmin
&AssumeRolePolicyDocument={ "Statement": [ { "Action": "sts:AssumeRole", "Effect": "Allow", "Principal": { "RAM": "acs:ram::123456789012345678:root" } } ], "Version": "1" }
&Description=ECS管理角色
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <CreateRoleResponse>
        <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
        <Role>
            <RoleId>901234567890123</RoleId>
            <RoleName>ECSAdmin</RoleName>
            <Arn>acs:ram::1234567890123456:role/ECSAdmin</Arn>
            <Description>ECS管理角色</Description>
            <AssumeRolePolicyDocument>{ "Statement": [ { "Action": "sts:AssumeRole", "Effect": "Allow", "Principal": { "RAM": "acs:ram::123456789012345678:root" } } ], "Version": "1" }</AssumeRolePolicyDocument>
            <CreateDate>2015-01-23T12:33:18Z</CreateDate>
        </Role>
    </CreateRoleResponse>
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
            "CreateDate": "2015-01-23T12:33:18Z"
        }
    }
    ```


