# ListGroups {#reference_qmy_zgn_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

列出所有的用户组

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：操作名称，取值：

    ```
    ListGroups
    ```


**Marker**

-   名称：Marker
-   类型：String
-   必须：否
-   描述：当请求的返回结果被截断时，可以使用Marker获取从当前截断位置之后的内容

**MaxItems**

-   名称：MaxIter
-   类型：Integer
-   必须：否
-   取值范围：\[1 - 1000\]
-   默认值：100
-   描述：指定返回结果的条数，当返回结果达到MaxItems限制被截断时，返回参数`IsTruncated`将等于`true`。

## 返回参数 { .section}

**Groups**

-   类型：[Group](intl.zh-CN/API参考/API 参考（RAM）/数据类型/Group.md) Array
-   描述：组信息集合

**IsTruncated**

-   类型：Boolean
-   描述：请求返回结果是否被截断

**Marker**

-   类型：String
-   描述：当`IsTruncated`为`true`时才有此字段，当返回`true`时，需要继续调用此接口，并且使用`Marker`获取截断后的内容

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:ListGroups
```

**Resource**

```
acs:ram:*:${AccountId}:group/*
```

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=ListGroups
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <ListGroupsResponse>
      <RequestId>065527AA-2F2E-AD7C-7484-F2626CFE4934</RequestId>
      <IsTruncated>true</IsTruncated>
      <Marker>EXAMPLE</Marker>
      <Groups>
        <Group>
          <GroupName>Dev-Team</GroupName>
          <Comments>开发团队</Comments>
          <CreateDate>2015-01-23T12:33:18Z</CreateDate>
          <UpdateDate>2015-01-23T12:33:18Z</UpdateDate>
        </Group>
        <Group>
          <GroupName>QA-Team</GroupName>
          <Comments>测试团队</Comments>
          <CreateDate>2015-02-18T17:22:08Z</CreateDate>
          <UpdateDate>2015-02-18T17:22:08Z</UpdateDate>
        </Group>
      </Groups>
    </ListGroupsResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "065527AA-2F2E-AD7C-7484-F2626CFE4934",
        "IsTruncated": true,
        "Marker": "EXAMPLE",
        "Groups": {
            "Group": [
                {
                    "GroupName": "Dev-Team",
                    "Comments": "开发团队",
                    "CreateDate" : "2015-01-23T12:33:18Z",
                    "UpdateDate" : "2015-01-23T12:33:18Z"
                },
                {
                    "GroupName": "QA-Team",
                    "Comments": "测试团队",
                    "CreateDate" : "2015-02-18T17:22:08Z",
                    "UpdateDate" : "2015-02-18T17:22:08Z"
                }
            ]
        }
    }
    ```


