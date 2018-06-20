# UnbindMFADevice {#reference_mms_2fn_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

解绑多因素认证设备

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：操作接口名，系统规定参数，取值：UnbindMFADevice

**UserName**

-   类型：String
-   必须：是
-   描述：指定用户名

## 返回参数 {#section_vnl_h5k_xdb .section}

**MFADevice**

-   类型：[MFADevice](intl.zh-CN/API参考/API 参考（RAM）/数据类型/MFADevice.md)
-   描述：MFA设备信息

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:UnbindMFADevice
```

**Resource**

```
acs:ram:*:${AccountId}:user/${UserName}
```

## 错误信息 {#section_erf_h2n_xdb .section}

**InvalidParameter.UserName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - "UserName" contains invalid chars.

**InvalidParameter.UserName.Length**

-   HTTP Status：400
-   Error Message：The parameter - "UserName" beyond the length limit.

**EntityNotExist.User**

-   HTTP Status：404
-   Error Message：The user does not exist.

**EntityNotExist.User.MFADevice**

-   HTTP Status：404
-   Error Message：The user has not bound any MFA device.

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=UnbindMFADevice
&UserName=zhangqiang
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <UnbindMFADeviceResponse>
        <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
        <MFADevice>
            <SerialNumber>acs:ram::1234567890123:mfa/device002</SerialNumber>
        </MFADevice>
    </UnbindMFADeviceResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368",
        "MFADevice": {
            "SerialNumber":"acs:ram::1234567890123:mfa/device002"
        }
    }
    ```


