# Creating tasks

By default, new tasks are inserted at the bottom of the deployment plan. After a task is created, you can move it, or copy it and paste it into another deployment plan. [You can also create dependencies with other tasks](cr_task_depend.md#).

Tasks can be added to a deployment by creating a new task or importing an existing task.

After you save a task, action icons are displayed for the task. You use action icons to change the task's status during a deployment. All tasks have the **Skip** action icon. Other icons, such as **Start**, are displayed when the context is appropriate for them.

1.   From the deployment detail page, click **Create task** to create one or more tasks. 
2.   Select the type of task. This field is required. The following are values for this field.
    -   Delayed
    -   Deployment Risk Analysis
    -   Email
    -   Header / Note
    -   Jenkins
    -   Manual
    -   Run another plan
    -   ServiceNow
    -   UrbanCode Deploy
    -   Wait for approval
3.   Type a name for the task in the **Name** field. 
4.   Complete other fields as appropriate. The required and optional fields are dependent on the type of task being created.
5.   Click **Save and create another** to create additional tasks. Click **Save** when finished. 

**Parent topic:** [Tasks](../../com.crelease.doc/topics/cr_task_ov.md)

