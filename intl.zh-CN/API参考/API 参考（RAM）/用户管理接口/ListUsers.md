# ListUsers {#reference_qnx_hwk_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

列出所有RAM用户

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   名称：Action
-   类型：String
-   必须：是
-   描述：系统规定参数，取值：ListUsers

**Marker**

-   名称：Marker
-   类型：String
-   必须：否
-   描述：当请求的返回结果被截断时，可以使用Marker获取从当前截断位置之后的内容

**MaxItems**

-   名称：MaxItems
-   类型：Integer
-   必须：否
-   取值范围：\[1 - 100\]
-   默认值：100
-   描述：指定返回结果的条数，当返回结果达到MaxItems限制被截断时，返回参数`IsTruncated`将等于`true`

## 返回参数 {#section_vnl_h5k_xdb .section}

**IsTruncated**

-   类型：Boolean
-   描述：请求返回结果是否被截断

**Marker**

-   类型：String
-   描述：当`IsTruncated`为`true`时才有此字段，当返回`true`时，需要继续调用此接口，并且使用`Marker`获取截断后的内容

**Users**

-   类型：[User](intl.zh-CN/API参考/API 参考（RAM）/数据类型/User.md) 
-   描述：用户信息集合

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:ListUsers
```

**Resource**

```
acs:ram:*:${AccountId}:user/*
```

## 操作示例 {#section_pwp_vtk_xdb .section}

**请求示例**

```
https://ram.aliyuncs.com/?Action=ListUsers
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <ListUsersResponse>
      <RequestId>4B450CA1-36E8-4AA2-8461-86B42BF4CC4E</RequestId>
      <Users>
        <User>
          <UserId>1227489245380721</UserId>
          <UserName>zhangqiang</UserName>
          <DisplayName>张强</DisplayName>
          <MobilePhone>86-18600008888</MobilePhone>
          <Email>zhangqiang@example.com</Email>
          <Comments>这是一位云计算工程师</Comments>
          <CreateDate>2015-01-23T12:33:18Z</CreateDate>
          <UpdateDate>2015-01-23T12:33:18Z</UpdateDate>
        </User>
        <User>
          <UserId>1406498224724456</UserId>
          <UserName>lili</UserName>
          <DisplayName>李丽</DisplayName>
          <MobilePhone>86-18600009999</MobilePhone>
          <Email>lili@example.com</Email>
          <Comments>权限管理员</Comments>
          <CreateDate>2015-02-18T17:22:08Z</CreateDate>
          <UpdateDate>2015-02-18T17:22:08Z</UpdateDate>
        </User>
      </Users>
      <IsTruncated>true</IsTruncated>
      <Marker>EXAMPLE</Marker>
    </ListUsersResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId" : "4B450CA1-36E8-4AA2-8461-86B42BF4CC4E",
      "IsTruncated": true,
      "Marker": "EXAMPLE",
      "Users" : {
        "User" : [
          {
            "UserId" : "1227489245380721",
            "UserName" : "zhangqiang",
            "DisplayName": "张强",
            "MobilePhone": "86-18600008888",
            "Email": "zhangqiang@example.com",
            "Comments": "这是一位云计算工程师",
            "CreateDate" : "2015-01-23T12:33:18Z",
            "UpdateDate" : "2015-01-23T12:33:18Z"
          },
          {
            "UserId" : "1406498224724456",
            "UserName" : "lili",
            "DisplayName": "李丽",
            "MobilePhone": "86-18600009999",
            "Email": "lili@example.com",
            "Comments": "权限管理员",
            "CreateDate" : "2015-02-18T17:22:08Z",
            "UpdateDate" : "2015-02-18T17:22:08Z"
          }
        ]
      }
    }
    ```


