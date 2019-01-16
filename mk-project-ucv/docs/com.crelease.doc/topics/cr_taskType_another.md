# Creating run another plan tasks

A run another plan task runs a deployment for another deployment plan.

The targeted plan can be created from a template or a tag. If you use a template, the template and the targeted plan must be in the same release as the run another plan task.

To create a run another plan task, complete the following steps:

1.   On the Deployment Plan Details page, click **Create Task**. If you want to insert a task at a specific position in the plan, select a task before you use the **Create Task** action. The new task is inserted before the selected task. 
2.   In the Create Task dialog box, in the **Type** list, select Run **Run another plan**. 
3.   In the **Name** field, enter a name for the task. 
4.   In the **How do you want to choose another plan** area, select an option. If you choose, **By template**, the template and associated deployment plan must be in the same release as the task's parent plan. If you choose, **By tag**, the tagged deployment plan must be in the same release as the task's parent plan.
5.   In the **Plan Template Name** list, select a deployment plan template. The template and associated deployment plan must be in the same release as the task's parent plan. 
6.   In the **Tags** list, attach a tag to the task. You can select multiple tags. To create a tag, type the tag name in text box.
7.   Click **Save**. The task is inserted into the deployment plan.

When the task runs, a deployment starts for the deployment plan that was created from the selected template or tagged plan. If multiple plans in the release event are eligible, deployments start for all of them. While the other deployments run, status information is provided by the run another plan task. Expand the task to see the status information. You can open the other deployments by using links on the task. While the other deployments run, the run another plan task has a status of **In Progress**.

**Parent topic:** [Tasks](../../com.crelease.doc/topics/cr_task_ov.md)

