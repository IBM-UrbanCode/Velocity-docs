# Managing licenses

Apply your license after the Standard Edition 60-day evaluation period ends.

Unless you configure a license when you install the Standard Edition, a 60-day evaluation period begins. During evaluation, you can use all product features. By the end of the 60-day trial, you must apply your Flexera FlexNet license. You can apply a license at any time; you do not have to wait for the end of the trial period.

**Note:** The UrbanCode™ Velocity Community Edition is free to use and does not require a license.

To complete license configuration, you install an SSH private key, which UrbanCode Velocity uses to encrypt communication with the license server. UrbanCode Velocity sends the SSH public key to FlexNet where it us used to decrypt messages.

Apply your license by connecting UrbanCode Velocity to a Flexera Flexnet server. The user applying the license must be in a role with administrative privileges.

 

1.   On the UrbanCode Velocity Web application, click **Settings**, and then, on the Settings page, select **License Management**. 
2.   On the License management page, click **Connect Server**. 
3.   On the License server connection page, in the **License server** field, specify the URL to the FlexNet server. 
4.   In the **Private key** box, paste your private RSA key, and then click **Save**. 
5.   Click **Save**. 

To modify, add, or remove license servers, click **Edit**.

**Parent topic:** [Administration](../topics/c_node_admin.md)

