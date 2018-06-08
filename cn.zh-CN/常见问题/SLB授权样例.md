# SLB授权样例 {#concept_e1s_1tx_ydb .concept}

-   Use Case \#1

    如果您的租户账号购买了10个SLB实例。而作为RAM管理员，您希望仅仅授权其中的2个SLB实例给某个RAM用户。那么您可以创建如下的授权策略：

    **说明：** 授予该策略的RAM用户是可以列出所有的SLB实例，但只能操作（比如DeleteLoadBalancer操作）其中的两台。目前，不支持RAM用户仅仅查看自己有访问权限的SLB实例。

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

-   se Case \#2

    RAM用户将一台后端ECS服务器（如i-001\)添加到SLB实例（如slb-001）。具体策略如下：

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
          "Resource": "acs:ecs:*:*:instance/i-001"
        }
      ],
      "Version": "1"
    }
    ```

-   Use Case \#3

    RAM用户将您租户账号中的任意后端ECS服务器添加到SLB实例（如slb-001）。具体策略如下：

    ```
    {
      "Statement": [
        {
          "Effect": "Allow",
          "Action": "slb:*",
          "Resource": ["acs:slb:*:*:loadbalancer/slb-001"]
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


