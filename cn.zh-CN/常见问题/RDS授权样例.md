# RDS授权样例 {#concept_e4d_ssx_ydb .concept}

如果您的租户账号购买了10个RDS实例。而作为RAM管理员，您希望仅仅授权其中的2个RDS实例给某个RAM用户。那么您可以创建如下的授权策略：

**说明：** 授予该策略的RAM用户是可以列出所有的RDS实例，但只能操作（比如DeleteDBInstance操作）其中的两台。目前，不支持RAM用户仅仅查看自己有访问权限的RDS实例。

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

