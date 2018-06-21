# GetPolicy {#concept_khp_dj4_xdb .concept}

## 接口描述 {#section_erh_xh4_xdb .section}

获取指定的授权策略信息

## 请求参数 {#section_nps_yh4_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：系统规定参数，取值：GetPolicy

**PolicyType**

-   类型：String
-   必须：是
-   描述：指定Policy的类型, 取值System或Custom

**PolicyName**

-   名称：PolicyName
-   类型：String
-   必须：是
-   描述：指定授权策略名称

## 返回参数 {#section_ldp_zh4_xdb .section}

**Policy**

-   类型：[Policy](intl.zh-CN/API参考/API 参考（RAM）/数据类型/Policy.md)
-   描述：授权策略的基本信息

## 需要的权限 {#section_twc_134_xdb .section}

**Action**

```
ram:GetPolicy
```

**Resource**

```
acs:ram:*:${AccountId} or system:policy/${PolicyName}
```

## 错误信息 {#section_zp3_c34_xdb .section}

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

## 请求示例 {#section_knn_d34_xdb .section}

```
https://ram.aliyuncs.com/?Action=GetPolicy
&PolicyName=OSS-Administrator
&<公共请求参数>
```

## 返回示例 {#section_jy3_f34_xdb .section}

-   XML格式

    ```
    <GetPolicyResponse>
        <RequestId>697852FB-50D7-44D9-9774-530C31EAC572</RequestId>
        <Policy>
            <PolicyName>OSS-Administrator</PolicyName>
            <PolicyType>Custom</PolicyType>
            <Description>OSS管理员权限</Description>
            <DefaultVersion>v1</DefaultVersion>
            <CreateDate>2015-01-23T12:33:18Z</CreateDate>
            <UpdateDate>2015-01-23T12:33:18Z</UpdateDate>
            <AttachmentCount>0</AttachmentCount>
        </Policy>
    </GetPolicyResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "697852FB-50D7-44D9-9774-530C31EAC572",
        "Policy": {
            "PolicyName": "OSS-Administrator",
            "PolicyType": "Custom",
            "Description": "OSS管理员权限",
            "DefaultVersion": "v1",
            "CreateDate": "2015-01-23T12:33:18Z",
            "UpdateDate": "2015-01-23T12:33:18Z",
            "AttachmentCount": 0
        }
    }
    ```


