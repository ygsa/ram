# CreateGroup {#reference_lqj_2gn_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

创建用户组

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：操作名称，取值：

    ```
    CreateGroup
    ```


**GroupName**

-   类型：String
-   必须：是
-   描述：组名称，最大长度64个字符
-   格式：

    ```
    ^[a-zA-Z0-9\-]+$
    ```


**Comments**

-   类型：String
-   必须：否
-   描述：备注信息, 最大长度128个字符。

## 返回参数 { .section}

**Group**

-   类型：[Group](intl.zh-CN/API参考/API 参考（RAM）/数据类型/Group.md)
-   描述：组信息

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:CreateGroup
```

**Resource**

```
acs:ram:*:${AccountId}:group/*
```

## 错误信息 {#section_erf_h2n_xdb .section}

**InvalidParameter.GroupName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - "GroupName" contains invalid chars.

**InvalidParameter.GroupName.Length**

-   HTTP Status：400
-   Error Message：The parameter - "GroupName" beyond the length limit.

**InvalidParameter.Comments.Length**

-   HTTP Status：400
-   Error Message：The parameter - "Comments" beyond the length limit.

**EntityAlreadyExists.Group**

-   HTTP Status：409
-   Error Message：The group does already EXIST.

**LimitExceeded.Group**

-   HTTP Status：409
-   Error Message：The count of groups beyond the current limits.

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=CreateGroup
&GroupName=Dev-Team
&Comments=开发团队
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <CreateGroupResponse>
        <RequestId>D3F0679E-9757-95DB-AF2D-04D5188C69C5</RequestId>
        <Group>
            <GroupName>Dev-Team</GroupName>
            <Comments>开发团队</Comments>
            <CreateDate>2015-01-23T12:33:18Z</CreateDate>
        </Group>
    </CreateGroupResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "D3F0679E-9757-95DB-AF2D-04D5188C69C5",
        "Group": {
            "GroupName": "Dev-Team",
            "Comments": "开发团队",
            "CreateDate": "2015-01-23T12:33:18Z"
        }
    }
    ```


