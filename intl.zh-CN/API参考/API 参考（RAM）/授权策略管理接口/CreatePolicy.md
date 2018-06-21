# CreatePolicy {#reference_nq2_w34_xdb .reference}

## 接口描述 {#section_erh_xh4_xdb .section}

创建一个授权策略

## 请求参数 {#section_nps_yh4_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：系统规定参数，取值：CreatePolicy

**PolicyName**

-   类型：String
-   必须：是
-   描述：授权策略名称, 最多包含128个字符
-   格式：

    ```
    ^[a-zA-Z0-9\-]+$
    ```


**Description**

-   类型：String
-   必须：否
-   描述：授权策略描述，最大长度1024字字符

**PolicyDocument**

-   类型：String
-   必须：是
-   描述：授权策略内容，最大长度2048字节

## 返回参数 {#section_ldp_zh4_xdb .section}

**Policy**

-   类型：[Policy](intl.zh-CN/API参考/API 参考（RAM）/数据类型/Policy.md)
-   描述：授权策略信息

## 需要的权限 {#section_twc_134_xdb .section}

**Action**

```
ram:CreatePolicy
```

**Resource**

```
acs:ram:*:${AccountId}:policy/*
```

## 错误信息 {#section_zp3_c34_xdb .section}

**InvalidParameter.PolicyName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - "PolicyNam" contains invalid chars.

**InvalidParameter.PolicyName.Length**

-   HTTP Status：400
-   Error Message：The parameter - "PolicyName" beyond the length limit.

**InvalidParameter.PolicyDocument.Length**

-   HTTP Status：400
-   Error Message：The parameter - "PolicyName" beyond the length limit.

**InvalidParameter.Description.Length**

-   HTTP Status：400
-   Error Message：The parameter - "Description" beyond the length limit.

**MalformedPolicyDocument**

-   HTTP Status：400
-   Error Message：\{The error details\}

**EntityAlreadyExists.Policy**

-   HTTP Status：409
-   Error Message：The group does already EXIST.

**LimitExceeded.Policy**

-   HTTP Status：409
-   Error Message：The count of policy beyond the current limits.

## 请求示例 {#section_knn_d34_xdb .section}

```
https://ram.aliyuncs.com/?Action=CreatePolicy
&PolicyName=OSS-Administrator
&PolicyDocument={ "Statement": [{ "Action": ["oss:*"], "Effect": "Allow", "Resource": ["acs:oss:*:*:*"]}], "Version": "1"}
&Description=OSS管理员权限
&<公共请求参数>
```

## 返回示例 {#section_jy3_f34_xdb .section}

-   XML格式

    ```
    <CreatePolicyResponse>
        <RequestId>9B34724D-54B0-4A51-B34D-4512372FE1BE</RequestId>
        <Policy>
            <PolicyName>OSS-Administrator</PolicyName>
            <PolicyType>Custom</PolicyType>
            <Description>OSS管理员权限</Description>
            <DefaultVersion>v1</DefaultVersion>
            <CreateDate>2015-01-23T12:33:18Z</CreateDate>
        </Policy>
    </CreatePolicyResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "9B34724D-54B0-4A51-B34D-4512372FE1BE",
        "Policy": {
            "PolicyName": "OSS-Administrator",
            "PolicyType": "Custom",
            "Description": "OSS管理员权限",
            "DefaultVersion": "v1",
            "CreateDate": "2015-01-23T12:33:18Z"
        }
    }
    ```


