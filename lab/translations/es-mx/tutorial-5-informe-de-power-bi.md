# Tutorial de Inteligencia en Tiempo Real, parte 5: Crear un informe de Power BI

Un informe de Power BI es una vista multiperspectiva de un modelo semántico, con visuales que representan hallazgos y conocimientos de ese modelo semántico. En esta sección, utilizas un resultado de consulta KQL para crear un nuevo informe de Power BI.

## Crear un informe de Power BI

1. Desde la barra de navegación, selecciona el conjunto de consultas KQL que creaste en un paso anterior, llamado *TutorialQueryset*.
2. Copia y pega la siguiente consulta en el editor de consultas. El resultado de esta consulta se utiliza como modelo semántico para crear el informe de Power BI.

    ```kusto
    TutorialTable
    | summarize arg_max(Timestamp, No_Bikes,  No_Empty_Docks, Neighbourhood, Lat=todouble(Latitude), Lon=todouble(Longitude)) by BikepointID
    ```

3. Selecciona **Power BI**. El editor de informes de Power BI se abre con el resultado de la consulta disponible como una fuente de datos llamada **Resultado de Consulta de Kusto**.

### Agrega visualizaciones al informe

1. En el editor de informes, selecciona el icono **Visualizaciones** > **Mapa**.
    :::image type="content" source="media/map-icon.png" alt-text="Captura de pantalla del editor de informes de Power BI con un mapa seleccionado.":::
2. Arrastra los siguientes campos desde **Datos** > **Resultado de Consulta de Kusto** al panel de **Visualizaciones**.
    * **Lat** > **Latitud**
    * **Lon** > **Longitud**
    * **No_Bikes** > **Tamaño de burbuja**
    * **Neighbourhood** > **Agrega campos de detalles aquí**

    :::image type="content" source="media/report-generated.png" alt-text="Captura de pantalla de un informe de Power BI con un mapa que muestra la disponibilidad de bicicletas en diferentes barrios.":::

3. En el editor de informes, selecciona el icono **Visualizaciones** > **Gráfico de columnas apiladas**.
    :::image type="content" source="media/stacked-column-chart.png" border="false":::
4. Arrastra los siguientes campos desde **Datos** > **Resultado de Consulta de Kusto** al panel de **Visualizaciones**.
    * **Neighbourhood** > **Eje X**
    * **No_Empty_Docks** > **Eje Y**
    * **No_Bikes** > **Eje Y**

    :::image type="content" source="media/second-visual-report.png" alt-text="Captura de pantalla de un informe de Power BI con un gráfico de columnas apiladas que muestra la disponibilidad de bicicletas y muelles vacíos en diferentes barrios." lightbox="media/second-visual-report.png":::

### Guarda el informe

1. En la esquina superior izquierda de la cinta de opciones, selecciona **Archivo** > **Guardar**.
2. Ingresa el nombre *TutorialReport*. Elige tu espacio de trabajo y establece la sensibilidad como Pública.
3. Selecciona **Continuar**.
4. Selecciona **Abrir el archivo en Power BI para ver, editar y obtener un enlace para compartir.**

## Interactúa con el informe

Cuando abres el informe de Power BI, puedes agregar o editar visualizaciones. También puedes interactuar con las visualizaciones. Por ejemplo, seleccionar una de las columnas de *Vecindario* en una visualización resalta los valores de ese vecindario en las otras visualizaciones.

:::image type="content" source="media/cross-highlight.gif" alt-text="GIF que muestra cómo resaltar visualmente los datos en un informe de Power BI." border="false" lightbox="media/cross-highlight.gif":::

Ahora que has creado un informe de Power BI, tus datos están visualizados de una manera que es fácil de entender y compartir con otros. Es momento de configurar una alerta en tu flujo de eventos para recibir una notificación en Teams cuando el número de bicicletas caiga por debajo de un cierto umbral.

## Paso siguiente

> [!div class="nextstepaction"]
> [Tutorial, parte 6: Configurar una alerta en tu flujo de eventos](tutorial-6-configurar-alertas.md)