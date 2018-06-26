# Attach policies to a RAM user {#concept_t13_3gf_xdb .concept}

There are two methods for authorizing a RAM user:

-   [Attach policies to a RAM user directly](#section_odn_kgf_xdb)
-   [Authorization for user group to which the user belongs](#section_tdn_kgf_xdb)

Both of these methods can achieve the purpose of granting a RAM user the permission for accessing related resources.

## Background {#section_ndn_kgf_xdb .section}

System authorization policies are a group of general authorization policies that meet coarse-granularity authorization requirements. For example, you can use them to authorize a RAM user to manage orders \(AliyunBSSFullAccess\), ECS resources \(AliyunECSFullAccess\), or all sub-users and their permissions \(AliyunRAMFullAccess\).

You can view all the system authorization policies that are supported by RAM in [Authorization Policy Management](../../../../intl.en-US/User Guide/Authorization/Authorization Policy Management.md).

If none of these authorization policies meet your needs, you can customize a finer-granularity authorization policy. For details, see [Create a custom policy \(optional\)](intl.en-US/Quick Start/Create a custom policy (optional).md).

## Attach policies to a RAM user directly {#section_odn_kgf_xdb .section}

Use AttachPolicyToUser to attach policies to a RAM user directly.

**The operation procedure is as follows:**

1.  Click **Users** in the left navigation pane of the RAM console.
2.  On the Users page, click **Authorize** next to the user \(which can be searched by user name\) to whom you want to grant permissions.
3.  In the **Edit User-Level Authorization** window, click an authorization policy and move it to the selected authorization policy field.

    -   Optional Authorization Policy Name from left Select the policy you want in the list, click the right arrow \(that is, authorization\) adds it to the list of selected Authorization Policy names.

    -   Instead, click the left arrow to deselect the policy in the list of selected Authorization Policy names.

    ![](images/3542_en-US.png "Edit a personal authorization policy")


## Authorization for user group to which the user belongs {#section_tdn_kgf_xdb .section}

Through the chain. Authorize the user group to which the user belongs.

Before using this method, make sure that the authorized user is already in the user group that you want to authorize.

**Operation steps**

1.  In the ram console, click Group Management in the left navigation bar.
2.  Locate the user group to which you want to authorize the user, and click the authorization button for this user group.
3.  In the Edit Group Authorization Policy Dialog Box, add an Authorization Policy \(search by keyword\), and click Determine.

**Subsequent operation**

-   For direct grant of RAM Permissions for users, you can go to the personal authorization Policies tab of the user authorization Policies Sub-page View permissions, or disauthorize.
-   For grant of RAM Permissions for user-owned user groups, you can go to the group Authorization Policy Management Sub-page to view the permissions or disauthorize.

