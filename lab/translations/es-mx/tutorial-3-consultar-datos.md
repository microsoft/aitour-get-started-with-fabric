# Tutorial de inteligencia en tiempo real, parte 3: Consulta datos en un conjunto de consultas KQL

En esta parte del tutorial, aprenderás a consultar los datos de streaming en un conjunto de consultas KQL. Crea un conjunto de consultas KQL, escribe una consulta KQL y visualiza los datos en un gráfico de tiempo.

## Crear un conjunto de consultas KQL

1. Ve al base de datos KQL que has creado en un paso anterior, denominado *Tutorial*.
2. Comprueba que los datos fluyen a la base de datos echando un vistazo al icono **Tamaño** en la página de detalles de la base de datos. Los valores en este mosaico deben ser mayores que cero.
3. En la cinta de opciones, selecciona **Nuevo elemento relacionado** y elige **Conjunto de consultas KQL**.

    :::image type="content" source="media/new-queryset.png" alt-text="Captura de pantalla de la base de datos Tutorial que muestra cómo agregar un nuevo elemento relacionado que es un conjunto de consultas KQL.":::

4. Escriba el nombre del conjunto de consultas KQL: *TutorialQueryset* y seleccione **Crear**.
5. Selecciona la base de datos *Tutorial* como origen de datos para el conjunto de consultas KQL y luego selecciona **Conectar**.
6. Selecciona **Crear**.
    Se crea un nuevo conjunto de consultas KQL que se abre en el editor de conjuntos de consultas KQL. Está conectado a la base de datos *Tutorial* como origen de datos y está prellenado con varias consultas generales.

## Escritura de una consulta de KQL

El nombre de la tabla que creaste en un paso anterior es *TutorialTable*. Utiliza este nombre (sensible a mayúsculas y minúsculas) como origen de datos para tu consulta.

1. En el editor de consultas, elimina las consultas prellenadas e ingresa la siguiente consulta. Luego presiona **Mayús + Entrar** para ejecutar la consulta.

    ```kusto
    TutorialTable
    | take 10
    ```

    Esta consulta devuelve 10 registros arbitrarios de la tabla. ¿Qué información sobre los datos puedes ver de un vistazo? Observa que una de las columnas se llama *No_Bikes*. Esta columna contiene el número de muelles vacíos en una estación de bicicletas. Este es un campo con el que podrías estar preocupado si estás rastreando la disponibilidad de bicicletas en una estación.

2. Para ver los datos de una manera más visual, utiliza el operador **render**. Ejecuta la siguiente consulta:

    ```kusto
    TutorialTable
    | where Neighbourhood == "Chelsea"
    | project Timestamp, No_Bikes
    | render timechart
    ```
    Esta consulta crea un gráfico de tiempo que muestra el número de bicicletas en el barrio de Chelsea.

    :::image type="content" source="media/empty-docks-timechart.png" alt-text="Captura de pantalla de un gráfico de tiempo de muelles vacíos en Real-Time Intelligence.":::

## Paso siguiente

> [!div class="nextstepaction"]
> [Tutorial, parte 4: Crear un tablero en tiempo real](tutorial-4-crear-tablero.md)