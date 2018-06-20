# CreateAccessKey {#reference_dbh_tbn_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

为RAM子用户创建AccessKey

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：操作接口名，系统规定参数，取值：CreateAccessKey

**UserName**

-   类型：String
-   必须：否
-   描述：指定用户名，子账号调用此接口时，默认为自己创建AccessKey

## 返回参数 {#section_vnl_h5k_xdb .section}

**AccessKey**

-   类型：[AccessKey](intl.zh-CN/API参考/API 参考（RAM）/数据类型/AccessKey.md)
-   描述：访问密钥

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:CreateAccessKey
```

**Resource**

```
acs:ram:*:${AccountId}:user/${UserName}
```

## 错误信息 {#section_wyy_rll_xdb .section}

**InvalidParameter.UserName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - "UserName" contains invalid chars.

**InvalidParameter.UserName.Length**

-   HTTP Status：400
-   Error Message：The parameter - "UserName" beyond the length limit.

**LimitExceeded.User.AccessKey**

-   HTTP Status：409
-   Error Message：The access key count of the user access keys beyond the current limits.

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=CreateAccessKey
&UserName=zhangqiang
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <CreateAccessKeyResponse>
        <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
        <AccessKey>
            <AccessKeyId>0wNEpMMlzy7szvai</AccessKeyId>
            <AccessKeySecret>PupkTg8jdmau1cXxYacgE736PJj4cA</AccessKeySecret>
            <Status>Active</Status>
            <CreateDate>2015-01-23T12:33:18Z</CreateDate>
        </AccessKey>
    </CreateAccessKeyResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368",
        "AccessKey": {
            "AccessKeyId": "0wNEpMMlzy7szvai",
            "AccessKeySecret": "PupkTg8jdmau1cXxYacgE736PJj4cA",
            "Status": "Active",
            "CreateDate": "2015-01-23T12:33:18Z"
        }
    }
    ```


