# 使用 ActionTrail 记录 RAM 操作 {#concept_cbf_khk_xdb .concept}

RAM 已经与 [操作审计（ActionTrail）](https://www.aliyun.com/product/actiontrail)服务进行了集成，您可以在 ActionTrail 中查看所有用户（主账号/RAM 用户）对您的资源实例所进行的运维管控类操作记录。

ActionTrail 记录的 RAM 信息包括：

-   主账号/RAM 用户登录。详情请参考 [ConsoleSignin 操作事件格式样例](https://help.aliyun.com/document_detail/28828.html)。
-   RAM 控制台操作。详情请参考 [RAM 操作事件格式样例](https://help.aliyun.com/document_detail/28824.html)的“RAM 用户通过控制台操作 RAM”。
-   RAM/STS 的所有创建、变更、删除类 API 调用。详情请参考 [RAM 操作事件格式样例](https://help.aliyun.com/document_detail/28824.html)的“RAM 用户通过 SDK 操作 RAM”。

关于操作记录的详细信息，请参考 [ActionTrail 操作日志的结构](https://help.aliyun.com/document_detail/28819.html)。

