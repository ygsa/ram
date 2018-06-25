# GetCallerIdentity {#reference_yyw_ssv_xdb .reference}

## 接口描述 {#section_lgj_jsv_xdb .section}

通过该接口，可以获取当前调用者的身份信息。

## 请求参数 {#section_it1_ksv_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：系统规定参数，取值：GetCallerIdentity

## 返回参数 {#section_tqj_lsv_xdb .section}

**AccountId**

-   类型：String
-   描述：当前调用者所属云帐号的数字ID

**UserId**

-   类型：String
-   描述：当前调用者的用户ID。如果当前调用者是云帐号，则返回值与AccountId相同。

**Arn**

-   类型：String
-   描述：当前调用者的阿里云资源描述符\(Aliyun Resource Names\)

## 操作示例 {#section_tdy_lsv_xdb .section}

**HTTP Request**

```
https://sts.aliyuncs.com?Action=GetCallerIdentity
&<公共请求参数>
```

**HTTP Response**

-   **XML格式**

    ```
    <GetCallerIdentityResponse>
        <RequestId>2C9BE469-4A35-44D5-9529-CAA280B11603</RequestId>
        <AccountId>1968132000123456</AccountId>
        <UserId>216959339000654321</UserId>
        <Arn>acs:ram::1968132000123456:user/admin</Arn>
    </GetCallerIdentityResponse>
    ```

-   **JSON格式**

    ```
    {
        "RequestId": "2C9BE469-4A35-44D5-9529-CAA280B11603",
        "AccountId": "1968132000123456",
        "UserId": "216959339000654321",
        "Arn": "acs:ram::1968132000123456:user/admin"
    }
    ```


