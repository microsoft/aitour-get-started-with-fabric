# Real-Time Intelligence tutorial part 1: Create resources

In this part of the tutorial, you set up the environment. Specifically, you create a *workspace* and an *eventhouse*, which automatically creates a child KQL database, and then you enable OneLake availability.

## Create a workspace
1. Sign in to the [Microsoft Fabric portal](https://fabric.microsoft.com).
2. Choose **Real-Time Intelligence** from the list of options on the home page or the menu bar on the bottom left of the portal.
3. Select **Workspaces** from the left navigation pane. Then select **+ New workspace**.
4. Enter a name for the workspace, such as *TutorialWorkspace*. Select **Apply** when done.

    :::image type="content" source="media/create-workspace-side-pane.png" alt-text="Screenshot showing how to create a new workspace in Real-Time Intelligence.":::

## Create an eventhouse

1. Browse to the workspace in which you want to create your tutorial resources.
2. On the bottom left experience switcher, select **Real-Time Intelligence**.
3. In the upper left corner, select **+ New > Eventhouse**.
4. Enter *Tutorial* as the eventhouse name. A KQL database is created simultaneously with the same name.
5. Select **Create**. When provisioning is complete, the eventhouse **System overview** page is shown.

## Turn on OneLake availability

1. From the **System overview** page, select the KQL database you created in the previous step.

    :::image type="content" source="media/select-tutorial-database.png" alt-text="Screnshot of the System overview for new eventhouse with Tutorial database selected and highlighted with a red box.":::

2. In the **Database details** section, select the **pencil icon** next to **OneLake availability**.
3. Toggle the button to **Active** and select **Done**.

    :::image type="content" source="media/one-lake-availability.png" alt-text="Screenshot showing how to turn on OneLake availability.":::


## Next step

> [!div class="nextstepaction"]
> [Tutorial part 2: Get data in the Real-Time Hub](tutorial-2-get-real-time-events.md)