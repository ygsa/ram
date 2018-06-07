# Policy 基本元素 {#concept_xg5_51g_xdb .concept}

RAM 中使用授权策略（Policy）来描述授权的具体内容，授权内容包含以下基本因素：效力（Effect）、资源（Resource）、对资源所授予的操作权限（Action）以及限制条件（Condition）。

## 效力（Effect） {#section_inm_v1g_xdb .section}

授权效力包括两种：允许（Allow）和拒绝（Deny）。

## 资源（Resource） {#section_jnm_v1g_xdb .section}

资源是指被授权的具体对象。

比如，访问策略“允许张三对资源 SampleBucket 执行 GetBucket 操作”中的资源是“SampleBucket”。

## 操作权限（Action） {#section_knm_v1g_xdb .section}

操作方法是指对具体资源的操作。

比如，访问策略“允许张三对资源 SampleBucket 执行 GetBucket 操作”中的操作是“GetBucket”。

## 限制条件（Condition） {#section_lnm_v1g_xdb .section}

限制条件是指授权生效的限制条件。

比如，访问策略“允许张三在2011年12月31日之前对资源 SampleBucket 执行 GetBucket 操作”中的限制条件是“在2011年12月31日之前”。

## 授权策略样例 {#section_mnm_v1g_xdb .section}

下面是一个权限策略实例，它描述的含义：允许对 OSS 的 samplebucket 进行只读操作，条件是请求者的 IP 来源为 42.160.1.0。

```

{
      "Version": "1",
      "Statement":
        [{
          "Effect": "Allow",
            "Action": ["oss:List*", "oss:Get*"],
            "Resource": ["acs:oss:*:*:samplebucket", "acs:oss:*:*:samplebucket/*"],
            "Condition":
             {
                "IpAddress":
                 {
                    "acs:SourceIp": "42.160.1.0"
                  }
              }
         }]
}
```

