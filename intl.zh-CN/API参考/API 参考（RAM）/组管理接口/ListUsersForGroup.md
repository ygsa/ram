# ListUsersForGroup {#reference_mxx_m3n_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

列出指定用户组所包含的子用户。

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   是否必需：是
-   描述：操作名称，取值：

    ```
    ListUsersForGroup
    ```


**GroupName**

-   类型：String
-   是否必需：是
-   描述：组名。例:Dev-Team

**Marker**

-   名称：Marker
-   类型：String
-   是否必需：否
-   描述：当请求的返回结果被截断时，可以使用Marker获取从当前截断位置之后的内容

**MaxItems**

-   名称：MaxIter
-   类型：Integer
-   是否必需：否
-   取值范围：\[1 - 1000\]
-   默认值：100
-   描述：指定返回结果的条数。当返回结果达到MaxItems限制被截断时，返回参数`IsTruncated`将等于`true`。

## 返回参数 { .section}

**Users**

-   类型：[User](intl.zh-CN/API参考/API 参考（RAM）/数据类型/User.md) Array
-   描述：用户信息集合

**IsTruncated**

-   类型：Boolean
-   描述：请求返回结果是否被截断

**Marker**

-   类型：String
-   描述：当`IsTruncated`为`true`时才有此字段。当返回`true`时，需要继续调用此接口，并且使用`Marker`获取截断后的内容。

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:ListUsersForGroup
```

**Resource**

```
acs:ram:*:${AccountId}:group/${GroupName}
```

## 错误信息 {#section_jyq_nhn_xdb .section}

**EntityNotExist.Group**

-   HTTP Status：404
-   Error Message：The group does not exist.

**InvalidParameter.GroupName.InvalidChars**

-   HTTP Status：400
-   Error Message：The parameter - “GroupName” contains invalid chars.

**InvalidParameter.GroupName.Length**

-   HTTP Status：400
-   Error Message：The parameter - “GroupName” beyond the length limit.

**EntityNotExist.Group**

-   HTTP Status：404
-   Error Message：The group does not exist.

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=ListUsersForGroup
&GroupName=dev
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <ListUsersForGroupResponse>
      <RequestId>5756784B-79C4-E82E-24C2-FC3E171E5AB3</RequestId>
      <Users>
        <User>
          <UserId>1227489245380721</UserId>
          <UserName>zhangqiang</UserName>
          <DisplayName>张强</DisplayName>
          <JoinDate>2015-01-23T12:33:18Z</JoinDate>
        </User>
        <User>
          <UserId>1406498224724456</UserId>
          <UserName>lili</UserName>
          <DisplayName>李丽</DisplayName>
          <JoinDate>2015-02-18T17:22:08Z</JoinDate>
        </User>
      </Users>
    </ListUsersForGroupResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId" : "4B450CA1-36E8-4AA2-8461-86B42BF4CC4E",
      "Users" : {
        "User" : [
          {
            "UserId" : "1227489245380721",
            "UserName" : "zhangqiang",
            "DisplayName" : "张强",
            "JoinDate" : "2015-01-23T12:33:18Z"
          },
          {
            "UserId" : "1406498224724456",
            "UserName" : "lili",
            "DisplayName" : "李丽",
            "JoinDate" : "2015-02-18T17:22:08Z"
          }
        ]
      }
    }
    ```


