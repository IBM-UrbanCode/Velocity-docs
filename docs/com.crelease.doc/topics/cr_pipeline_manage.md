# Managing pipelines

Add applications and jobs to your pipeline, and add or modify stages.

You can add environments, or stages, at any time and rearrange them as needed. Each application that you add to a pipeline is inserted onto a separate row below the last application. As you add apps and jobs to stages, tasks are added to the associated deployment plan in the order that they appear in the pipeline.

To modify a pipeline, complete the following steps:

1.   On the Pipeline detail page, click **Add Environment** to create an environment, or stage. Drag the stage to a new location in the pipeline. You can re-order the stages except for the first stage, **Input**. To rename the stage, select **Edit environment** from the stage context menu.
2.   To map an [UrbanCode Deploy application environment](../../com.insights.doc/topics/t_admin_environments_map.md#) to the stage, complete the following steps: 
    1.   For the application where you want to add the environment, click ![Add button](../images/event-add.png), and then select **Manage logical environment**. 
    2.   On the Map app environments to logical environment window, select an environment, and then click **Save**. The environment is added to the stage.
    3.   To change the mapped environment, select **Edit application environment**. 
    4.   To delete the environment, select **Delete**. 
3.   Click **View deployment plan** on the stage context menu fo view the deployment plan associated with the stage The deployment plan detail page is displayed. As you add apps and jobs to the pipeline, associated tasks are inserted into the plan. You can also add tasks directly to the plan. For example, you might add a [DRA task](cr_taskType_DRA.md#) to the top of the plan to ensure deployments can only start after the associated DRA tests are satisfied.
4.   Click **Schedule deployment** to schedule a deployment for a stag, and then specify the date and time. 
5.   To add the stage to a release, complete the following steps: 
    1.   Click **Join release** for the stage that you want to add to a release. 
    2.   On the Map app environments to logical environment window, select a release, and then click **Save**. The release is added to the stage, as shown in the following figure.

         ![Stage with scheduled release](../images/pipeline-release.png "Stage with scheduled release") 

        To view the release, click the release link.

6.   Click **Delete** to delete an app or job, and then confirm the deletion by entering the name of the application. The application is removed from the pipeline along with all apps and jobs defined for it.
7.   Click **Add app** to add an application to the pipeline, and then, on the Add apps window, select the application type. Depending on the type, complete one of the following options:

    -   If you select **Jenkins**, enter a name for the application, and then click **Save**.
    -   If you select **UrbanCode Deploy**, select an UrbanCode Deploy application, and then click **Continue**. Next, select a process, and then click **Save**.
    The application is added to the pipeline on a new row. If you selected multiple applications, each has its own row.


[Run a deployment for a pipeline stage](cr_pipeline_run.md#).

**Parent topic:** [Pipelines](../../com.crelease.doc/topics/cr_pipelines_ov.md)

