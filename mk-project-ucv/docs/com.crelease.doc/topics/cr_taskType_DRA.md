# Deployment risk analysis tasks

Use deployment risk analysis \(DRA\) tasks to enforce quality standards and gates.

Configure a Jenkins job that uses the [IBM Cloud DevOps Insights service](https://console.bluemix.net/docs/services/DevOpsInsights/about_risk.html#about-deployment-risk). Reference that job with the DRA task.

1.   On the Deployment plan detail page, click **Create Task**. If you want to insert a task at a specific position in the plan, select a task before using the **Create Task**. The new task is inserted above the selected task.
2.   On the Create Task dialog box, in the **Type** list, select **Deployment Risk Analysis**. 
3.   In the **Name** field, enter a name for the task. 
4.   In the **API Key** field, enter the API key for your IBM Cloud DevOps Insights service. 
5.   In the **Application name** field, enter the name of the DevOps Insights application. 
6.   In the **Jenkins Job or Pipeline** field, select pipeline or job that uses the DRA application. 
7.   In the **Build Number** field, enter the Jenkins build number. 
8.   Click **Save**. 

**Parent topic:** [Tasks](../../com.crelease.doc/topics/cr_task_ov.md)

