# UpdateGroup {#reference_hfq_sgn_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

更新用户组信息

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：操作名称，取值：

    ```
    UpdateGroup
    ```


**GroupName**

-   类型：String
-   必须：是
-   描述：指定组名称
-   格式：

    ```
    ^[a-zA-Z0-9\-]+$
    ```


**NewGroupName**

-   类型：String
-   必须：否
-   描述：新的组名
-   格式：

    ```
    ^[a-zA-Z0-9\-]+$
    ```


**NewComments**

-   类型：String
-   必须：否
-   描述：新的备注信息, 最大长度128个字符。

## 返回参数 { .section}

**Group**

-   类型：[Group](intl.zh-CN/API参考/API 参考（RAM）/数据类型/Group.md)
-   描述：组信息

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:UpdateGroup
```

**Resource**

```
acs:ram:*:${AccountId}:group/${GroupName}
```

## 错误信息 {#section_erf_h2n_xdb .section}

**InvalidParameter.GroupName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - "GroupName" contains invalid chars.

**InvalidParameter.GroupName.Length**

-   HTTP Status：400
-   Error Message：The parameter - "GroupName" beyond the length limit.

**InvalidParameter.NewGroupName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - "NewGroupName" contains invalid chars.

**InvalidParameter.NewGroupName.Length**

-   HTTP Status：400
-   Error Message：The parameter - "NewGroupName" beyond the length limit.

**InvalidParameter.NewComments.Length**

-   HTTP Status：400
-   Error Message：The parameter - "NewComments" beyond the length limit.

**EntityNotExist.Group**

-   HTTP Status：404
-   Error Message：The group does not exist.

**EntityAlreadyExists.Group**

-   HTTP Status：409
-   Error Message：The group does already EXIST.

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=UpdateGroup
&GroupName=Dev-Team
&NewGroupName=NewDev-Team
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <UpdateGroupResponse>
        <RequestId>EC6647CC-0A36-EC7A-BA72-CC81BF3DE182</RequestId>
        <Group>
            <GroupName>NewDev-Team</GroupName>
            <Comments>开发团队</Comments>
            <CreateDate>2015-01-23T12:33:18Z</CreateDate>
            <UpdateDate>2015-01-23T12:33:18Z</UpdateDate>
        </Group>
    </UpdateGroupResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "EC6647CC-0A36-EC7A-BA72-CC81BF3DE182",
        "Group": {
            "GroupName": "NewDev-Team",
            "Comments": "开发团队",
            "CreateDate" : "2015-01-23T12:33:18Z",
            "UpdateDate" : "2015-01-23T12:33:18Z"
        }
    }
    ```


