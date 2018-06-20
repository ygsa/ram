# DeleteVirtualMFADevice {#reference_igl_c2n_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

删除虚拟多因素认证设备

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：操作接口名，系统规定参数，取值：DeleteVirtualMFADevice

**SerialNumber**

-   类型：String
-   必须：是
-   描述：指定MFA设备的序列号

## 返回参数 {#section_vnl_h5k_xdb .section}

只有公共返回参数，详见[公共参数](intl.zh-CN/API参考/API 参考（RAM）/调用方式/公共参数.md)

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:DeleteVirtualMFADevice
```

**Resource**

```
${SerialNumber}
```

## 错误信息 {#section_erf_h2n_xdb .section}

**EntityNotExist.VirtualMFADevice**

-   HTTP Status：404
-   Error Message：The virtual mfa device does not exist.

**DeleteConflict.VirtualMFADevice.User**

-   HTTP Status：409
-   Error Message：The virtual mfa device CAN NOT been bound to any user while deleting it.

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=DeleteVirtualMFADevice
&SerialNumber=acs:ram::1234567890123:mfa/device002
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <DeleteVirtualMFADeviceResponse>
        <RequestId>04F0F334-1335-436C-A1D7-6C044FE73368</RequestId>
    </DeleteVirtualMFADeviceResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "04F0F334-1335-436C-A1D7-6C044FE73368"
    }
    ```


