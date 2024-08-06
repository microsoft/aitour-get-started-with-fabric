# Tutorial de inteligencia en tiempo real, parte 2: obtención de datos en el centro en tiempo real

En esta parte del tutorial, examinarás el centro en tiempo real, crearás una secuencia de eventos, transformarás eventos y crearás un destino para enviar los eventos transformados a una base de datos KQL.

## Crea un flujo de eventos

1. En la barra de navegación, selecciona **Centro en tiempo real**.
2. Selecciona **+ Obtener eventos**.

    :::image type="content" source="media/get-events.png" alt-text="Captura de pantalla de la página de centro en tiempo real con el botón Obtener eventos resaltado.":::

3. Se abre el panel **Obtener eventos**. Selecciona **Datos de ejemplo**.

### Datos de ejemplo

1. En **Nombre de origen**, escribe *TutorialSource*.
2. En **Datos de ejemplo**, selecciona *Bicicletas (compatible con Reflex)*.

### Detalles de la flujo

1. Edita el **Nombre de la Eventstream** seleccionando el icono de lápiz e ingresando *TutorialEventstream*.
2. Selecciona **Siguiente**.

:::image type="content" source="media/connect-source.png" alt-text="Captura de pantalla de la ventana Conectar en el centro en tiempo real.":::

### Revisar y crear

1. Revisa los detalles de la flujo de eventos y selecciona **Crear origen**.

   Se crea una nueva flujo de eventos llamada *TutorialEventstream*.

## Transformar eventos

1. Selecciona **Abrir Eventstream** en la notificación que aparece después de crear la flujo de eventos o ve a la flujo de eventos desde el centro en tiempo real y selecciona **Abrir Eventstream**.
2. Desde el menú de cinta, selecciona **Editar**.
3. En el lienzo de autoría de la flujo de eventos, selecciona la flecha hacia abajo en el mosaico **Transformar eventos o agregar destino**.
4. Selecciona **Administrar campos**. Se cambia el nombre del icono a *Administrar_campos*
5. Selecciona el icono de lápiz en el mosaico *Administrar_campos*.
6. En el panel **Administrar campos**, realiza las siguientes acciones:

    i. En **Nombre de la operación**, escribe *TutorialTransform*.  
    ii. Selecciona **Agregar un campo**.  
    iii. Selecciona **+ Agregar campo**
    iv. En la lista desplegable **Función de fecha y hora integrada**, selecciona **SYSTEM.Timestamp()**.

    :::image type="content" source="media/system-timestamp.png" alt-text="Captura de pantalla que muestra la selección de la marca de tiempo del sistema en el mosaico de administración de campos de la flujo de eventos en Real-Time Intelligence.":::

    v. Escribe *Timestamp* como **Nombre del campo**.
    vi. Seleccione **Agregar**.
7. Selecciona **Listo**.
    > [!NOTE] 
    > El mosaico *TutorialTransform* ahora se muestra pero con un error, porque no se ha establecido el destino.

## Crear un destino

1. Mantén el puntero sobre el borde derecho del icono TutorialTransform y selecciona el icono verde "+"
2. Selecciona **Destinos** > **Base de datos KQL**.

    Se crea un nuevo mosaico titulado *KQLDatabase1*.

3. Selecciona el icono de lápiz en el icono *KQLDatabase1*.
4. Introduce la siguiente información en el panel **Base de datos KQL**:

    :::image type="content" source="media/kql-database-details.png" alt-text="Captura de pantalla que muestra cómo configurar la base de datos KQL en Real-Time Intelligence.":::

    | Campo | Valor |
    | --- | --- |
    | **Nombre del destino** | *TutorialDatabase* |
    | **Área de trabajo** | *Selecciona el área de trabajo en la que creaste tus recursos.* |
    | **Base de datos KQL** | *Tutorial* |
    | **Tabla de destino** | *Crear nueva: escribe TutorialTable como nombre de tabla* |
    | **Formato de datos de entrada** | *JSON* |

5. Selecciona **Guardar**.
6. Selecciona **Publicar**.

El flujo de eventos ahora está configurado para transformar eventos y enviarlos a una base de datos KQL. Los conocimientos aún no están disponibles para crear alertas; lo harás en un paso posterior para que puedas monitorear el número de bicicletas en tiempo real. Por ahora, puedes pasar al siguiente paso para consultar los datos en la base de datos KQL.

## Paso siguiente

> [!div class="nextstepaction"]
> [Tutorial, parte 3: Consultar datos de transmisión en un conjunto de consultas KQL](tutorial-3-consultar-datos.md)