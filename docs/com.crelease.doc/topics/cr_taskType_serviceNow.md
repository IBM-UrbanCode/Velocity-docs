# Creating ServiceNow tasks

A ServiceNow task can create and update ServiceNow change requests.

ServiceNow task prerequisites:

-   ServiceNow tasks work with Internet-accessible instances of ServiceNow, such as `my_instance.service-now.com`.
-   ServiceNow tasks work with the Jakarta release of ServiceNow, and references the current API version.
-   The user supplying credentials for the task must have access to the ServiceNow API, and permission to see and modify all change request fields. At a minimum, the user must be in a ServiceNow role that has the Create Change permission.

A ServiceNow task can perform one of the following actions:

-   **Create** creates a ServiceNow change request. You can set the values for all request fields, and pass the request ID to update, and wait tasks.
-   **Update** can update the values for any request field.
-   **Wait** waits for a particular value in a specific field. The field can be any field on the change request.

A ServiceNow task can include ServiceNow properties and UrbanCode Velocity properties. ServiceNow properties have the following syntax: `propertyName=value`.

[This short video describes how to use ServiceNow with UrbanCode Velocity.](https://youtu.be/Sf7WBNv0RtA)

To create a ServiceNow task, complete the following steps:

1.   On the Deployment plan detail page, click **Create Task**. If you want to insert a task at a specific position in the plan, select a task before using the **Create Task**. The new task is inserted above the selected task.
2.   On the Create Task dialog box, in the **Type** list, select **ServiceNow**. 
3.   In the **Name** field, enter a name for the task. 
4.   In the **Tags** list, attach a tag to the task. You can select multiple tags. To create a tag, type the tag name in list's text field.
5.   In the **Connection settings** area, enter the URL of the ServiceNow instance, and the user ID, and password of the ServiceNow user. 
6.   In the **Action** list, select the action type for the task. The action types are defined in this list:
    -   The **create**action creates a ServiceNow change request with the properties defined in the task.
    -   The **update** action modifies properties in change request.
    -   The **wait** action waits for a specific value in a change request field.
7.   Complete the action-specific parameters, as described in the following tables: 

    |Create action|Description|
    |-------------|-----------|
    |Request type|You can use the ServiceNow default types or a user-created type. Default types are normal, emergency, and standard. Normal requests pass through all stages of the ServiceNow state model. Standard types are pre-authorized and skip the Assess and Authorize states. Emergency types skip the Assess state.|
    |Short description|The text you enter is displayed in the Short description field of the ServiceNow change request.|
    |Assignment group|The ServiceNow agent or group responsible for resolving the change request. Possible assignees include agents and groups available to the ServiceNow instance.|
    |Additional properties|The ServiceNow properties set by this task. Each property must be on its own line. For example, a simple request might include the following fragments: \`approval=requested\`.|
    |Output property|UrbanCode Velocity property that contains the change request ID. For example, if you specify ``service_now_stage_ticket_id``, you can use the property with update and wait actions to identify the ticket.|

    |Update action|Description|
    |-------------|-----------|
    |System ID|The ID of the ServiceNow change request. If you capture the ID with a create action **Output property** field, you can use it here. For example, if you specify ``service_now_stage_ticket_id`` in the **Output property** field of a create action, you can use the ID by specifying ``${service_now_stage_ticket_id}``. [See the Properties reference for information about properties](cr_properties_ov.md#).|
    |Additional properties|The ServiceNow properties set by this task. Each property must be on its own line. For example, to update the state of the change request, you can specify or ``state=-1``.|

    |Wait action|Description|
    |-----------|-----------|
    |System ID|The ID of the ServiceNow change request. If you capture the ID with a create action **Output property** field, you can use it here. For example, if you specify ``service_now_stage_ticket_id`` in the **Output property** field of a create action, you can use the ID by specifying ``${service_now_stage_ticket_id}``.|
    |Field|The name of the affected field in the ServiceNow change request. The value in the field is checked for updates by the interval defined by the Check request interval field. For example, if you are checking the**approval** field, you might specify``approval``.|
    |Value|The value expected in the ServiceNow field as defined by the**Field** property. For example, if you are checking the **approval** field, you might specify ``approved``. In this example, when the value in the **approval** field changes to ``approved``, the task completes successfully.|
    |Check request interval|The value defines how frequently ServiceNow is checked for updates. The value represents minutes. The default value is \`1\`, which mean ServiceNow is polled every minute.|

    When the task starts, it has the status of **In progress**. The status changes to **Complete** when the related ServiceNow action is resolved.


The ServiceNow change request life cycle is referred to as the state model. As a change request is used, it progresses through the various states of model. The state of a closed request is 'closed', for example.

In UrbanCode Velocity, ServiceNow tasks are frequently used to change the state of a request. To modify a request state, you use the ServiceNow \`state\` property. For example, to change the state of a request to Review, you can specify **\`state=0\`** in the **Additional properties** field of an Update action.

The following table provides the values for the default states for the normal request type. For more information, see the configure dictionary for the state property in the ServiceNow documentation.

|State|Value|
|-----|-----|
|New|-5|
|Assess|-4|
|Authorize|-3|
|Scheduled|-2|
|Implement|-1|
|Review|0|
|Closed|3|
|Canceled|4|

**Parent topic:** [Tasks](../../com.crelease.doc/topics/cr_task_ov.md)

