# Starting deployments manually

Starting deployments manually

You can start a deployment manually at any time, including deployments that are scheduled to start later.

Tasks in a deployment plan might be inapplicable for deployment. UrbanCode Deploy tasks are inapplicable if no version or environment is specified for the tasks. When you create UrbanCode Deploy tasks, you can delay selecting the environment and version by using the **Use Version** option. Before the deployment starts, ensure that all UrbanCode Deploy tasks are applicable for the upcoming deployment.

You can deliberately exclude tasks from a deployment. You can make tagged tasks inapplicable by excluding their tags from the deployment. Tasks with excluded tags are inapplicable for deployment.

Inapplicable tasks have the status of \`Not Applicable\`. Tasks with the \`Not Applicable\` status cannot be started. If an inapplicable task is a prerequisite for an active task, the dependency is ignored.

To start a deployment, complete the following steps:

1.   On the **Release** page, click the deployment plan that you want to use for the deployment. The deployment detail page is displayed. 
2.   To make tagged tasks inapplicable for the current deployment, click **Versions**, and then in the **Tags** area, clear the tags. If a task has more than one tag, clear all of them. 
3.   To select the version or environment for any inapplicable UrbanCode Deploy tasks, click **Versions**, and then select the environment and version. You can also change your choices for tasks that have their environments and versions already selected. 
4.   Click **Hide Not Applicable Tasks** to remove inapplicable tasks from the displayed task list. Hidden tasks are not removed from the deployment plan. 
5.   Click the **Start** action for one of the plan's eligible tasks. If more than one task is eligible, you can start any of them. Only eligible tasks display the start button. A started task has the status of \`In Progress\` until it is resolved. After a deployment starts, the plan's status changes to \`In Progress\`. The status remains \`In Progress\` until all tasks are resolved. When all tasks are resolved, the plan's status changes to \`Done\`.

**Parent topic:** [Running deployments](../../com.crelease.doc/topics/cr_deployRun_ov.md)

