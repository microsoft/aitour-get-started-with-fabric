# Tutorial de inteligencia en tiempo real, parte 4: creación de un panel en tiempo real

En esta parte del tutorial, aprenderás a crear un panel en tiempo real en inteligencia en tiempo real. Crea una consulta KQL, crea un panel en tiempo real, agrega un icono nuevo al panel y explora visualmente los datos incorporando una agregación.

## Crear de un panel en tiempo real

1. Copia y pega la siguiente consulta en el conjunto de consultas KQL. Esta consulta devuelve un gráfico de columnas que muestra el número más reciente de bicicletas por BikepoointID.

    ```kusto
    TutorialTable
    | summarize arg_max(Timestamp, No_Bikes) by BikepointID
    | sort by BikepointID
    | render columnchart with (ycolumns=No_Bikes, xcolumn= BikepointID)
    ```

    :::image type="content" source="media/lab/bikes-by-bikepoint.png" alt-text="Captura de pantalla de la consulta que muestra un gráfico de columnas de bicicletas por ID de punto de bicicleta.":::

2. Selecciona **Anclar al panel**.
3. Escriba la siguiente información:

    :::image type="content" source="media/lab/pin-dashboard.png" alt-text="Captura de pantalla de cómo anclar la consulta al panel en inteligencia en tiempo real.":::

    | Campo | Valor |
    | --- | --- |
    | **Crear un icono nuevo** | *En un panel nuevo* |
    | **Nombre del panel** | *TutorialDashboard* |
    | **Nombre del icono** | *Bicicletas recientes por Bikepoint* |
    | **Abrir el panel después de la creación** | *Seleccionado* |

4. Seleccione **Crear**.

El nuevo panel, *TutorialDashboard*, se abre con el icono *Bicicletas recientes por Bikepoint*.

## Incorporar de un icono nuevo al panel

1. En la barra de menú superior, cambia el modo **Visualización** por el modo **Edición**.
2. Selecciona **Nuevo icono**.

    :::image type="content" source="media/lab/new-tile.png" alt-text="Captura de pantalla del panel en tiempo real en modo de edición con un nuevo icono seleccionado.":::

3. Escriba la siguiente consulta:

    ```kusto
    TutorialTable
    | where Neighbourhood == "Chelsea"
    ``` 

4. En **Nombre del icono**, esribe *Bicicletas de Chelsea*.
5. Seleccione **Aplicar cambios**.

## Exploración visual de los datos mediante la incorporación de una agregación

1. En el icono **Bicicletas de Chelsea**, seleccione el icono **Explorar** :::image type="icon" source="media/lab/explore-icon.png" border="false":::.
    
    :::image type="content" source="media/lab/add-aggregation.gif" alt-text="GIF de cómo agregar y modificar visualmente la consulta." border="false":::

2. Selecciona **+ Agregar** > **Agregación**.
3. Selecciona **+ Agregar agrupación**.
4. Selecciona **Agrupar por** > *Calle*.
5. Selecciona **Aplicar**.

    Observa que los elementos de consulta se actualizan para incluir la agregación count() por Calle, resaltada en verde. La tabla resultante se ha cambiado para mostrar el recuento total de ubicaciones de bicicletas por calle.

## Paso siguiente

> [!div class="nextstepaction"]
> [Tutorial, parte 5: Crear un informe de Power BI a partir de tu conjunto de consultas KQL](tutorial-5-informe-de-power-bi.md)