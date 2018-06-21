# DeletePolicy {#reference_nmt_tj4_xdb .reference}

## 接口描述 {#section_erh_xh4_xdb .section}

删除指定的授权策略

## 请求参数 {#section_nps_yh4_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：系统规定参数，取值：DeletePolicy

**PolicyName**

-   类型：String
-   必须：是
-   描述：指定授权策略名称

## 返回参数 {#section_ldp_zh4_xdb .section}

只有公共返回参数，详见[公共参数](intl.zh-CN/API参考/API 参考（RAM）/调用方式/公共参数.md)

## 需要的权限 {#section_twc_134_xdb .section}

**Action**

```
ram:DeletePolicy
```

**Resource**

```
acs:ram:*:${AccountId}:policy/${PolicyName}
```

## 错误信息 {#section_zp3_c34_xdb .section}

**InvalidParameter.PolicyName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - "PolicyNam" contains invalid chars.

**InvalidParameter.PolicyName.Length**

-   HTTP Status：400
-   Error Message：The parameter - "PolicyName" beyond the length limit.

**EntityNotExist.Policy**

-   HTTP Status：404
-   Error Message：The policy does not exist.

**DeleteConflict.Policy.User**

-   HTTP Status：409
-   Error Message：The policy CAN NOT been attached to any user while deleting the policy.

**DeleteConflict.Policy.Group**

-   HTTP Status：409
-   Error Message：The policy CAN NOT been attached to any group while deleting the policy.

**DeleteConflict.Policy.Version**

-   HTTP Status：409
-   Error Message：The policy CAN NOT has any version except the defaul version.

## 请求示例 {#section_knn_d34_xdb .section}

```
https://ram.aliyuncs.com/?Action=DeletePolicy
&PolicyName=OSS-Administrator
&<公共请求参数>
```

## 返回示例 {#section_jy3_f34_xdb .section}

-   XML格式

    ```
    <DeletePolicyResponse>
        <RequestId>898FAB24-7509-43EE-A287-086FE4C44394</RequestId>
    </DeletePolicyResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "898FAB24-7509-43EE-A287-086FE4C44394"
    }
    ```


