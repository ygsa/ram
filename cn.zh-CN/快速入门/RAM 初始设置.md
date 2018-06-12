# RAM 初始设置 {#concept_sj1_r1f_xdb .concept}

在 RAM 控制台中您可以设置您的[企业别名](#section_jfs_t1f_xdb)、 [RAM 用户的登录密码强度](#section_nfs_t1f_xdb)以及[RAM 用户安全策略](#section_rfs_t1f_xdb)。

## 设置您的企业别名 {#section_jfs_t1f_xdb .section}

为您的云账号设置一个 RAM 企业别名，好处是能让 RAM 用户更容易记住登录入口。

由于安全原因，RAM 用户的登录入口不同于主账号的登录入口。RAM 用户登录时，需要提供主账号的 RAM 企业别名、RAM 用户名和 RAM 用户登录密码。

**操作步骤**

1.  在RAM控制台点击左侧导航栏中的**设置**。
2.  点击**企业别名设置**，进入子页面。
3.  点击**编辑企业别名**，进入编辑页面。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/12339/3513_zh-CN.png "编辑企业别名")

4.  输入**企业别名**，并点击**确认**。

至此，您已完成企业别名的设置。登录到阿里云控制台后，将鼠标悬置在导航菜单右上角的账号名上，即可在悬浮窗口中查看当前账号的企业别名。

## 设置 RAM 用户的登录密码强度 {#section_nfs_t1f_xdb .section}

在 RAM 中，您可以统一指定所有 RAM 用户的密码登录强度，那么在用户重置密码时将要求不得低于您设置的密码强度。

**操作步骤**

1.  在RAM控制台点击左侧导航栏中的**设置**。
2.  在密码强度设置 子页面配置密码策略。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/12339/3514_zh-CN.png "设置密码强度")

3.  完成配置后，点击**保存修改**。

至此，您已完成 RAM 用户登录密码强度的设置。

## 设置 RAM 用户安全策略 {#section_rfs_t1f_xdb .section}

在 RAM 中，您可以指定 RAM 用户必须设置多因素认证\(MFA\)。一旦设置 MFA，您还可以统一指定是否允许登录时在其登录设备上保存 MFA 登录状态\(保存7天\)。此外，您可以进一步指定是否允许子用户自主管理密码、AccessKey及多因素认证设备。

## 操作步骤 {#section_sfs_t1f_xdb .section}

1.  在RAM控制台点击左侧导航栏中的**设置**。
2.  点击**子用户安全设置**，进入子页面。
3.  在子页面勾选需要的安全策略。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/12339/3515_zh-CN.png "子用户安全设置")

4.  完成设置后，点击**保存修改**。

至此， 您已完成 RAM 用户安全设置。

