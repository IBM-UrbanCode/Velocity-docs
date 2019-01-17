# Running deployments with pipelines

Add applications and jobs to your pipeline, and add or modify stages.

Pipeline stages run sequentially from left to right. When you run a stage deployment, tasks run in the order that they are assigned by the pipeline. You can run a deployment at any time by using the **Run** button, or you can schedule a deployment for a later time.

To run a deployment with a pipeline, complete the following steps:

1.   On the Pipeline detail page, click the stage **Run** button. A deployment starts that uses the deployment plan associated with the stage. Tasks for every application on the stage are run in order starting with the first or top application. You can view the deployment's progress by using the supplied link.
2.   To schedule a deployment for a stage, click **Schedule deployment** on the context menu for the stage, and then select a date and start time. A deployment for the stage deployment plan will start at the scheduled time. Pipeline scheduled deployments are displayed on the calendar.
3.   On the Release page, select the release associated with the pipeline stage, and then open the default deployment plan. Start a deployment by starting one of the eligible tasks, or click **Edit** schedule a deployment. As with other deployment plans, you can add and delete tasks on the pipeline-generated plan at any time. On the release or plan page, use the **Go to** link to open the associated pipeline or stage.

**Parent topic:** [Pipelines](../../com.crelease.doc/topics/cr_pipelines_ov.md)

