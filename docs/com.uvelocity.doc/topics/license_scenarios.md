# License scenarios

To continue using the product after the evaluation period, you must acquire a license.

UrbanCode™ Velocity supports floating- and token-type licenses. You can see the type of license that the server is using by logging onto the UrbanCode Velocity server, and accessing the License Management page, **Settings** \> **License management**.

**Note:** UrbanCode Velocity is also available as a hosted service. In this case, IBM hosts the server for you. For more information, see the [IBM Marketplace](https://www.ibm.com/us-en/marketplace/application-release-automation).

If both license types are available, UrbanCode Velocity uses the type of license with the highest priority. The license scenarios have the following priority, from highest to lowest:

1.  Concurrent sessions \(floating licenses\)
2.  Concurrent sessions \(token licenses\)

## Concurrent sessions \(floating licenses\)

An IBM Rational floating license is a license for a single software product that can be shared among multiple team members. However, the total number of concurrent users cannot exceed the number of floating licenses you purchase. In this scenario, when a user logs on to UrbanCode Velocity, a license is retrieved from a license server. If the first license server does not have available licenses, UrbanCode Velocity attempts to retrieve a license from the other license servers. 15 minutes after the user logs off, the server returns the license to the license server.

For this type of licensing, the **Floating Licenses** card on the License Management [page displays license usage statistics](licenseManage.md#).

## Concurrent sessions \(token licenses\)

The token-based license model means that you can buy a certain number of token licenses. In this scenario, when a user logs on, UrbanCode Velocity retrieves thirteen tokens from a license server. If the first license server does not have enough tokens available, the UrbanCode Velocity server attempts to retrieve licenses from the other license servers. Each user requires thirteen tokens. 15 minutes after the user logs off, the server returns the licenses to the license server.

For this type of licensing, the **Token Licenses** card on the License Management [page displays license usage statistics](licenseManage.md#).

