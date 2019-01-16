# Managing licenses

To use licenses, you install a Rational® Common Licensing server, import your license keys, and link UrbanCode™ Velocity to the license server.

Ensure that you have a Rational Common Licensing server with licenses for UrbanCode Velocity.

The user applying the license must be in a role with administrative privileges.

For information about the types of licenses, see [License scenarios](license_scenarios.md).

1.   On the UrbanCode Velocity Web application, click **Settings**, and then, on the Settings page, select **License Management**. 
2.   On the License management page, click **Connect Server**. 
3.   On the License server connection page, in the **License server** field, specify the connection information for the license server, and then click **Save**. You can specify the port and host name or IP address for the license server, such as `27000@RCLServer.example.com`. To avoid problems when a license server is not available, you can specify multiple license servers. In this case, separate each address with colons on Linux and UNIX or semicolons on Windows, as in the following example: `27000@RCLServer.example.com;27000@backupRCLServer.example.com`.
4.   Click **Save**. The License management page displays license usage for your license types.

To modify, add, or remove license servers, click **Edit**.

