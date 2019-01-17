# Creating Jenkins tasks

A Jenkins task runs a job in your integrated Jenkins instance.

Before using Jenkins tasks in your deployments, [add the UrbanCode Velocity plug-in to your Jenkins instance and configure an integration.](../../com.uvelocity.doc/topics/t_integration_Jenkins.md#) After integrating UrbanCode Velocity to Jenkins, you can add Jenkins jobs to you pipelines and releases.

To create a Jenkins task, complete the following steps:

1.   On the Deployment plan detail page, click **Create Task**. If you want to insert a task at a specific position in the plan, select a task before using the **Create Task**. The new task is inserted above the selected task.
2.   On the Create Task dialog box, in the **Type** list, select **Jenkins**. 
3.   In the **Name** field, enter a name for the task. 
4.   In the **Jenkins Job or Pipeline** field, select a job or pipeline. 
5.   In the **Duration** field, estimate the length of the task. 
6.   In the **Tags** list, attach a tag to the task. You can select multiple tags. To create a tag, type the tag name in list's text field.
7.   Click **Save**. The task is inserted into the deployment plan.

**Parent topic:** [Tasks](../../com.crelease.doc/topics/cr_task_ov.md)

