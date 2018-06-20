# ListAccessKeys {#reference_esl_4cn_xdb .reference}

## 接口描述 {#section_whn_4tk_xdb .section}

列出指定用户的AccessKeys

## 请求参数 {#section_k2y_ptk_xdb .section}

**Action**

-   类型：String
-   必须：是
-   描述：系统规定参数，取值：ListAccessKeys

**UserName**

-   类型：String
-   必须：否
-   描述：指定用户，子帐号访问时不提供此参数则表示列出自己的AccessKeys。

## 返回参数 {#section_vnl_h5k_xdb .section}

**AccessKeys**

-   类型：[AccessKey](intl.zh-CN/API参考/API 参考（RAM）/数据类型/AccessKey.md) Array
-   描述：用户信息集合

## 需要的权限 {#section_g22_rtk_xdb .section}

**Action**

```
ram:ListAccessKeys
```

**Resource**

```
acs:ram:*:${AccountId}:user/${UserName}
```

## 错误信息 {#section_wyy_rll_xdb .section}

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
https://ram.aliyuncs.com/?Action=ListAccessKeys
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <ListAccessKeysResponse>
      <RequestId>4B450CA1-36E8-4AA2-8461-86B42BF4CC4E</RequestId>
      <AccessKeys>
        <AccessKey>
            <AccessKeyId>0wNEpMMlzy7szvai</AccessKeyId>
            <Status>Active</Status>
            <CreateDate>2015-01-23T12:33:18Z</CreateDate>
        </AccessKey>
        <AccessKey>
            <AccessKeyId>WnIWUruvfaDT37vQ</AccessKeyId>
            <Status>Inactive</Status>
            <CreateDate>2015-03-24T21:12:21Z</CreateDate>
        </AccessKey>
      </AccessKeys>
    </ListAccessKeysResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId" : "4B450CA1-36E8-4AA2-8461-86B42BF4CC4E",
      "AccessKeys":{
        "AccessKey":[
          {
            "AccessKeyId": "0wNEpMMlzy7szvai",
            "Status": "Active",
            "CreateDate": "2015-01-23T12:33:18Z"
          },
          {
            "AccessKeyId": "WnIWUruvfaDT37vQ",
            "Status": "Inactive",
            "CreateDate": "2015-03-24T21:12:21Z"
          }
        ]
      }
    }
    ```


