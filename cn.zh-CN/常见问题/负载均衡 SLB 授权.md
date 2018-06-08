# 负载均衡 SLB 授权 {#concept_qhc_xqx_ydb .concept}

## 问题 {#section_x1f_w4x_ydb .section}

-   [查看 SLB 的权限定义](#section_mzy_x4x_ydb)
-   [为一个子用户授予只读访问 SLB 的权限](#section_jft_y4x_ydb)
-   [为一个子用户授予完全管理 SLB 的权限](#section_fnn_z4x_ydb)
-   [授权一个子用户管理两台指定的 SLB 实例](#section_jpq_1px_ydb)
-   [已经授权子用户管理某个负载均衡器的权限，但是在均衡器实例中添加/移除 ECS 服务器以及设置权重时提示没有权限](#section_a1c_cpx_ydb)

## 查看 SLB 的权限定义 {#section_mzy_x4x_ydb .section}

请参考 SLB OpenAPI 文档中的 [RAM鉴权](../../cn.zh-CN/API参考/RAM鉴权.md) 部分。

## 为一个子用户授予只读访问 SLB 的权限 {#section_jft_y4x_ydb .section}

在 RAM 控制台中创建一个子用户，并为此子用户附加系统授权策略 “AliyunSLBReadOnlyAccess”。附加授权策略的方式请参考[授权](../cn.zh-CN/用户指南/授权管理/授权.md)。

## 为一个子用户授予完全管理 SLB 的权限 {#section_fnn_z4x_ydb .section}

在 RAM 控制台中为此子用户附加系统授权策略 “AliyunSLBFullAccess”。

## **授权一个子用户管理两台指定的 SLB 实例** {#section_jpq_1px_ydb .section}

您需要使用自定义授权策略的功能。假设您的两台实例 ID 分别是 i-001 和 i-002。

首先您需要创建一条自定义授权策略，包含管理 i-001、i-002 的权限以及查看 SLB 所有资源的权限：

```
{
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "slb:*",
      "Resource": [
                  "acs:slb:*:*:loadbalancer/i-001",
                  "acs:slb:*:*:loadbalancer/i-002"
                  ]
    },
    {
      "Effect": "Allow",
      "Action": "slb:Describe*",
      "Resource": "*"
    }
  ],
  "Version": "1"
}
```

然后为此用户添加此条自定义授权策略。

## 已经授权子用户管理某个负载均衡器的权限，但是在均衡器实例中添加/移除 ECS 服务器以及设置权重时提示没有权限 {#section_a1c_cpx_ydb .section}

在负载均衡器中关于 ECS 服务器操作的接口，不仅检查 SLB 的资源权限，还要检查 ECS 服务器的权限；避免一个子用户拥有某个负载均衡器的权限后，可以将任意服务器加入此均衡器实例。

例如，如果希望将 i-001 这台 ECS 加入 SLB-001 这个负载均衡器，那么需要授予此账号如下权限：

```
{
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "slb:AddBackendServers",
      "Resource": ["acs:slb:*:*:loadbalancer/slb-001"]
    },
    {
      "Effect": "Allow",
      "Action": "slb:AddBackendServers",
      "Resource": ["acs:ecs:*:*:instance/i-001"]
    },
    {
        "Effect": "Allow",
        "Action": "slb:DescribeLoadBalancers",
        "Resource": "acs:slb:*:*:loadbalancer/*"
    }
  ],
  "Version": "1"
}
```

如果您希望简化授权，只要授权一个负载均衡器的管理权，就可以向此实例中添加任意服务器，以及设置任意实例的权重，可以参考下面的授权策略。此授权策略在 ECS 资源上添加了所有 SLB 的操作权限。

```
{
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "slb:*",
      "Resource": [
                  "acs:slb:*:*:loadbalancer/i-001",
                  "acs:slb:*:*:loadbalancer/i-002"
                  ]
    },
    {
      "Effect": "Allow",
      "Action": "slb:Describe*",
      "Resource": "*"
    },
    {
      "Effect": "Allow",
      "Action": "slb:*",
      "Resource": "acs:ecs:*:*:*"
    }
  ],
  "Version": "1"
}
```

