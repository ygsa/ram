# 对象存储 OSS 授权 {#concept_ohn_ypx_ydb .concept}

## 问题 {#section_x1f_w4x_ydb .section}

-   [查看 OSS 的权限定义](#section_mzy_x4x_ydb)
-   [为一个子用户授予只读访问 OSS 的权限](#section_jft_y4x_ydb)
-   [为一个子用户授予完全管理 OSS 的权限](#section_fnn_z4x_ydb)
-   [授权一个子用户列出并读取一个 Bucket 中的资源](#section_jpq_1px_ydb)
-   [授权子用户完全管理某个 Bucket 的权限](#section_a1c_cpx_ydb)

## 查看 OSS 的权限定义 {#section_mzy_x4x_ydb .section}

请参考 OSS 产品文档中的[访问控制](../../cn.zh-CN//访问控制.md)部分。

## 为一个子用户授予只读访问 OSS 的权限 {#section_jft_y4x_ydb .section}

在 RAM 控制台中创建一个子用户，并为此子用户附加系统授权策略”AliyunOSSReadOnlyAccess”。附加授权策略的方式请参考[授权](../cn.zh-CN/用户指南/授权管理/授权.md)。

## 为一个子用户授予完全管理 OSS 的权限 {#section_fnn_z4x_ydb .section}

在 RAM 控制台中为此子用户附加系统授权策略 “AliyunOSSFullAccess”。

## 授权一个子用户列出并读取一个 Bucket 中的资源 {#section_jpq_1px_ydb .section}

如果您需要授权一个子用户（例如，代表您的某个应用程序）通过 OSS SDK 或 OSS CMD 列出并读取一个 Bucket 中的资源，那么您需要创建一条自定义授权策略来完成。

假设您的 Bucket 名称为 “myphotos”，那么创建的授权策略样例如下：

```
{
    "Version": "1",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "oss:ListObjects",
            "Resource": "acs:oss:*:*:myphotos"
        },
        {
            "Effect": "Allow",
            "Action": "oss:GetObject",
            "Resource": "acs:oss:*:*:myphotos/*"
        }
    ]
}
```

如果您希望被授权的子用户能够通过 OSS 控制台进行操作，那么授权策略中还需要添加 GetBucketAcl 以及 GetObjectAcl 权限（控制台为了操作体验的优化需要额外调用 OSS 的部分 API）。允许子用户通过 OSS 控制台操作的授权策略样例如下：

```
{
    "Version": "1",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "oss:ListBuckets",
            "Resource": "acs:oss:*:*:*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "oss:ListObjects",
                "oss:GetBucketAcl"
            ],
            "Resource": "acs:oss:*:*:myphotos"
        },
        {
            "Effect": "Allow",
            "Action": [
                "oss:GetObject",
                "oss:GetObjectAcl"
            ],
            "Resource": "acs:oss:*:*:myphotos/*"
        }
    ]
}
```

## 授权子用户完全管理某个 Bucket 的权限 {#section_a1c_cpx_ydb .section}

首先您需要创建一条自定义授权策略。假设您的 Bucket 名称为 “myphotos”。创建如下的自定义授权策略：

```
{
    "Version": "1",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "oss:*",
            "Resource": [
                "acs:oss:*:*:myphotos",
                "acs:oss:*:*:myphotos/*"
            ]
        }
    ]
}
```

