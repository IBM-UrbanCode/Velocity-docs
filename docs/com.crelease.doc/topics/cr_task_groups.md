# Creating task groups

You can combine two or more tasks into a task group. When you create a group, you define the whether the group task are executed sequentially or in parallel.

Tasks can run in a parallel or sequential pattern. When you create the task you, you decide the execution pattern. Tasks without dependencies can execute in any order or simultaneously which is parallel execution. Tasks that must execute in specific order are sequential execution. Tasks are done in list-order starting with the first or top-most task.

You can embed groups within other groups. A sequential-pattern group can be embedded within a parallel-pattern group, and vice versa. However, you cannot embed a sequential-pattern group within another sequential group, or a parallel-pattern group within another parallel group.

1.   On the details page for a deployment, select two or more tasks. 
2.   Depending on the type of group you want to create, complete one of the following. 

    -   To create a parallel group, click the Parallel icon \) ![sequential icon](../images/para-icon.png)\). If you cannot create a parallel group with the selected tasks, the icon is disabled. For example, you cannot create a parallel group if all the selected tasks are already in a parallel group.
    -   To create a sequential group, click the Sequential icon \( ![sequential icon](../images/seq-icon.png)\).
    The group is formed and a group select bar is added to the deployment plan. If you selected discontiguous tasks, the tasks form a contiguous list starting with the topmost selected task.


**Parent topic:** [Tasks](../../com.crelease.doc/topics/cr_task_ov.md)

