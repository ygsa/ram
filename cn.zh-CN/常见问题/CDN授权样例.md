# CDN授权样例 {#concept_n3d_2tx_ydb .concept}

如下的授权策略允许一个RAM用户对CDN资源的READ、Push和Refresh操作。

```
{
  "Version": "1",
  "Statement": [
    {
      "Action": [
        "cdn:Describe*",
        "cdn:PushObjectCache",
        "cdn:RefreshObjectCaches"
      ],
      "Resource": "acs:cdn:*:*:*",
      "Effect": "Allow"
    }
  ]
}
```

