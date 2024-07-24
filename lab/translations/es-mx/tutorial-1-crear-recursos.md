# Tutorial de la inteligencia en tiempo real, parte 1: creación de recursos

En esta parte del tutorial, configuras el entorno. Específicamente, creas un *espacio de trabajo* y una *eventhouse*, lo cual crea automáticamente una base de datos KQL hija, y luego habilitas la disponibilidad de OneLake.

## Crear un espacio de trabajo
1. Inicia sesión en el [portal de Microsoft Fabric](https://fabric.microsoft.com).
2. Elige **Inteligencia en Tiempo Real** de la lista de opciones en la página de inicio o en la barra de menú en la esquina inferior izquierda del portal.
3. Selecciona **Espacios de trabajo** en el panel de navegación izquierdo. Luego selecciona **+ Nuevo espacio de trabajo**.
4. Ingresa un nombre para el espacio de trabajo, como *TutorialWorkspace*. Selecciona **Aplicar** cuando termines.

    :::image type="content" source="media/lab/create-workspace.png" alt-text="Captura de pantalla que muestra cómo crear un espacio de trabajo en Real-Time Intelligence.":::

## Creación de instancia de Eventhouse

1. Ve al área de trabajo en la que deseas crear la base de datos.
2. En el conmutador de experiencias inferior izquierdo, selecciona **Inteligencia en tiempo real**.
3. En la esquina superior izquierda, selecciona **+ Nuevo > Eventhouse**.
4. Escriba *Tutorial* como nombre de la Eventhouse. Una base de datos KQL se crea simultáneamente con el mismo nombre.
5. Seleccione **Crear**. Una vez completado el aprovisionamiento, se muestra la página de **información general del sistema** de Eventhouse.

## Activación de la disponibilidad de OneLake

1. En la página **Información general del sistema**, selecciona la base de datos KQL que creaste en el paso anterior.
    
    :::image type="content" source="media/lab/select-tutorial-database.png" alt-text="Screnshot of the System overview for new eventhouse with Tutorial database selected and highlighted with a red box.":::

2. Junto a la sección **Detalles de la base de datos**, selecciona el **icono de lápiz** al lado de disponibilidad de **OneLake**.
3. Cambie el botón a **Activo** y seleccione **Listo**.

    :::image type="content" source="media/lab/one-lake-availability.png" alt-text="Captura de pantalla que muestra cómo activar la disponibilidad de OneLake.":::

## Paso siguiente

> [!div class="nextstepaction"]
> [Tutorial, parte 2: obtención datos en el centro en tiempo real](tutorial-2-obtención-de-datos-en-el-centro-en-tiempo-real.md)