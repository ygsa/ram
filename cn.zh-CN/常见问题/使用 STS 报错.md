# 使用 STS 报错 {#concept_wsg_bsx_ydb .concept}

## 问题 {#section_x1f_w4x_ydb .section}

[STS 使用 Javasdk 生成临时账户密码报错](#section_mzy_x4x_ydb)

## STS 使用 Javasdk 生成临时账户密码报错 {#section_mzy_x4x_ydb .section}

STS 使用 Javasdk 生成临时账户密码报错。报错信息如下：

```
Error message: You are not authorized to do this action. You should be authorized by RAM
```

因为进行授权的子账户没有 “AliyunSTSAssumeRoleAccess” 权限。

