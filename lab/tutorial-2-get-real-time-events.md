# Real-Time Intelligence tutorial part 2: Get data in the Real-Time hub

In this part of the tutorial, you browse the Real-Time hub, create an event stream, transform events, and create a destination to send the transformed events to a KQL database.

## Create an event stream

1. From the navigation bar, select **Real-Time**. You may get a dialog Welcome to Real-Time hub. Click **Get started** to close the dialog.

2. Select **+ Connect data source**.

   ![Screenshot of Real-time hub with add source highlighted.](media/add-source.png)

3. The **Connect a data source** pane opens. Select **Sample scenarios** category, and the select **Connect** on the _Bicycles rentals_ tile.

   ![Screenshot of Real-time hub with sample data highlighted.](media/sample-data.png)

4. On the **Connect page**, for **Source name**, enter +++_TutorialSource_+++.
5. In the **Stream details** section, select the pencil icon, and change the name of the eventstream to +++_TutorialEventstream_+++, and then select **Next**.

   ![Screenshot of connect window in Real-Time hub.](media/connect-source.png)

6. On the **Review + connect** page, review settings and select **Connect**.

   A new event stream named _TutorialEventstream_ is created.

## Transform events - add a timestamp

1. On the **Review + connect** page, select **Open Eventstream**.
   
   You can also browse to the eventstream from the **My data streams** by selecting the stream and then selecting **Open Eventstream**.

2. From the menu ribbon, select **Edit**. The authoring canvas, which is the center section, turns yellow and becomes active for changes.

   ![Screenshot showing the edit button in Real-Time Intelligence.](media/event-stream-edit-button.png)

3. In the event stream authoring canvas select the down arrow on the **Transform events or add destination** tile, and then select **Manage fields**. The tile is renamed to _ManageFields_.

   ![Screenshot showing the transform events or add destination tile in Real-Time Intelligence.](media/transform-events.png)

4. Select **Manage fields**. The tile is renamed to _Manage_fields_.
5. Select the pencil icon on the _Manage_fields_ tile.
6. In the Manage fields pane, do the following actions:

   i. In **Operation name**, enter +++_TutorialTransform_+++.

   ii. Select **Add all fields**.

   iii. Select **+ Add field**.

   iv. From the **Field** dropdown, expand **Built-in Date Time Function** then select **SYSTEM.Timestamp()**.

   v. Enter +++_Timestamp_+++ as the **Name**.

   vi. Select **Add**.

   ![Screenshot showing the system timestamp selected in the event stream manage fields tile in Real-Time Intelligence.](media/system-timestamp.png)

7. Confirm that **Timestamp** is added to the field list, and select **Save**. The _TutorialTransform_ tile now displays but with an error, because the destination isn't configured yet.

## Create a destination for the timestamp transformation

1. Hover over the right edge of the _TutorialTransform_ tile and select the green plus icon.
2. Select **Destinations** > **Eventhouse**.

   A new tile is created entitled _Eventhouse_. A new tile is created entitled _Eventhouse_.

3. Select the pencil icon on the _Eventhouse_ tile.
   
      ![Screenshot showing the Eventhouse pane in Real-Time Intelligence.](media/pencil-on-event-house.png)

4. Enter the following information in the **Eventhouse** pane:

   ![Screenshot showing the KQL database destination pane in Real-Time Intelligence.](media/kql-database-details.png)

   | Field                 | Value                                                        |
   | --------------------- | ------------------------------------------------------------ |
   | **Data ingestion mode** | _Event processing before ingestion_                          |
   | **Destination name**  | +++_TutorialDestination_+++                                  |
   | **Workspace**         | Select the workspace in which you've created your resources. |
   | **Eventhouse**        | _Tutorial_                                                   |
   | **KQL Database**      | _Tutorial_                                                   |
   | **Destination table** | _Create new_ - enter +++_RawData_+++ as table name     |
   | **Input data format** | _JSON_                                                       |

5. Ensure that the box **Activate ingestion after adding the data** is checked.
6. Select **Save**.
7. From the menu ribbon select **Publish**.

> [!NOTE]
> In case you see the Source has been deactivated, as in the screenshot below, select **Activate all** to manually activate the source.

   ![Screenshot showing the source deactivated in Real-Time Intelligence.](media/source-deactivated.png)

The event stream is now set up to transform events and send them to a KQL database. The insights are not yet available to create alerts, you will do this in a later step so you can monitor the number of bikes in real-time. For now, you can move on to the next step to query the data in the KQL database.

## Next step

> Select **Next >** to transform streaming data in a KQL database.
