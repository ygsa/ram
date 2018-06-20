# API 概览 {#concept_vdd_rmk_xdb .concept}

本页面列出了 RAM 所有 API 接口。更多 OpenAPI 资源，请关注 [API Explorer](https://api.aliyun.com/)。

**用户管理相关接口**

|API|描述|
|---|--|
|[CreateUser](cn.zh-CN/API参考/API 参考（RAM）/用户管理接口/CreateUser.md)|创建 RAM 子用户|
|[GetUser](cn.zh-CN/API参考/API 参考（RAM）/用户管理接口/GetUser.md)|获取用户的详细信息|
|[UpdateUser](cn.zh-CN/API参考/API 参考（RAM）/用户管理接口/UpdateUser.md)|更新用户的基本信息|
|[DeleteUser](cn.zh-CN/API参考/API 参考（RAM）/用户管理接口/DeleteUser.md)|删除一个 RAM 用户|
|[ZH-CN\_TP\_12390.dita](ZH-CN_TP_12390.dita)|列出所有 RAM 用户|
|[CreateLoginProfile](cn.zh-CN/API参考/API 参考（RAM）/用户管理接口/CreateLoginProfile.md)|为一个 RAM 子用户启用 Web 控制台登录|
|[GetLoginProfile](cn.zh-CN/API参考/API 参考（RAM）/用户管理接口/GetLoginProfile.md)|查看一个 RAM 用户的登录配置|
|[DeleteLoginProfile](cn.zh-CN/API参考/API 参考（RAM）/用户管理接口/DeleteLoginProfile.md)|关闭指定子用户登录 Web 控制台的功能|
|[ZH-CN\_TP\_12394.dita](ZH-CN_TP_12394.dita)|修改用户的登录配置|
|[CreateAccessKey](cn.zh-CN/API参考/API 参考（RAM）/用户管理接口/CreateAccessKey.md)|为 RAM 子用户创建 AccessKey|
|[UpdateAccessKey](cn.zh-CN/API参考/API 参考（RAM）/用户管理接口/UpdateAccessKey.md)|变更 RAM 子用户 AccessKey 的状态|
|[DeleteAccessKey](cn.zh-CN/API参考/API 参考（RAM）/用户管理接口/DeleteAccessKey.md)|删除 RAM 子用户的 AccessKey|
|[ListAccessKeys](cn.zh-CN/API参考/API 参考（RAM）/用户管理接口/ListAccessKeys.md)|列出指定用户的 AccessKeys|
|[CreateVirtualMFADevice](cn.zh-CN/API参考/API 参考（RAM）/用户管理接口/CreateVirtualMFADevice.md)|创建虚拟多因素认证设备|
|[ListVirtualMFADevices](cn.zh-CN/API参考/API 参考（RAM）/用户管理接口/ListVirtualMFADevices.md)|列出虚拟多因素认证设备|
|[DeleteVirtualMFADevice](cn.zh-CN/API参考/API 参考（RAM）/用户管理接口/DeleteVirtualMFADevice.md)|删除虚拟多因素认证设备|
|[BindMFADevice](cn.zh-CN/API参考/API 参考（RAM）/用户管理接口/BindMFADevice.md)|绑定多因素认证设备|
|[UnbindMFADevice](cn.zh-CN/API参考/API 参考（RAM）/用户管理接口/UnbindMFADevice.md)|解绑多因素认证设备|
|[GetUserMFAInfo](cn.zh-CN/API参考/API 参考（RAM）/用户管理接口/GetUserMFAInfo.md)|获取指定子用户的多因素认证设备信息|
|[ChangePassword](cn.zh-CN/API参考/API 参考（RAM）/用户管理接口/ChangePassword.md)|修改子用户密码|

**组管理相关接口**

|API|描述|
|---|--|
|[CreateGroup](cn.zh-CN/API参考/API 参考（RAM）/组管理接口/CreateGroup.md)|创建用户组|
|[GetGroup](cn.zh-CN/API参考/API 参考（RAM）/组管理接口/GetGroup.md)|获取用户组信息|
|[UpdateGroup](cn.zh-CN/API参考/API 参考（RAM）/组管理接口/UpdateGroup.md)|更新用户组信息|
|[ListGroups](cn.zh-CN/API参考/API 参考（RAM）/组管理接口/ListGroups.md)|列出所有的用户组|
|[DeleteGroup](cn.zh-CN/API参考/API 参考（RAM）/组管理接口/DeleteGroup.md)|删除指定的组|
|[AddUserToGroup](cn.zh-CN/API参考/API 参考（RAM）/组管理接口/AddUserToGroup.md)|将子用户添加到指定的用户组|
|[RemoveUserFromGroup](cn.zh-CN/API参考/API 参考（RAM）/组管理接口/RemoveUserFromGroup.md)|将子用户从用户组中移除|
|[ListGroupsForUser](cn.zh-CN/API参考/API 参考（RAM）/组管理接口/ListGroupsForUser.md)|列出指定子用户所加入的组信息|
|[ListUsersForGroup](cn.zh-CN/API参考/API 参考（RAM）/组管理接口/ListUsersForGroup.md)|列出指定用户组所包含的子用户|

**角色管理相关接口**

|API|描述|
|---|--|
|[CreateRole](cn.zh-CN/API参考/API 参考（RAM）/角色管理接口/CreateRole.md)|创建角色|
|[GetRole](cn.zh-CN/API参考/API 参考（RAM）/角色管理接口/GetRole.md)|获取角色信息|
|[UpdateRole](cn.zh-CN/API参考/API 参考（RAM）/角色管理接口/UpdateRole.md)|更新角色信息|
|[ListRoles](cn.zh-CN/API参考/API 参考（RAM）/角色管理接口/ListRoles.md)|列出角色|
|[DeleteRole](cn.zh-CN/API参考/API 参考（RAM）/角色管理接口/DeleteRole.md)|删除指定的角色|

**授权策略管理接口**

|API|描述|
|---|--|
|[CreatePolicy](cn.zh-CN/API参考/API 参考（RAM）/授权策略管理接口/CreatePolicy.md)|创建一个授权策略|
|[GetPolicy](cn.zh-CN/API参考/API 参考（RAM）/授权策略管理接口/GetPolicy.md)|获取指定的授权策略信息|
|[DeletePolicy](cn.zh-CN/API参考/API 参考（RAM）/授权策略管理接口/DeletePolicy.md)|删除指定的授权策略|
|[ListPolicies](cn.zh-CN/API参考/API 参考（RAM）/授权策略管理接口/ListPolicies.md)|列出授权策略|
|[CreatePolicyVersion](cn.zh-CN/API参考/API 参考（RAM）/授权策略管理接口/CreatePolicyVersion.md)|为授权策略创建新的版本|
|[GetPolicyVersion](cn.zh-CN/API参考/API 参考（RAM）/授权策略管理接口/GetPolicyVersion.md)|获取某个授权策略的版本|
|[DeletePolicyVersion](cn.zh-CN/API参考/API 参考（RAM）/授权策略管理接口/DeletePolicyVersion.md)|删除指定的授权策略的某个版本|
|[ListPolicyVersions](cn.zh-CN/API参考/API 参考（RAM）/授权策略管理接口/ListPolicyVersions.md)|列出授权策略版本|
|[SetDefaultPolicyVersion](cn.zh-CN/API参考/API 参考（RAM）/授权策略管理接口/SetDefaultPolicyVersion.md)|设置授权策略默认版本|
|[AttachPolicyToUser](cn.zh-CN/API参考/API 参考（RAM）/授权策略管理接口/AttachPolicyToUser.md)|为指定用户附加授权|
|[DetachPolicyFromUser](cn.zh-CN/API参考/API 参考（RAM）/授权策略管理接口/DetachPolicyFromUser.md)|为用户撤销指定的授权|
|[AttachPolicyToGroup](cn.zh-CN/API参考/API 参考（RAM）/授权策略管理接口/AttachPolicyToGroup.md)|为指定组附加授权|
|[DetachPolicyFromGroup](cn.zh-CN/API参考/API 参考（RAM）/授权策略管理接口/DetachPolicyFromGroup.md)|为组撤销指定的授权|
|[AttachPolicyToRole](cn.zh-CN/API参考/API 参考（RAM）/授权策略管理接口/AttachPolicyToRole.md)|为指定角色附加授权|
|[DetachPolicyFromRole](cn.zh-CN/API参考/API 参考（RAM）/授权策略管理接口/DetachPolicyFromRole.md)|为角色撤销指定的授权|
|[ListEntitiesForPolicy](cn.zh-CN/API参考/API 参考（RAM）/授权策略管理接口/ListEntitiesForPolicy.md)|列出引用授权策略的实体|
|[ListPoliciesForUser](cn.zh-CN/API参考/API 参考（RAM）/授权策略管理接口/ListPoliciesForUser.md)|列出指定用户被授予的授权策略|
|[ListPoliciesForGroup](cn.zh-CN/API参考/API 参考（RAM）/授权策略管理接口/ListPoliciesForGroup.md)|列出组被授予的授权策略|
|[ListPoliciesForRole](cn.zh-CN/API参考/API 参考（RAM）/授权策略管理接口/ListPoliciesForRole.md)|列出角色被授予的授权策略|

**安全设置相关接口**

|API|描述|
|---|--|
|[SetAccountAlias](cn.zh-CN/API参考/API 参考（RAM）/安全设置接口/SetAccountAlias.md)|设置云账号别名|
|[GetAccountAlias](cn.zh-CN/API参考/API 参考（RAM）/安全设置接口/GetAccountAlias.md)|查看云账号别名|
|[ClearAccountAlias](cn.zh-CN/API参考/API 参考（RAM）/安全设置接口/ClearAccountAlias.md)|清除云账号别名|
|[SetPasswordPolicy](cn.zh-CN/API参考/API 参考（RAM）/安全设置接口/SetPasswordPolicy.md)|设置子用户密码强度等策略|
|[GetPasswordPolicy](cn.zh-CN/API参考/API 参考（RAM）/安全设置接口/GetPasswordPolicy.md)|获取子用户密码强度等策略|
|[SetSecurityPreference](cn.zh-CN/API参考/API 参考（RAM）/安全设置接口/SetSecurityPreference.md)|设置全局安全首选项|

**数据类型**

|类型|描述|
|--|--|
|[User](cn.zh-CN/API参考/API 参考（RAM）/数据类型/User.md)|用户信息|
|[LoginProfile](cn.zh-CN/API参考/API 参考（RAM）/数据类型/LoginProfile.md)|用户登录配置|
|[MFADevice](cn.zh-CN/API参考/API 参考（RAM）/数据类型/MFADevice.md)|多因素认证设备|
|[VirtualMFADevice](cn.zh-CN/API参考/API 参考（RAM）/数据类型/VirtualMFADevice.md)|虚拟多因素认证设备|
|[AccessKey](cn.zh-CN/API参考/API 参考（RAM）/数据类型/AccessKey.md)|访问密钥|
|[Group](cn.zh-CN/API参考/API 参考（RAM）/数据类型/Group.md)|组信息类型|
|[Role](cn.zh-CN/API参考/API 参考（RAM）/数据类型/Role.md)|角色|
|[Policy](cn.zh-CN/API参考/API 参考（RAM）/数据类型/Policy.md)|授权策略|
|[PolicyVersion](cn.zh-CN/API参考/API 参考（RAM）/数据类型/PolicyVersion.md)|授权策略版本|
|[PasswordPolicy](cn.zh-CN/API参考/API 参考（RAM）/数据类型/PasswordPolicy.md)|密码策略|
|[SecurityPreference](cn.zh-CN/API参考/API 参考（RAM）/数据类型/SecurityPreference.md)|安全首选项|

