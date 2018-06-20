# ChangePassword {#reference_w4g_sfn_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

修改子用户密码

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：操作接口名，系统规定参数，取值：ChangePassword

**OldPassword**

-   类型：String
-   必须：是
-   描述：旧密码

**NewPassword**

-   类型：String
-   必须：是
-   描述：指定密码，密码必须符合密码强度要求。关于密码强度设置接口，请参考[SetPasswordPolicy](intl.zh-CN/API参考/API 参考（RAM）/安全设置接口/SetPasswordPolicy.md)。

## 返回参数 { .section}

只有公共返回参数，详见[公共参数](intl.zh-CN/API参考/API 参考（RAM）/调用方式/公共参数.md)

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:ChangePassword
```

**Resource**

```
acs:ram:*:${AccountId}:user/${UserName}
```

## 错误信息 {#section_erf_h2n_xdb .section}

**NotSupport.Account**

-   HTTP Status：400
-   Error Message：This method can be only invoked by sub user.

**InvalidParameter.OldPassword.Incorrect**

-   HTTP Status：400
-   Error Message：The parameter - “OldPassword” is incorrect.

**InvalidParameter.NewPassword.TooWeak**

-   HTTP Status：400
-   Error Message：The parameter - “NewPassword” is not compliant with the password policy.

**InvalidParameter.NewPassword.ReusePrevention**

-   HTTP Status：400
-   Error Message：The parameter - “NewPassword” is not compliant with the reuse prevention password policy.

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=ChangePassword
&OldPassword=123456
&NewPassword=aw$2ad)d
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <ChangePassword>
        <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
    </ChangePassword>
    ```

-   JSON格式

    ```
    {
        "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368"
    }
    ```


