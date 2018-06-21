# DeletePolicyVersion {#reference_lj5_2n4_xdb .reference}

## 接口描述 {#section_erh_xh4_xdb .section}

删除指定的授权策略的某个版本

## 请求参数 {#section_nps_yh4_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：系统规定参数，取值：DeletePolicyVersion

**PolicyName**

-   类型：String
-   必须：是
-   描述：授权策略名称

**VersionId**

-   类型：String
-   必须：是
-   描述：指定目标版本的Id

## 返回参数 {#section_ldp_zh4_xdb .section}

只有公共返回参数，详见[公共参数](intl.zh-CN/API参考/API 参考（RAM）/调用方式/公共参数.md)

## 需要的权限 {#section_twc_134_xdb .section}

**Action**

```
ram:DeletePolicyVersion
```

**Resource**

```
acs:ram:*:${AccountId}:policy/${PolicyName}
```

## 错误信息 {#section_unp_qm4_xdb .section}

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

**DeleteConflict.Policy.Version.Default**

-   HTTP Status：409
-   Error Message：The default policy version CAN NOT been deleted directly.

## 操作示例 {#section_hbw_1n4_xdb .section}

## 请求示例 {#section_knn_d34_xdb .section}

```
https://ram.aliyuncs.com/?Action=DeletePolicyVersion
&PolicyName=OSS-Administrator
&VersionId=v3
&<公共请求参数>
```

## 返回示例 {#section_jy3_f34_xdb .section}

-   XML格式

    ```
    <DeletePolicyVersionResponse>
        <RequestId>9B34724D-54B0-4A51-B34D-4512372FE1BE</RequestId>
    </DeletePolicyVersionResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "9B34724D-54B0-4A51-B34D-4512372FE1BE"
    }
    ```


