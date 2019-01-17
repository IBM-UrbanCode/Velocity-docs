# Resolving tasks

Complete a deployment by resolving the tasks in the deployment plan.

A started task is resolved when its status changes to \`Complete\`, \`Failed\`, or \`Skipped\`.

You resolve manual tasks by using the appropriate status action. Auto tasks, such as UrbanCode Deploy tasks or Jenkins, change status automatically as conditions change. However, you can manually resolve auto tasks. For example, you might manually fail an UrbanCode Deploy task that is taking too long to complete.

To resolve a started task, apply one of the following statuses:

-   Click **Complete** to finish the task. \`Complete\` means that the task finished with the expected results.
-   Click Skip to skip the task for the current deployment.
-   Click **Fail** to end the task. \`Fail\` means that the task did not finish or finished with unexpected results.
-   Click **Task Reopen** to open a resolved a task. If all tasks are completed, reopening a task reopens the deployment.

**Parent topic:** [Running deployments](../../com.crelease.doc/topics/cr_deployRun_ov.md)

