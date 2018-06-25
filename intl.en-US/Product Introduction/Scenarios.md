# Scenarios {#concept_xrp_jt2_xdb .concept}

RAM is applicable to the following scenarios: account management and authorization in an enterprise, resource management and authorization between enterprises, and temporary authorization for apps running on untrusted client endpoint.

## Account management and authorization in an enterprise {#section_rvv_kt2_xdb .section}

Assume that an enterprise A buys several types of cloud resources such as ECS instances, RDS instances, Server Load Balancer instances and OSS buckets, and the employees at the enterprise A need to perform operations on these resources such as buying, O&M, or online application. Different employees require different permissions, because they have different responsibilities.

**Requirements**

-   For security, the Alibaba Cloud account owner of the enterprise A does not want to disclose its account AccessKey to its employees. Rather, the account owner prefers to create different RAM user accounts for their employees and associate each RAM user account with different permissions.
-   The employees then can perform resource operations only under their permissions with their RAM user accounts and charges are not billed to these accounts but to the account owner.
-   The account owner can also revoke the permissions of a RAM user account at any time, and delete an account.

## Resource management and authorization between enterprises {#section_tvv_kt2_xdb .section}

Assume that an enterprise A has bought a lot of cloud resources, such as ECS instances, RDS instances, Server Load Balancer instances and OSS buckets for its business requirements.

Requirements

-   Enterprise A wants to focus on its business systems, so it grants cloud resource O&M, monitoring management, and other tasks to the enterprise B.
-   Enterprise B then further delegates O&M tasks to its employees. Enterprise B needs to precisely control the delegated operations that its employees can perform on the cloud resources of the enterprise A.
-   If A and B terminate this O&M entrustment contract, enterprise A can revoke the permissions of the enterprise B as needed.

## Temporary authorization for apps running on untrusted client endpoint {#section_vvv_kt2_xdb .section}

Assume that an enterprise A has developed a mobile app and has bought OSS for it. The mobile app must upload and download data to and from OSS.

**Requirements**

-   Enterprise A does not want to allow all apps to use the appServer to transmit data. Instead, enterprise A wants the apps to directly upload and download data to and from OSS.
-   Because the mobile app runs on user devices, these devices are out of control of enterprise A. For security reasons, enterprise A cannot save the AccessKey in the app.
-   Enterprise A also wants to minimize its security risks by, for example, giving each app an access token with the minimum permissions that the app needs to connect to OSS and restricting the access duration to a specified period of time \(such as 30 minutes\).

