# VirtualMFADevice {#reference_gps_qlv_xdb .reference}

## 描述 {#section_erh_xh4_xdb .section}

虚拟多因素认证设备

## 节点名称 {#section_nps_yh4_xdb .section}

VirtualMFADevice

## 子节点 {#section_ldp_zh4_xdb .section}

**SerialNumber**

-   类型：String
-   描述：设备序列号

**Base32StringSeed**

-   类型：String
-   描述：多因素认证设备密钥

**QRCodePNG**

-   类型：String
-   描述：密钥二维码PNG，使用Base64编码

**ActivateDate**

-   类型：String
-   描述：激活日期

**User**

-   类型：User
-   描述：绑定用户的基本信息

