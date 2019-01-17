# Creating pipelines

Create a pipeline to use external tools and systems in your software releases.

Before you can use applications in pipelines, configure integrations with external tools. [Integrate with UrbanCode Deploy to run UrbanCode Applications with your pipelines](../../com.uvelocity.doc/topics/t_integration_UCD.md#).

[Configure an integration with Jenkins](../../com.uvelocity.doc/topics/t_integration_Jenkins.md#) to run Jenkins jobs with your pipeline.

The applications that are available to a pipeline depend on the team that is assigned to the pipeline. The applications that are managed by the team in UrbanCode Deploy are also available in UrbanCode Velocity.

To create a pipeline, complete the following steps:

1.   On the UrbanCode Velocity main menu, click **Pipelines**. 
2.   On the Pipelines page, click **Create pipeline**. 
3.   On the Crate a Pipeline window, in the **Name** field, enter a name for the pipeline. 
4.   In the **Team** list, select a team to manage the pipeline. Only teams to which the current user belongs are available.
5.   Clear the **Add default environments** box if you do not want to use the default environments, or stages. The default stages are DEV, QA, and PROD and can be used to logically model the stages of typical software development lifecycle. Each stage has an release associated with it automatically. You can add stages to a pipeline at any time.
6.   Click **Save**. The pipeline is created and the Pipeline detail page is displayed. You can see the releases associated with each stage on the Releases page. The new release names have the following format, `PipelineName|StageName release`.

[Add applications and jobs to your pipeline](cr_pipeline_manage.md#).

**Parent topic:** [Pipelines](../../com.crelease.doc/topics/cr_pipelines_ov.md)

