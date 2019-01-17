# Creating properties

Creating properties xxx

You define properties with the Deployment plan detail page **Properties** tab. You can create a property before you use it, or you can create a property by first referencing it in a task, and then later defining its attributes. If you create a property by reference, it appears as text-type property on the **Properties** tab.

To create a property, complete the following steps:

1.   On the Deployment plan detail page, click **Properties**, and then click **Add**. 
2.   On the Add property window, in the **Name** field, enter the name. Property names cannot contain white spaces, \``{}`\`, or \``:`\`. 
3.   In the **Label** field, enter the label that appears in the user interface. 
4.   In the **Type** list, select the property type. The available types are described in this list:
    -   `Text`
    -   `Text area`
    -   `Password`
    -   `Select`
    -   `Boolean`
    -   `Date and time`. Values are replaced by a string with the following format `day, month, year, time`. For example, `Thursday, January 1st 1970, 12:00 am UTC`.

        **Note:** When a date and time property is used in a ServiceNow task, the value is replaced with the date and time format expected by ServiceNow.

5.   In the **Value** field, you can enter an initial value for the property. 
6.   In the **Default Value** field, enter a value for the property. This value is used unless the user sets the value. You can leave this field blank.
7.   If you want users to supply a value for the property when they create a release, check **Prompt for this property at release creation at the specified sequence position**. 
8.   In the **Display sequence position** list, select a position for the property. This selected value affects the property's position on the**Properties** tab
9.   Click **Save**. The property is displayed on the deployment plan **Properties** tab.

After the release is created, you can add deployment plans, events, and tags to it.

**Parent topic:** [Using properties](../../com.crelease.doc/topics/cr_properties_ov.md)

