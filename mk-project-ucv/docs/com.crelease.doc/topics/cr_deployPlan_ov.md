# Deployment plans

A deployment plan is a container for tasks. Tasks define the activities that your team runs to complete a software deployment.

You create a deployment plan by assigning a team to manage it and then adding tasks to the plan. Team members add tasks to the plan and run the tasks during deployments. The managing team also determines which UrbanCode Deploy applications are available. After an integration is configured, all applications that are managed by the team in UrbanCode Deploy are available.

When you use the Pipeline feature, releases and deployment plans are automatically generated as you add stages and applications to the pipeline. You can start deployments directly from the pipeline, or open the deployment plan and start the deployment by running an eligible task.

The tasks define the activities that the team performs to complete a deployment. You can create new tasks, copy tasks from other deployment plans or import tasks from CSV files. When you are satisfied with the plan, you can schedule a deployment. You can also run a deployment at any time by starting one of the plan's tasks.

Tasks are displayed on individual rows in deployment plans. Each row contains information that identifies the task and provides its status. Each row also contains action icons that are used during deployments, such as **Start** task or **Skip**.

By default, tasks run sequentially beginning with the first task, or topmost task, in the plan. After the first task finishes, the second task is eligible to run, and so forth. The order in which tasks are eligible to run is called the execution order.

The execution order can be modified by combining tasks into groups. [When you create a group](cr_task_groups.md#), you set the group's execution pattern, which can be sequential or parallel. If a group has a sequential execution pattern, its tasks run sequentially starting with the first task. A deployment plan's default execution pattern is sequential. If a group has a parallel execution pattern, tasks in the group can be started in any order and they can run simultaneously. If a plan consists entirely of parallel tasks, you can start any task regardless of its position in the list.

Task eligibility can also be effected by task dependencies. [If a task has any prerequisites](cr_task_depend.md#), it cannot start, even if it is otherwise eligible, until all prerequisite tasks are resolved.

Some tasks start automatically as soon as they are eligible to run, while other tasks are started manually. Whether a task starts automatically or not depends on its type. Manual tasks, as the name implies, are started manually. UrbanCode Deploy and Delayed-type tasks automatically start as soon as they are eligible.

Eligible tasks display a **Start Task** button. To start a deployment, you start one of a plan's eligible tasks. Scheduled deployments start automatically at the scheduled time if an eligible task is of a type that can start automatically, such as UrbanCode Deploy.

-   **[Managing deployment plans](../../com.crelease.doc/topics/cr_deployplan_manage.md)**  
You can change existing deployment plans and view current status from the deployment plan detail page.
-   **[Creating deployment plans](../../com.crelease.doc/topics/cr_deployPlan_create.md)**  
You can start with a blank plan that has no defined tasks, copy an existing plan, or start with a plan template. You can also auto-create them by assigning applications to pipelines. When you copy a plan or use a template, many tasks are already defined.
-   **[Importing tasks into deployment plans](../../com.crelease.doc/topics/cr_deployPlan_importTasks.md)**  
You can import tasks that are defined in comma-separated values \(CSV\) files into a deployment plan.
-   **[Copying deployment plans](../../com.crelease.doc/topics/cr_deployPlan_promote.md)**  
You can duplicate deployment plans by copying them.
-   **[Managing deployment plan templates](../../com.crelease.doc/topics/cr_deployPlan_template.md)**  
You can convert deployment plans to create deployment plan templates.
-   **[Archiving deployment plans](../../com.crelease.doc/topics/cr_deployPlan_archive.md)**  
You can remove deployment plans from releases by archiving them.

**Parent topic:** [Release management](../../com.crelease.doc/topics/c_node_releases.md)

