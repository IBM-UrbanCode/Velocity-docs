# Running deployments

Complete deployments by resolving the tasks in a deployment plan.

A deployment starts when one of the plan's eligible tasks starts. A scheduled deployment starts automatically at the scheduled time if one of its eligible tasks is an auto task, such as UrbanCode Deploy tasks. Otherwise, begin a deployment by starting one of the plan's eligible tasks. If the plan contains several eligible tasks, you can start any of them. You can manually start a deployment at any time. You can manually start a scheduled deployment before its scheduled time.

The deployment plan's execution pattern determines when tasks are eligible to start. If the plan has the sequential execution pattern, which is the default pattern, tasks become eligible in the order in which they are listed in the plan, starting with the first task. After the first task resolves, the second task becomes eligible. Start eligible manual tasks by clicking the task's **Start** button. Auto tasks, such as UrbanCode Deploy tasks, start automatically as soon as they become eligible.

The tasks in a group with a parallel execution pattern become eligible simultaneously. Tasks in parallel groups can be started in any order. Nested groups and tasks with ad hoc dependencies can affect the execution pattern.

You can modify a deployment plan after you start a deployment. You can add, delete, and modify tasks.

After all tasks are resolved, the deployment is complete. A task is resolved if it has a status of \`Complete\`, \`Failed\`, or \`Skipped\`. If you reopen a task or add a task after the deployment is complete, the deployment's status changes to \`In Progress\`.

-   **[Starting deployments manually](../../com.crelease.doc/topics/cr_deployRun_manual.md)**  
Starting deployments manually
-   **[Resolving tasks](../../com.crelease.doc/topics/cr_deployRun_taskResolve.md)**  
Complete a deployment by resolving the tasks in the deployment plan.
-   **[Importing tasks into deployment plans](../../com.crelease.doc/topics/cr_deployPlan_importTasks.md)**  
You can import tasks that are defined in comma-separated values \(CSV\) files into a deployment plan.
-   **[Running scheduled deployments](../../com.crelease.doc/topics/cr_deployRun_scheduled.md)**  
A scheduled deployment starts automatically at its scheduled time if any of its auto tasks are eligible to start.

**Parent topic:** [Release management](../../com.crelease.doc/topics/c_node_releases.md)

