# SecurityPreference {#reference_alh_5mv_xdb .reference}

## 描述 {#section_erh_xh4_xdb .section}

安全首选项

## 节点名称 {#section_nps_yh4_xdb .section}

SecurityPreference

## 子节点**\[LoginProfilePreference\]** {#section_ldp_zh4_xdb .section}

**EnableSaveMFATicket**

-   类型：Boolean
-   必须：否
-   描述：是否允许在用户在登录时保存MFA验证票据，目前票据有效期是七天

**AllowUserToChangePassword**

-   类型：Boolean
-   必须：false
-   描述：是否允许用户修改自己的密码

**子节点 \[AccessKeyPreference\]****AllowUserToManageAccessKeys**

-   类型：Boolean
-   必须：false
-   描述：是否允许用户管理自己的AccessKey

## 子节点 \[MFAPreference\] {#section_ivn_wmv_xdb .section}

**AllowUserToManageMFADevices**

-   类型：Boolean
-   必须：false
-   描述：是否允许用户管理自己绑定或解绑MFA设备

