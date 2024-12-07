# Real-Time Intelligence tutorial part 5: Create a Power BI report

A Power BI report is a multi-perspective view into a semantic model, with visuals that represent findings and insights from that semantic model. In this section, you use a KQL query output to create a new Power BI report.

## Build a Power BI report

1. Browse to the KQL database you created in a previous step, named *Tutorial*.
2. In the object tree, under the KQL database name, select the query workspace called **Tutorial_queryset**.
3. Copy and paste the following query into the query editor. The output of this query is used as the semantic model for building the Power BI report. 

    ```kusto
    RawData | summarize arg_max(Timestamp, No_Bikes,  No_Empty_Docks, Neighbourhood, Lat=todouble(Latitude), Lon=todouble(Longitude)) by BikepointID
    ```

4. Select **Power BI**. The Power BI report editor opens with the query result available as a data source named **Kusto Query Result**.

### Add visualizations to the report

1. In the report editor, select **Visualizations** > **Stacked column chart** icon.
    ![Icon for the stacked column chart](media/stacked-column-chart-icon.png)
4. Drag the following fields from **Data** > **Kusto Query Result** to the **Visualizations** pane.
    * **Neighbourhood** > **X-axis**
    * **No_Bikes** > **Y-axis**
    * **No_Empty_Docks** > **Y-axis**

    ![Screenshot of adding the second visual, a column chart, to the report.](media/second-visual-report.png)

### Save the report

1. In the top left corner of the ribbon, select **File** > **Save**.
2. Enter the name +++*TutuorialReport*+++ and choose your workspace.
3. Select **Continue**.
4. Select **Open the file in Power BI to view, edit, and get a shareable link.**

Now that you have created a Power BI report, your data is visualized in a way that is easy to understand and share with others. It's time to set an alert on your event stream to receive a notification in Teams when the number of bikes falls below a certain threshold.

## Next step

> Select **Next >** to set an alert on your event stream
