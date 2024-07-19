# Real-Time Intelligence tutorial part 2: Get data in the Real-Time hub

In this part of the tutorial, you browse the Real-Time hub, create an event stream, transform events, and create a destination to send the transformed events to a KQL database.

## Create an event stream

1. From the navigation bar, select **Real-Time hub**.
2. Select **+ Get events**.
    
    :::image type="content" source="media/lab/get-events.png" alt-text="Screenshot of Real-time hub with get events highlighted.":::

3. The **Get events** pane opens. Select **Sample data**. 

### Sample data

1. In **Source name**, enter *TutorialSource*.
2. In **Sample data** select *Bicycles (Reflex compatible)*.

### Stream details

1. Edit the **Eventstream name** by selecting the pencil icon and entering *TutorialEventstream*.
2. Select **Next**.

:::image type="content" source="media/lab/connect-source.png" alt-text="Screenshot of connect window in Real-Time hub.":::

### Review and create

1. Review the event stream details and select **Create source**.

   A new event stream named *TutorialEventstream* is created.

## Transform events

1. Select **Open Eventstream** from the notification that appears after creating the event stream, or browse to the event stream from the Real-time hub and select **Open Eventstream**.
2. From the menu ribbon, select **Edit**.
3. In the event stream authoring canvas select the down arrow on the **Transform events or add destination** tile.  
4. Select **Manage fields**. The tile is renamed to *Manage_fields*.
5. Select the pencil icon on the *Manage_fields* tile.
6. In the **Manage fields** pane, do the following actions:

    i. In **Operation name**, enter *TutorialTransform*. 
    ii. Select **Add all fields**
    iii. Select **+ Add field**.
    iv. From the **Built-in Date Time Function** dropdown, select **SYSTEM.Timestamp()**
       :::image type="content" source="media/lab/system-timestamp.png" alt-text="Screenshot showing the system timestamp selected in the event stream manage fields tile in Real-Time Intelligence.":::

    v. Enter *Timestamp* as the **Field name**.
    vi. Select **Add**.
8. Select **Save**.

    The *TutorialTransform* tile is now displayed but with an error, because the destination has not been set.

## Create a destination

1. Hover over the right edge of the *TutorialTransform* tile and select the green plus icon.
2. Select **Destinations** > **KQL Database**.

    A new tile is created entitled *KQLDatabase1*.

3. Select the pencil icon on the *KQLDatabase1* tile.
4. Enter the following information in the **KQL Database** pane:

    :::image type="content" source="media/lab/kql-database-details.png" alt-text="Screenshot showing the KQL database destination pane in Real-Time Intelligence.":::

    | Field | Value |
    | --- | --- |
    | **Destination name** | *TutorialDestination* |
    | **Workspace** | Select the workspace in which you've created your resources. |
    | **KQL Database** | *Tutorial* |
    | **Destination table** | *Create new* - enter *TutorialTable* as table name |
    | **Input data format** | *JSON* |  

5. Select **Save**.
6. From the menu ribbon select **Publish**.

The event stream is now set up to transform events and send them to a KQL database. The insights are not yet available to create alerts, you will do this in a later step so you can monitor the number of bikes in real-time. For now, you can move on to the next step to query the data in the KQL database.

## Next step

> [!div class="nextstepaction"]
> [Tutorial part 3: Query streaming data in a KQL queryset](tutorial-3-query-data.md)
