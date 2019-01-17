# Using properties

You can use properties in deployment plans, REST API endpoints, and external systems, such as ServiceNow.

## Property examples

Use the following syntax to reference a property: ``${propertyName}``. To escape the syntax pattern, use two dollar-sign symbols, `$${...}`. You set property values with the deployment plan's **Properties** tab, REST API endpoints, or external systems, such as ServiceNow.

The following table describes how to properties with task types.

|Task type|Usage|
|---------|-----|
|**ServiceNow**| You can use the [ServiceNow](cr_taskType_serviceNow.md#) **Output property** field in a create change request action to store the change request ID in a property, for example, ``service_now_prod_ticket_id``. Then, with another task, update the change request by referencing the property in the **System ID** field like this, ``${service_now_prod_ticket_id}``.

 |
|**Email**| You can reference a system property in the [email task](cr_taskType_email.md#) **Subject** field like this example: ``${sys:release.name}` is complete!`

 |
|**Delayed**| You can reference a [delay task](cr_taskType_delay.md#) property in the **Delay property** field like this example: \``${prodTarget}``. In this example, the task delays until the value in the ``${prodTarget}`` property is reached.

 |

## System properties

System properties enable you to access information about the parent release of a deployment plan. System properties can be referenced by any property-enabled task that is part of a release.

The following table contains the available system properties:

|Property|Description|
|--------|-----------|
|`${sys:release.name}`|The value in the release's **Name** field.|
|`${sys:release.description}`|Contains the content of the release's **Description** field.|
|`${sys:release.start}`|Release's **Start time**.|
|`$${sys:release.end}`|Contains the content of the release's **End time** field.|

In the **Email message** field of an email-type task, you can reference system properties like this example: `Deployment for release `${sys:release.name}` - `${sys:release.description}` is complete.`

You can reference a system property in a ServiceNow task's **Short description** field like this example: `Staging deployment `${sys:release.name}`\`.

**Parent topic:** [Using properties](../../com.crelease.doc/topics/cr_properties_ov.md)

