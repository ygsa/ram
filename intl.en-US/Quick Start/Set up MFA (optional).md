# Set up MFA \(optional\) {#concept_u2b_ww2_xdb .concept}

This article describes how to open MFA \(multi-factor authentication\) in the ram console\) and how to sign in with MFA to help you use MFA Improve account security.

## Open Multi-factor certification for main account {#section_gw3_xw2_xdb .section}

Your Alibaba Cloud account has full control permission for all resources under it. Therefore, once the logon password or access key of the primary account is disclosed, the security of assets under the account will be greatly threatened. To reduce risks, we strongly recommend that you bind multi-factor authentication \(MFA\) to your primary account.

**Prerequisite**

You need to install the virtual MFA application on the smartphone terminal to do the following, you are recommended to use the Ali cloud app.

Google Authenticator is a common MFA application. You can select your desired MFA application. About Google authenticator For installation issues, please refer.

The steps described below are described in the case of Ali cloud app, which is similar to those of other MFA applications.

**Operation Steps**

1.  Log in to the Account Administration Security page using the Ali cloud master account.
2.  Under the virtual MFA menu, click Settings to enter the enable virtual MFA Device binding process.
3.  Complete the authentication via mailbox authentication, mobile phone authentication, or security issues, and go to the enable virtual MFA devices page, as shown in the following illustration.

     ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/12338/3500_en-US.png "Identity verification") 

4.  Open the Alibaba Cloud app in your phone and select**+** \> **Sweep Code add**Sweep code. The user is automatically added upon completion of the sweep code, and the Alibaba Cloud app displays the dynamic password for your current account, update every 30 seconds.

     ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/12338/3501_en-US.png "Dynamic Password") 

    **Note:** If your smart device does not support code sweep, then you can also select hand-to-hand information acquisition and manually enter it in the MFA application. How the MFA key is configured.

5.  Enter mfa on the enable virtual MFA appliance page Apply the two consecutive sets of dynamic passwords displayed in, and then click OK to enable. As shown in the following illustration:

     ![](images/3503_en-US.png "Enable virtual MFA Devices") 


So far, you have successfully enabled the MFA device.

## Login process after opening MFA {#section_nw3_xw2_xdb .section}

After opening MFA, you can only log in to Ali cloud after completing two-step verification. The procedure is as follows:

1.  Enter your login user name and password first when you log on to the console.
2.  After the password is verified, you also need to provide the dynamic verification code from the VMFA device, as shown in the figure below:

    ![](images/3503_en-US.png "Verify dynamic security verification code")


In your mobile Alibaba Cloud app, get and enter the dynamic verification code for your login account, you can log in to Ali cloud.

