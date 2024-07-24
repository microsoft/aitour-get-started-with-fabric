# Tutorial de inteligencia en tiempo real, parte 6: Establecer una alerta en el flujo de eventos

Los conocimientos del flujo de eventos ahora están disponibles para que crees alertas. En esta parte del tutorial, aprenderás cómo configurar una alerta en tu flujo de eventos para recibir una notificación en Teams cuando el número de bicicletas caiga por debajo de un cierto umbral.

## Configura una alerta en el flujo de eventos

1. Desde la barra de navegación izquierda, selecciona **Centro de Tiempo Real**.
2. Selecciona el flujo de eventos que creaste en el tutorial anterior, llamado *TutorialEventstream*. Se abre la página de detalles del flujo de eventos.

    :::image type="content" source="media/lab/set-alert.png" alt-text="Captura de pantalla de la página de detalles del flujo de eventos con el botón Configurar alerta resaltado." lightbox="media/lab/set-alert.png":::

3. Selecciona **Configurar alerta**
4. Se abre un nuevo panel. Completa los campos de la siguiente manera:

    | Campo | Valor |
    | --- | --- |
    | **Condición** |  |
    | Verificar | En cada evento cuando |
    | Campo | No_Bikes |
    | Condición | Es menor que |
    | Valor | 5 |
    | **Acción** | **Enviarme un mensaje en Teams**
    | **Ubicación de guardado** | |
    | Espacio de trabajo | El espacio de trabajo en el que creaste recursos|
    | Elemento | Crear un nuevo elemento |
    | Nombre del nuevo elemento | Tutorial-Reflex |

    :::image type="content" source="media/lab/alert-logic.png" alt-text="Captura de pantalla de cómo configurar una alerta en el flujo de eventos en Real-Time Intelligence.":::

5. Selecciona **Crear**.

    La alerta está configurada y recibirás una notificación en Teams cuando se cumpla la condición.

## Paso siguiente

> [!div class="nextstepaction"]
> [Tutorial, parte 7: Limpiar recursos](tutorial-7-limpiar-recursos.md)