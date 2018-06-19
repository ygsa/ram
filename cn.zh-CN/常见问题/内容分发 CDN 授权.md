# 内容分发 CDN 授权 {#concept_g2m_jrx_ydb .concept}

## 问题 {#section_x1f_w4x_ydb .section}

[授权子用户执行刷新缓存及预热操作](#section_mzy_x4x_ydb)

## 授权子用户执行刷新缓存及预热操作 {#section_mzy_x4x_ydb .section}

您可以创建如下授权策略，包含 CDN 只读、刷新缓存及预热权限：

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

然后将新创建的权限授权给子用户。

