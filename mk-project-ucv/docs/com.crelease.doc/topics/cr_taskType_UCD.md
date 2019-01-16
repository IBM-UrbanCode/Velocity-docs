# Creating UrbanCode Deploy tasks

Use UrbanCode Deploy tasks to run UrbanCode Deploy applications.

Before you can use UrbanCode Deploy tasks in pipelines and deployment plans, [you must first configure an UrbanCode Deploy integration](../../com.uvelocity.doc/topics/t_integration_UCD.md#).

The applications that are available to a deployment plan depend on the team that is assigned to the plan. The applications that are managed by the team in UrbanCode Deploy are also available in UrbanCode Velocity.

To create this task type, specify the application's process, version, and environment. You can set the version and environment at design time or select them at run time. When you run this task, the application runs in the integrated UrbanCode Deploy instance. During deployments, UrbanCode Deploy tasks start automatically when they become eligible to run.

To create an UrbanCode Deploy task, complete the following steps:

1.   On the Deployment plan detail page, click **Create Task**. If you want to insert a task at a specific position in the plan, select a task before using the **Create Task**. The new task is inserted above the selected task.
2.   On the Create Task dialog box, in the **Type** list, select **UrbanCode Deploy**. 
3.   In the **Name** field, enter a name for the task. 
4.   In the **Application Name** list, select an application. 
5.   In the **Process** list, select an application process. Processes that belong to the selected UrbanCode Deploy application are available.
6.   In the **Environment** list, select an application environment. Environments that belong to the selected UrbanCode Deploy application are available. To postpone selecting an environment until you are ready to run the deployment, select **Use Version** tab.
7.   In the **Version** list, select an application version. Versions refer to IBM UrbanCode Deploy application snapshots. Versions that belong to the selected application are available. To postpone selecting a version, select **Use Version Tab**. If the application process does not require a version, select **No Version**. You might select this last option if you are running a configuration-type process that does not require components.
8.   In the **Duration \(minutes\)** field, enter the number of minutes that you expect the task to run until it is completed. The estimated duration is used to calculate expected deployment times.
9.   In the **Tags** list, attach a tag to the task. You can select multiple tags. To create a tag, type the tag name in list's text field.
10.  Click **Save**. The task is inserted into the deployment plan.

After the task is created, the plan's **Version** tab is updated with information about the application. If you selected **Use Version Tab** for the application environment and version, use the **Version** tab to set those options before running the deployment.

**Parent topic:** [Tasks](../../com.crelease.doc/topics/cr_task_ov.md)

