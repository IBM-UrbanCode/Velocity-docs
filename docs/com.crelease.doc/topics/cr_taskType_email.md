# Creating email tasks

An email task sends an email message when the task runs. You specify the email's recipients and message when you create the task. Email tasks are auto tasks and run as soon as they are eligible.

Before using email tasks in your deployments, [setup an email server.](../../com.uvelocity.doc/topics/t_admin_emailServer.md#)

To create an email task, complete the following steps:

1.   On the Deployment plan detail page, click **Create Task**. If you want to insert a task at a specific position in the plan, select a task before using the **Create Task**. The new task is inserted above the selected task.
2.   On the Create Task dialog box, in the **Type** list, select **Email**. 
3.   In the **Name** field, enter a name for the task. 
4.   In the **Recipients** field, enter or select the email's recipient. The list of available recipients includes the users and groups who are members the team that manages the task. You can also type the email addresses of non-team members. You can specify multiple recipients.
5.   In the **Email subject** field, enter the email topic. You can use properties in this field.
6.   In the **Email message** field, enter or paste the email message. You can use properties in this field. You example, you might notify email recipients that a release is started by using a message similar to this one, "The ``${sys:release.name}`` release has started." [See the Properties reference for information about properties](cr_properties_ov.md#).
7.   Click **Save**. The task is inserted into the deployment plan.

When the task runs, the recipients receive an email from UrbanCode Velocity with the subject you specified when you created the task.

**Parent topic:** [Tasks](../../com.crelease.doc/topics/cr_task_ov.md)

