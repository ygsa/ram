# 如何利用标签对ECS实例进行分组授权 {#concept_acb_stx_ydb .concept}

假设您有10台ECS实例，您想将其中5台授权给dev团队，另外5台授权给ops团队。您希望每个团队只能看到被授权的机器，未被授权的机器不允许查看。

## 分组授权 {#section_ckj_gtx_ydb .section}

您可以通过RAM实现这种功能。具体操作如下：

1.  通过打标签，将ECS的资源进行分组。比如，将其中5台机器打上一对标签，标签键是team，标签值是dev。将另外5台机器打上另一对标签，标签键是team，标签值是ops。

    对一台机器打标签的操作如下：

    1.  在ECS控制台上选择一个实例，然后单击对应的下拉菜单**更多**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/12553/4446_zh-CN.png "选择实例")

    2.  在下拉菜单中选择**编辑标签**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/12553/4447_zh-CN.png "编辑标签")

    3.  输入**标签键**和**标签值**。这里取标签键为team，标签值为dev。

         ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/12553/4449_zh-CN.png "替换标签键和标签值") 

2.  创建两个用户组，比如分别是dev和ops。然后为您的员工创建相应的用户账号，将不同的用户账号添加到不同的用户组。
3.  创建两个自定义授权策略，分别授权给不同的用户组。

    比如，给dev组授权的自定义授权策略名称是policyForDevTeam，策略内容如下：

    ```
    {
        "Statement": [
        {
            "Action": "ecs:*",
            "Effect": "Allow",
            "Resource": "*",
            "Condition": {
                "StringEquals": {
                    "ecs:tag/team": "dev"
                }
            }
        },
        {
            "Action": "ecs:DescribeTag*",
            "Effect": "Allow",
            "Resource": "*"
        }
        ],
        "Version": "1"
    }
    ```

    **说明：** 如果您的自定义标签不同，那么上述策略中关于标签条件的描述需要进行相应的替换。

    ![](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/67912/cn_zh/1520426257196/4.png)


## 显示被授权实例 {#section_lkt_ktx_ydb .section}

1.  若登录ECS控制台后未显示实例，点击实例子页的**标签**按钮。
2.  选择指定的标签键以显示被授权实例。

