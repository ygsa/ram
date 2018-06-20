# CreateVirtualMFADevice {#reference_zw5_vcn_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

创建虚拟多因素认证设备

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：操作接口名，系统规定参数，取值：CreateVirtualMFADevice

**VirtualMFADeviceName**

-   类型：String
-   必须：是
-   描述：指定设备名称, 最大长度64个字符
-   限制：

    ```
    [a-zA-Z0-9-]*
    ```


## 返回参数 {#section_vnl_h5k_xdb .section}

**VirtualMFADevice**

-   类型：[VirtualMFADevice](intl.zh-CN/API参考/API 参考（RAM）/数据类型/VirtualMFADevice.md)
-   描述：虚拟多因素认证设备

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:CreateVirtualMFADevice
```

**Resource**

```
acs:ram:*:${AccountId}:mfa/*
```

## 错误信息 {#section_wyy_rll_xdb .section}

**InvalidParameter.VirtualMFADeviceName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - "VirtualMFADeviceName" contains invalid chars.

**InvalidParameter.VirtualMFADeviceName.Length**

-   HTTP Status：400
-   Error Message：The parameter - "VirtualMFADeviceName" beyond the length limit.

**EntityAlreadyExists.VirtualMFADevice**

-   HTTP Status：409
-   Error Message：The virtual mfa device does already EXIST.

**LimitExceeded.VirtualMFADevice**

-   HTTP Status：409
-   Error Message：The count of virtual mfa devices beyond the current limits.

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=CreateVirtualMFADevice
&VirtualMFADeviceName=device001
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <CreateVirtualMFADeviceResponse>
        <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
        <VirtualMFADevice>
            <SerialNumber>acs:ram::1234567890123:mfa/device001</VirtualMFASerialNumber>
            <Base32StringSeed>DSF98HAD982KJA9SDFNAS9D8FU839B8ADHBGSD7A8</Base32StringSeed>
            <QRCodePNG>YXNkZmFzZDlmeW5hc2Q5OGZoODd4bXJmcThhaGU5aSBmYXNkZiBzYWRmIGFGIDRxd2VjIGEgdHEzdCAg</QRCodePNG>
        </VirtualMFADevice>
    </CreateVirtualMFADeviceResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368",
        "VirtualMFADevice": {
            "SerialNumber": "acs:ram::1234567890123:mfa/device001",
            "Base32StringSeed": "DSF98HAD982KJA9SDFNAS9D8FU839B8ADHBGSD7A8",
            "QRCodePNG": "YXNkZmFzZDlmeW5hc2Q5OGZoODd4bXJmcThhaGU5aSBmYXNkZiBzYWRmIGFGIDRxd2VjIGEgdHEzdCAg"
        }
    }
    ```


