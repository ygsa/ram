# ListVirtualMFADevices {#reference_sk3_ddn_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

创建虚拟多因素认证设备

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：操作接口名，系统规定参数，取值：ListVirtualMFADevices

## 返回参数 {#section_vnl_h5k_xdb .section}

**VirtualMFADevices**

-   类型：[VirtualMFADevice](intl.zh-CN/API参考/API 参考（RAM）/数据类型/VirtualMFADevice.md) Array
-   描述：虚拟MFA设备列表

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:ListVirtualMFADevices
```

**Resource**

```
acs:ram:*:${AccountId}:mfa/*
```

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=ListVirtualMFADevices
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <ListVirtualMFADevicesResponse>
        <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
        <VirtualMFADevices>
            <VirtualMFADevice>
                <SerialNumber>acs:ram::1234567890123:mfa/device001</SerialNumber>
            </VirtualMFADevice>
            <VirtualMFADevice>
                <SerialNumber>acs:ram::1234567890123:mfa/device002</MFASerialNumber>
                <ActivateDate>2015-02-18T17:22:08Z<Activate>
                <User>
                    <UserId>1227489245380721</UserId>
                    <UserName>zhangqiang</UserName>
                    <DisplayName>张强</DisplayName>
                </User>
            </VirtualMFADevice>
        <VirtualMFADevicess>
    </ListVirtualMFADevicesResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368",
        "VirtualMFADevices": {
            "VirtualMFADevice": [
                {
                    "SerialNumber": "acs:ram::1234567890123:mfa/device001"
                },
                {
                    "SerialNumber": "acs:ram::1234567890123:mfa/device002",
                    "ActivateDate": "2015-02-18T17:22:08Z",
                    "User": {
                        "UserId": "1227489245380721",
                        "UserName": "zhangqiang",
                        "DisplayName": "张强"
                    }
                }
            ]
        }
    }
    ```


