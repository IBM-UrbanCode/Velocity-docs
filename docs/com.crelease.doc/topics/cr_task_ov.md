# Tasks

A task represents a business-meaningful activity that is associated with a software deployment. Each task is defined on a separate row in a deployment plan. During a deployment, you run tasks defined in the deployment plan to complete the deployment.

Most tasks have a starting and ending point, and a measurable duration. A task can have other attributes depending on its type. A task can be of one of following types:

-   **Delayed**

    Represents a critical event that happens at a specific time.

-   **Deployment Risk Analysis**

    use the IBM Cloud service DevOps Insights..???

-   **Email**

    Sends an email message.

-   **Header/Note**

    an organizational element. For example, you might use a header task to identify a task group.

-   **Jenkins**

    Runs a Jenkins job or pipeline.

-   **Manual**

    Represents any activity that is associated with a software deployment, such as taking a server offline or updating a database. Users assigned manual tasks can be sent email notifications when their tasks start or fail.

-   **Run another plan**

    Runs deployments for other deployment plans participating in the same release event. This is an experimental task type.

-   **ServiceNow**

    Creates and manages ServiceNow tickets.

-   **UrbanCode Deploy**

    Represents an IBM UrbanCode Deploy application. Use this task to run UrbanCode Deploy applications.

-   **Wait for approval**

    Pauses a deployment until the designated users approve the task.


You can add tasks to deployment plans by one of the following methods:

-   Create a new task
-   Import from CSV files that are created by UrbanCode Release or another application
-   Copy tasks from other deployment plans

Additionally, tasks are auto-created when you add an application to a [pipeline](cr_pipelines_ov.md#).

-   **[Managing tasks](../../com.crelease.doc/topics/cr_task_manage.md)**  
A list of associated tasks can be viewed from a deployment plan page. The list of tasks include details about the task. You use action icons to change the task's status during a deployment, such as start or skip a task.
-   **[Creating tasks](../../com.crelease.doc/topics/cr_task_create.md)**  
By default, new tasks are inserted at the bottom of the deployment plan. After a task is created, you can move it, or copy it and paste it into another deployment plan. [You can also create dependencies with other tasks](cr_task_depend.md#).
-   **[Managing task dependencies](../../com.crelease.doc/topics/cr_task_depend.md)**  
You can make a task a prerequisite for other tasks. If a task is a prerequisite, dependent tasks cannot start, even if they are otherwise eligible, until the prerequisite task is resolved.
-   **[Creating task groups](../../com.crelease.doc/topics/cr_task_groups.md)**  
You can combine two or more tasks into a task group. When you create a group, you define the whether the group task are executed sequentially or in parallel.
-   **[Managing task groups](../../com.crelease.doc/topics/cr_task_groups_manage.md)**  
You can combine two or more tasks into a task group. When you create a group, you define the whether the group task are executed sequentially or in parallel.
-   **[Managing task tags](../../com.crelease.doc/topics/cr_task_tags.md)**  
Tags are organizing elements that you can add to tasks. You can filter deployment plans by tag. For example, during a deployment to a production environment, you might disable tasks with the \`DEV\_only\` tag, which is intended to be used only in development environments.
-   **[Creating run another plan tasks](../../com.crelease.doc/topics/cr_taskType_another.md)**  
A run another plan task runs a deployment for another deployment plan.
-   **[Creating delay tasks](../../com.crelease.doc/topics/cr_taskType_delay.md)**  
Delayed-type tasks represent milestones or critical events during a deployment. With delayed tasks, you can ensure that important tasks start at the expected time. Typically, delayed tasks are prerequisites for other important tasks.
-   **[Deployment risk analysis tasks](../../com.crelease.doc/topics/cr_taskType_DRA.md)**  
Use deployment risk analysis \(DRA\) tasks to enforce quality standards and gates.
-   **[Creating email tasks](../../com.crelease.doc/topics/cr_taskType_email.md)**  
An email task sends an email message when the task runs. You specify the email's recipients and message when you create the task. Email tasks are auto tasks and run as soon as they are eligible.
-   **[Creating header/note tasks](../../com.crelease.doc/topics/cr_taskType_header.md)**  
Header tasks represent organization elements that you can add to deployment plans. If you create a task group, you might identify the group with a header task. Header tasks can have dependencies like any other task.
-   **[Creating Jenkins tasks](../../com.crelease.doc/topics/cr_taskType_Jenkins.md)**  
A Jenkins task runs a job in your integrated Jenkins instance.
-   **[Creating manual tasks](../../com.crelease.doc/topics/cr_taskType_manual.md)**  
Manual tasks represent some activity that is associated with a software release. Manual tasks have a start point, end point, and a measurable duration.
-   **[Creating ServiceNow tasks](../../com.crelease.doc/topics/cr_taskType_serviceNow.md)**  
A ServiceNow task can create and update ServiceNow change requests.
-   **[Creating UrbanCode Deploy tasks](../../com.crelease.doc/topics/cr_taskType_UCD.md)**  
Use UrbanCode Deploy tasks to run UrbanCode Deploy applications.
-   **[Creating wait for approval tasks](../../com.crelease.doc/topics/cr_taskType_waitForApproval.md)**  
A Wait for approval task pauses a deployment until a designated user provides approval. Email notifications are sent to users when the task starts.

**Parent topic:** [Release management](../../com.crelease.doc/topics/c_node_releases.md)

