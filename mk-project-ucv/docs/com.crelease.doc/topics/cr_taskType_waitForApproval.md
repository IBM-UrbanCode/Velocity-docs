# Creating wait for approval tasks

A Wait for approval task pauses a deployment until a designated user provides approval. Email notifications are sent to users when the task starts.

Before using email tasks in your deployments, [setup an email server.](../../com.uvelocity.doc/topics/t_admin_emailServer.md#)

To create a wait for approval task, complete the following steps:

1.   On the Deployment plan detail page, click **Create Task**. If you want to insert a task at a specific position in the plan, select a task before using the **Create Task**. The new task is inserted above the selected task.
2.   On the Create Task dialog box, in the **Type** list, select **Wait for approval**. 
3.   In the **Name** field, enter a name for the task. 
4.   In the **Approval prompt** field, enter the text that you want to include in the email message. The text is displayed in the **Task Details** section of the email.
5.   In the **Approvers** list, select the users or groups designated to approve the task. Team members and groups are available to choose.
6.   In the **Required approver**area, specify whether all the approvers must approve the task, or a single approver is sufficient. 
7.   Click **Save**. The task is inserted into the deployment plan.

When the task runs, email notifications are sent to the selected approvers. The deployment plan cannot progress until the task is approved or skipped. Approval is granted by completing the task in the deployment plan.

**Parent topic:** [Tasks](../../com.crelease.doc/topics/cr_task_ov.md)

