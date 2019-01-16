# Importing tasks into deployment plans

You can import tasks that are defined in comma-separated values \(CSV\) files into a deployment plan.

You can import tasks from CSV files that are exported from UrbanCode Release or another application capable of creating CSV files. When you import a deployment plan from UrbanCode Release, segments are converted into groups with the same execution pattern as the original segments. Segment tasks are bracketed by note-type Start Segment and End Segment tasks. Task dependencies are preserved during import. Segment dependencies are represented by dependencies to End Segment tasks.

To learn about deployment plans exported from UrbanCode Release, download the SamplePlan.csv file from the Import Tasks dialog.

**Note:** When you import tasks, tasks that are already defined in the deployment plan are overwritten and replaced by the tasks in the CSV file.

The following table contains the fields that define a task in an UrbanCode Release deployment plan. The first row in the CSV file contains the column headers, which correspond to the table's Field column. The rows after the first row contain task data, one task per row. The order of the columns does not matter.

**Note:** If you are creating tasks in a CSV file, you must include the required fields that are identified by the asterisk character \(\*\) in the following table.

|Field|Description|
|-----|-----------|
|segmentName\*|The name segment. Required field.|
|name\*|The name of the deployment task. Required field.|
|type\*|Task type. Possible values are note, waitfortimetask, ucdtask, or manual. During import, if the field contains an unrecognized value, the task is assigned the manual type.|
|description|Description of the deployment plan.|
|property:processId|The process ID in IBM UrbanCode Deploy that corresponds to the task.|
|property:task-environments|Application environments available to the task.|
|property:mailRecipients|Email addresses of users who receive email messages when notifications are sent.|
|taskTagNames|The names of the tags that are associated with the task.|
|taskPrequisiteIds|A comma-separated list of IDs for tasks that must complete before this task can start.|
|segmentPrerequisitelds|A comma-separated list of IDs for segments with which the current segment has dependencies.|
|taskPrequisiteNames|A comma-separated list of names for tasks that must complete before this task can start.|
|segmentPrerequisiteNames|A comma-separated list of names for segments with which the current segment has dependencies.|
|assignedUserEmail|Email address of the user who is assigned to the current task.|
|executorGroup|User group assigned to the current task.|
|segmentPattern|Execution pattern of the selected segment.|

Complete the following steps to import tasks into a deployment plan:

1.   On the Deployment Plan Details page, click **Import Tasks**. 
2.   In the Import Tasks dialog, click **Choose File**, and then select the CSV file. You can also drag a file onto the field. 
3.   Click **Import**. The tasks are added to the deployment plan. If the import process is unsuccessful, click **View Report** to display the error log. 

**Parent topic:** [Deployment plans](../../com.crelease.doc/topics/cr_deployPlan_ov.md)

**Parent topic:** [Running deployments](../../com.crelease.doc/topics/cr_deployRun_ov.md)

