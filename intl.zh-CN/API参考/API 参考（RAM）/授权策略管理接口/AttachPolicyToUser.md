# AttachPolicyToUser {#reference_nfy_c44_xdb .reference}

## 接口描述 {#section_erh_xh4_xdb .section}

为指定用户附加授权

## 请求参数 {#section_nps_yh4_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：系统规定参数，取值：AttachPolicyToUser

**PolicyType**

-   类型：String
-   必须：是
-   描述：指定Policy的类型, 取值System或Custom

**PolicyName**

-   类型：String
-   必须：是
-   描述：指定授权策略名称

**UserName**

-   类型：String
-   必须：是
-   描述：指定用户名。例:zhangqiang

## 返回参数 {#section_ldp_zh4_xdb .section}

只有公共返回参数，详见[公共参数](intl.zh-CN/API参考/API 参考（RAM）/调用方式/公共参数.md)

## 需要的权限 {#section_twc_134_xdb .section}

**Action**

```
ram:AttachPolicyToUser
```

**Resource**

```
acs:ram:*:${AccountId}:user/${UserName}

acs:ram:*:${AccountId} or system:policy/${PolicyName}
```

## 错误信息 {#section_unp_qm4_xdb .section}

**InvalidParameter.UserName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - "UserName" contains invalid chars.

**InvalidParameter.UserName.Length**

-   HTTP Status：400
-   Error Message：The parameter - "UserName" beyond the length limit.

**EntityNotExist.User**

-   HTTP Status：404
-   Error Message：The user does not exist.

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

**EntityAlreadyExists.User.Policy**

-   HTTP Status：409
-   Error Message：The user has already been attached this policy.

**LimitExceeded.User.Policy**

-   HTTP Status：409
-   Error Message：The policy count of the user attached policies beyond the current limits.

## 操作示例 {#section_hbw_1n4_xdb .section}

## 请求示例 {#section_knn_d34_xdb .section}

```
https://ram.aliyuncs.com/?Action=AttachPolicyToUser
&PolicyType=Custom
&PolicyName=OSS-Administrator
&UserName=zhangqiang
&<公共请求参数>
```

## 返回示例 {#section_jy3_f34_xdb .section}

-   XML格式

    ```
    <AttachPolicyToUserResponse>
        <RequestId>697852FB-50D7-44D9-9774-530C31EAC572</RequestId>
    </AttachPolicyToUserResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "697852FB-50D7-44D9-9774-530C31EAC572"
    }
    ```


