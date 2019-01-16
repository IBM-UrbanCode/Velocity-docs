# Release management

A release is a container for deployment plans, events, and properties.

A release is a repeatable plan that is used to drive deployments. You can schedule a release at any point in your development-operations lifecycle. Your releases can represent all kinds of events, from major events in the life of your company to comparatively minor events, like recurring maintenance.

Typically, a release contains deployment plans and events that are related in some business-meaningful way. For example, the deployment plans might represent the phases in a software development lifecycle, such as development, QA, and production. An event might represent a blackout that affects the release.

If a deployment plan in a release has user-defined properties, the tasks in the release's other deployment plans can reference them. In other words, properties have release scope.

If you add events to a release, you can use the calendar to filter the Releases page to display releases and deployment plans.

You can use pipelines to manage releases. Every application added to a pipeline has release and deployment plan templates generated for it. As jobs and apps are added to a pipeline, tasks are inserted in the default deployment plan. You can run deployments directly from the Pipeline page or from the Deployment plan detail page.

-   **[Managing a release](../../com.crelease.doc/topics/cr_release_managedetails.md)**  
Use the release details page to view details about a specific release.
-   **[Managing releases](../../com.crelease.doc/topics/cr_release_manage.md)**  
Release management is the process of managing, planning, scheduling and controlling a software build through different stages and environments; including testing and deploying software releases.
-   **[Creating releases](../../com.crelease.doc/topics/cr_release_create.md)**  

-   **[Archiving releases](../../com.crelease.doc/topics/cr_release_archive.md)**  
You can archive a release to remove it from the list of releases.
-   **[Events and tags](../../com.crelease.doc/topics/cr_events_ov.md)**  
An event represents a release-related activity that you manage with the calendar. A tag is a label that you can add to a release or an event. You can use tags to filter the Activities list on the Releases page. Tags do not appear on the calendar.
-   **[Restoring archived releases, plans, and templates](../../com.crelease.doc/topics/cr_restore_archive.md)**  
You can restore archived releases, deployment plans, and templates.
-   **[Deployment plans](../../com.crelease.doc/topics/cr_deployPlan_ov.md)**  
A deployment plan is a container for tasks. Tasks define the activities that your team runs to complete a software deployment.
-   **[Running deployments](../../com.crelease.doc/topics/cr_deployRun_ov.md)**  
Complete deployments by resolving the tasks in a deployment plan.
-   **[Tasks](../../com.crelease.doc/topics/cr_task_ov.md)**  
A task represents a business-meaningful activity that is associated with a software deployment. Each task is defined on a separate row in a deployment plan. During a deployment, you run tasks defined in the deployment plan to complete the deployment.
-   **[Using properties](../../com.crelease.doc/topics/cr_properties_ov.md)**  
A deployment plan can contain user-defined properties. Properties values can be defined at design- or run-time.

