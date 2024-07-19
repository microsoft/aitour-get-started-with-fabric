# Real-Time Intelligence tutorial part 6: Set an alert on your event stream

In this part of the tutorial, you learn how to set an alert on your event stream to receive a notification in Teams when the number of bikes falls below a certain threshold.

## Set an alert on the event stream

1. From the left navigation bar, select **Real-Time hub**.
2. Select the event stream you created in the previous tutorial named *TutorialEventstream*.
    The event stream details page opens.
    
    :::image type="content" source="media/lab/set-alert.png" alt-text="Screenshot of event streams details page and set alert selected." lightbox="media/tutorial/set-alert.png":::

3. Select **Set alert**
4. A new pane opens. Fill in the fields as follows:

    | Field | Value |
    | --- | --- |
    | **Condition** |  |
    | Check | On each event when |
    | Field | No_Bikes |  
    | Condition | Is less than |
    | Value | 5 |
    | **Action** |  **Message me in Teams**
    | **Save location** | | 
    | Workspace | The workspace in which you created resources|
    | Item | Create a new item |
    | New item name | Tutorial-Reflex |

    :::image type="content" source="media/lab/alert-logic.png" alt-text="Screenshot of Set alert pane in Real-Time Intelligence.":::

5. Select **Create**.

    The alert is set and you receive a notification in Teams when the condition is met.

## Next step

> [!div class="nextstepaction"]
> [Tutorial part 7: Clean up resources](tutorial-7-clean-up-resources.md)