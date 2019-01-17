# Managing deployment plan templates

You can convert deployment plans to create deployment plan templates.

To create a template, use the **Copy as template** action On the Deployment Plan page. When you create a template, a new plan with the name "Copy of plan\_name" is inserted into the Templates page. The status of a template is \`template\` even if the original plan has a status of \`done\` or \`in progress\`. The template contains all the tasks that are defined in the original plan. If UrbanCode Deploy tasks are in the plan, the applications selected in the original are also selected in the template.

You cannot run deployments with templates. To use a template for a deployment, first copy or promote it and then use the copied or promoted plan.

**Parent topic:** [Deployment plans](../../com.crelease.doc/topics/cr_deployPlan_ov.md)

