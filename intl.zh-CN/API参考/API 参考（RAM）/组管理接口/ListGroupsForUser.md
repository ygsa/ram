# ListGroupsForUser {#reference_afj_g3n_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

列出指定子用户所加入的组信息

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：操作名称，取值：

    ```
    ListGroupsForUser
    ```


**UserName**

-   类型：String
-   必须：是
-   描述：用户名称

## 返回参数 { .section}

**Groups**

-   类型：[Group](intl.zh-CN/API参考/API 参考（RAM）/数据类型/Group.md) Array
-   描述：组信息集合

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:ListGroupsForUser
```

**Resource**

```
acs:ram:*:${AccountId}:user/${UserName}
```

## 错误信息 {#section_jyq_nhn_xdb .section}

**InvalidParameter.UserName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - "UserName" contains invalid chars.

**InvalidParameter.UserName.Length**

-   HTTP Status：400
-   Error Message：The parameter - "UserName" beyond the length limit.

**EntityNotExist.User**

-   HTTP Status：404
-   Error Message：The user does not exist.

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=ListGroupsForUser
&UserName=zhangqiang
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <ListGroupsForUserResponse>
      <RequestId>0945BF6F-54A4-C384-C89C-C500DCEE367C</RequestId>
      <Groups>
        <Group>
          <GroupName>Dev-Team</GroupName>
          <Comments>开发团队</Comments>
          <JoinDate>2015-01-23T12:33:18Z</JoinDate>
        </Group>
        <Group>
          <GroupName>QA-Team</GroupName>
          <Comments>测试团队</Comments>
          <JoinDate>2015-02-18T17:22:08Z</JoinDate>
        </Group>
      </Groups>
    </ListGroupsForUserResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "0945BF6F-54A4-C384-C89C-C500DCEE367C",
        "Groups": {
            "Group": [
                {
                    "GroupName": "Dev-Team",
                    "Comments": "开发团队",
                    "JoinDate" : "2015-01-23T12:33:18Z"
                },
                {
                    "GroupName": "QA-Team",
                    "Comments": "测试团队",
                    "JoinDate" : "2015-02-18T17:22:08Z"
                }
            ]
        }
    }
    ```


