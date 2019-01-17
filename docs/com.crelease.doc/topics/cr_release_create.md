# Creating releases

1.   On the Releases page, click **Create release** 
2.   In the Create release window, type a name for the release in the **Name** field. This field can be referenced with the `${sys:release.name}` system property. A name is required.
3.   In the **Tags** list, select one or more events or tags. You can also create a tag by typing the name of the new tag in the field. If you want the event to appear on the calendar, select an event that is created on the Configure Calendar page. Tags that you create with the Create release window are not displayed on the calendar, which can prevent calendar clutter.
4.   In the **Description** field, type a description of the release. This field can be referenced with the `${sys:release.description}` system property. 
5.   In the **Deployment plan templates** field, select one or more templates to add to the release. Each template that you select, adds a deployment plan to the release with the name **Copy of template\_name**. You can convert any deployment plan into a template. If the selected templates have user-defined properties, you are prompted to provide values for them when you save the release.
6.   In the **Start Time** field, select a starting date and time. This field can be referenced with the `${sys:release.start}` system property. Starting times are required for all releases. 
7.   In the **End Time** field, select the ending date and time. This field can be referenced with the `${sys:release.end}` system property. 
8.   In the **Team** list, select a team to manage the release. You can add deployment plans from other teams to the release event, not just the team that manages the release. All the teams that you belong to are available. A team is required. 
9.   If the selected templates have properties, click **Next**, and then provide values for the properties. Otherwise, click **Save** and view details to save the release and open the release details page. If you added templates to the release, a deployment plan for each template is created and displayed. If you didn't select any templates, an empty deployment plan is added to the release with the name **Plan: release\_name**. 

    To display the release in the **Activities** list, ensure that the date range includes dates within the release's start or end times.


After the release is created, you can add deployment plans, events, and tags to it.

**Parent topic:** [Release management](../../com.crelease.doc/topics/c_node_releases.md)

