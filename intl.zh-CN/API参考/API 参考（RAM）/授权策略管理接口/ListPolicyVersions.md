# ListPolicyVersions {#reference_kpp_mn4_xdb .reference}

## 接口描述 {#section_erh_xh4_xdb .section}

列出授权策略版本

## 请求参数 {#section_nps_yh4_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：系统规定参数，取值：ListPolicyVersions

**PolicyType**

-   类型：String
-   必须：是
-   描述：指定Policy的类型, 取值System或Custom

**PolicyName**

-   类型：String
-   必须：是
-   描述：授权策略名称

## 返回参数 {#section_ldp_zh4_xdb .section}

**PolicyVersions**

-   类型：[PolicyVersion](intl.zh-CN/API参考/API 参考（RAM）/数据类型/PolicyVersion.md) Array
-   描述：授权策略名称列表

## 需要的权限 {#section_twc_134_xdb .section}

**Action**

```
ram:ListPolicyVersions
```

**Resource**

```
acs:ram:*:${AccountId} or system:policy/${PolicyName}
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

**EntityNotExist.Policy**

-   HTTP Status：404
-   Error Message：The policy does not exist.

## 操作示例 {#section_hbw_1n4_xdb .section}

## 请求示例 {#section_knn_d34_xdb .section}

```
https://ram.aliyuncs.com/?Action=ListPolicyVersions
&<公共请求参数>
```

## 返回示例 {#section_jy3_f34_xdb .section}

-   XML格式

    ```
    <ListPolicyVersionsResponse>
        <RequestId>7B8A4E7D-6CFF-471D-84DF-195A7A241ECB</RequestId>
        <PolicyVersions>
            <PolicyVersion>
                <VersionId>v3</VersionId>
                <IsDefaultVersion>false</IsDefaultVersion>
                <CreateDate>2015-01-23T12:33:18Z</CreateDate>
            </PolicyVersion>
            <PolicyVersion>
                <VersionId>v5</VersionId>
                <IsDefaultVersion>true</IsDefaultVersion>
                <CreateDate>2015-02-26T01:25:52Z</CreateDate>
            </PolicyVersion>
        </PolicyVersions>
    </ListPolicyVersionsResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "7B8A4E7D-6CFF-471D-84DF-195A7A241ECB",
        "PolicyVersions": {
            "PolicyVersion": [
                {
                    "VersionId": "v3",
                    "IsDefaultVersion": false,
                    "CreateDate": "2015-01-23T12:33:18Z"
                },
                {
                    "VersionId": "v5",
                    "IsDefaultVersion": true,
                    "CreateDate": "2015-02-26T01:25:52Z"
                }
            ]
        }
    }
    ```


