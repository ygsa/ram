# 云数据库 RDS 授权 {#concept_zqh_gqx_ydb .concept}

## 问题 {#section_x1f_w4x_ydb .section}

-   [查看 RDS 的权限定义](#section_mzy_x4x_ydb)
-   [为一个子用户授予只读访问 RDS 的权限](#section_jft_y4x_ydb)
-   [为一个子用户授予 RDS 服务的完全管理权限](#section_fnn_z4x_ydb)
-   [授权一个子用户管理两台指定的 RDS 实例](#section_jpq_1px_ydb)
-   [子用户访问 DMS 管理数据库内容](#section_a1c_cpx_ydb)

## 查看 RDS 的权限定义 {#section_mzy_x4x_ydb .section}

请参考RDS资源授权。

## 为一个子用户授予只读访问 RDS 的权限 {#section_jft_y4x_ydb .section}

在 RAM 控制台中创建一个子用户，并为此子用户附加系统授权策略”AliyunRDSReadOnlyAccess”。添加授权策略的方式请参考[授权](../cn.zh-CN/用户指南/授权管理/授权.md)。

## 为一个子用户授予 RDS 服务的完全管理权限 {#section_fnn_z4x_ydb .section}

在 RAM 控制台中为此子用户附加系统授权策略 “AliyunRDSFullAccess”。

## **授权一个子用户管理两台指定的 RDS 实例** {#section_jpq_1px_ydb .section}

您需要使用自定义授权策略的功能。这里例如您的两台实例 ID 分别是 i-001 和 i-002。

首先您需要创建一条自定义授权策略，包含管理 i-001、i-002 的权限以及查看 RDS 所有资源的权限：

```
{
  "Statement": [
    {
      "Action": "rds:*",
      "Effect": "Allow",
      "Resource": [
                  "acs:rds:*:*:dbinstance/i-001",
                  "acs:rds:*:*:dbinstance/i-002"
                  ]
    },
    {
      "Action": "rds:Describe*",
      "Effect": "Allow",
      "Resource": "*"
    }
  ],
  "Version": "1"
}
```

然后为此用户添加此条自定义授权策略。

## 子用户访问 DMS 管理数据库内容 {#section_a1c_cpx_ydb .section}

使用 DMS 访问 RDS 云数据库，对应的授权 Action 是 “dms:LoginDatabase”。

**授权子用户登录指定 RDS**

授权策略样例如下：

```
{
  "Statement": [
    {
      "Action": "dms:LoginDatabase",
      "Effect": "Allow",
      "Resource": "acs:rds:*:*:dbinstance/rds783a0639ks5k7328y"
    }
  ],
  "Version": "1"
}
```

请将 `rds783a0639ks5k7328y` 替换为您要授权的 RDS 实例 ID。

**授权子用户登录所有 RDS**

授权策略样例如下：

```
{
  "Statement": [
    {
      "Action": "dms:LoginDatabase",
      "Effect": "Allow",
      "Resource": "acs:rds:*:*:*"
    }
  ],
  "Version": "1"
}
```

