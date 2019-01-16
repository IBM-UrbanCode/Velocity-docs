# Pipelines

A pipeline is a sequence of stages that retrieve input and run applications and jobs, such as builds, tests, and deployments.

Stages organize input and jobs as your code is built, deployed, and tested. Stages accept input from either source control repositories \(SCM\) or other external applications, such as UrbanCode Deploy. When you create your first stage, some default settings are set for you on the **Input** stage.

You add applications to the pipeline from external tools that are integrated with UrbanCode Velocity, such as Jenkins, and UrbanCode Deploy. Stages and jobs run serially; they enable flow control for your work. For example, you might place a test stage before a deployment stage. You can ensure that if the tests in the test stage fail, the deployment stage won't run.

You can define stage environment properties that can be used in all jobs. For example, you might define a `TEST_URL` property that passes a single URL to deploy and test jobs in a single stage. The deploy job would deploy to that URL, and the test job would test the running app at the URL.

Each pipeline stage automatically has a release and deployment plan associated with it. You do not have to manually create a release beforehand. As you add applications to a stage, a task is automatically added to the default deployment plan. For example, if you add a UrbanCode Deploy application to a stage, and UrbanCode Deploy task is added to the deployment plan.

When you run a pipeline application, a deployment starts that uses the associated deployment plan. You can monitor the progress of the deployment with links provided on the stage card.

-   **[Creating pipelines](../../com.crelease.doc/topics/cr_pipeline_create.md)**  
Create a pipeline to use external tools and systems in your software releases.
-   **[Managing pipelines](../../com.crelease.doc/topics/cr_pipeline_manage.md)**  
Add applications and jobs to your pipeline, and add or modify stages.
-   **[Running deployments with pipelines](../../com.crelease.doc/topics/cr_pipeline_run.md)**  
Add applications and jobs to your pipeline, and add or modify stages.

