# GetPolicyVersion {#reference_sdt_vm4_xdb .reference}

## 接口描述 {#section_erh_xh4_xdb .section}

获取某个授权策略的版本

## 请求参数 {#section_nps_yh4_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：系统规定参数，取值：GetPolicyVersion

**PolicyType**

-   类型：String
-   必须：是
-   描述：指定Policy的类型, 取值System或Custom

**PolicyName**

-   类型：String
-   必须：是
-   描述：授权策略名称

**VersionId**

-   类型：String
-   必须：是
-   描述：指定目标版本的Id

## 返回参数 {#section_ldp_zh4_xdb .section}

**PolicyVersion**

-   名称：[PolicyVersion](intl.zh-CN/API参考/API 参考（RAM）/数据类型/PolicyVersion.md)
-   类型：String
-   描述：授权策略版本信息

## 需要的权限 {#section_twc_134_xdb .section}

**Action**

```
ram:GetPolicyVersion
```

**Resource**

```
acs:ram:*:${AccountId} or system:group/${PolicyName}
```

## 错误信息 {#section_unp_qm4_xdb .section}

**InvalidParameter.PolicyType**

-   HTTP Status：400
-   Error Message：The parameter - "PolicyType" is incorrect.

**InvalidParameter.PolicyName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - "PolicyNam" contains invalid chars.

**InvalidParameter.PolicyName.Length**

-   HTTP Status：400
-   Error Message：The parameter - "PolicyName" beyond the length limit.

**InvalidParameter.VersionId.Format**

-   HTTP Status：400
-   Error Message：The format of the parameter - "VersionId" is incorrect.

**EntityNotExist.Policy**

-   HTTP Status：404
-   Error Message：The policy does not exist.

**EntityNotExist.Policy.Version**

-   HTTP Status：404
-   Error Message：The policy version does not exist.

## 操作示例 {#section_hbw_1n4_xdb .section}

## 请求示例 {#section_knn_d34_xdb .section}

```
https://ram.aliyuncs.com/?Action=GetPolicyVersion
&PolicyName=OSS-Administrator
&PolicyType=Custom
&VersionId=v3
&<公共请求参数>
```

## 返回示例 {#section_jy3_f34_xdb .section}

-   XML格式

    ```
    <GetPolicyVersionResponse>
        <RequestId>9B34724D-54B0-4A51-B34D-4512372FE1BE</RequestId>
        <PolicyVersion>
            <VersionId>v3</VersionId>
            <IsDefaultVersion>false</IsDefaultVersion>
            <CreateDate>2015-01-23T12:33:18Z</CreateDate>
            <PolicyDocument>
                { "Statement": [{ "Action": ["oss:*"], "Effect": "Allow", "Resource": ["acs:oss:*:*:*"]}], "Version": "1"}
            </PolicyDocument>
        </PolicyVersion>
    </GetPolicyVersionResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "9B34724D-54B0-4A51-B34D-4512372FE1BE",
        "PolicyVersion": {
            "VersionId": "v3",
            "IsDefaultVersion": false,
            "CreateDate": "2015-01-23T12:33:18Z",
            "PolicyDocument": "{ \"Statement\": [{ \"Action\": [\"oss:*\"], \"Effect\": \"Allow\", \"Resource\": [\"acs:oss:*:*:*\"]}], \"Version\": \"1\"}"
        }
    }
    ```


