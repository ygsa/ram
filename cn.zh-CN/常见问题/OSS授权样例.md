# OSS授权样例 {#concept_z1z_jsx_ydb .concept}

-   Use Case \#1

    如下的授权策略允许一个RAM用户通过OSS Web控制台对某个指定的OSS存储Bucket（比如myphotos）进行READ操作。

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

-   Use Case \#2

    如下的授权策略允许一个RAM用户通过OSS SDK对某个指定的OSS存储Bucket（比如myphotos）进行READ操作，但要求的限制条件为：请求者的SourceIP必须来自于”42.120.88.18” 或 “42.120.66.0/24”。

    ```
    {
        "Version": "1",
        "Statement": [
            {
                "Effect": "Allow",
                "Action": [
                    "oss:ListBuckets"
                ],
                "Resource": [
                    "acs:oss:*:*:*"
                ]
            },
            {
                "Effect": "Allow",
                "Action": [
                    "oss:ListObjects",
                    "oss:GetObject"
                ],
                "Resource": [
                    "acs:oss:*:*:myphotos",
                    "acs:oss:*:*:myphotos/*"
                ],
                "Condition":{
                    "IpAddress": {
                        "acs:SourceIp": ["42.120.88.18", "42.120.66.0/24"]
                    }
                }
            }
        ]
    }
    ```

-   Use Case \#3

    如下的授权策略允许一个RAM用户通过OSS Web控制台对某个指定的OSS存储路径下的所有对象（比如myphotos/hangzhou/2015/）进行READ操作。

    ```
    {
        "Version": "1",
        "Statement": [
            {
                "Effect": "Allow",
                "Action": [
                    "oss:ListBuckets",
                    "oss:GetBucketAcl"
                ],
                "Resource": [
                    "acs:oss:*:*:*"
                ]
            },
            {
                "Effect": "Allow",
                "Action": [
                    "oss:GetObject",
                    "oss:GetObjectAcl"
                ],
                "Resource": [
                    "acs:oss:*:*:myphotos/hangzhou/2015/*"
                ]
            },
            {
                "Effect": "Allow",
                "Action": [
                    "oss:ListObjects"
                ],
                "Resource": [
                    "acs:oss:*:*:myphotos"
                ],
                "Condition": {
                    "StringLike": {
                        "oss:Delimiter": "/",
                        "oss:Prefix": [
                            "",
                            "hangzhou/",
                            "hangzhou/2015/*"
                        ]
                    }
                }
            }
        ]
    }
    ```


