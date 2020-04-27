---
title: 'Azure Event Grid: Aplicaciones sin servidor'
description: Azure Event Grid es una solución sin servidor para la entrega y el enrutamiento confiables de eventos a escala masiva según un modelo de pago por evento.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/06/2020
ms.openlocfilehash: 408e1b9cd1b1e5316c7c6a17bb1b0c76a38f9e11
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135716"
---
# <a name="event-grid"></a>Event Grid

[Azure Event Grid](/azure/event-grid/overview) proporciona una infraestructura sin servidor para las aplicaciones basadas en eventos. Puede publicar en Event Grid desde cualquier origen y consumir mensajes de cualquier plataforma. Event Grid también tiene compatibilidad integrada con los eventos de los recursos de Azure para simplificar la integración con sus aplicaciones. Por ejemplo, puede suscribirse a eventos de Blob Storage para notificar a la aplicación cuando se cargue un archivo. A continuación, la aplicación puede publicar un mensaje de Event Grid personalizado que otras aplicaciones locales o en la nube pueden usar. Event Grid se creó para controlar de forma confiable el escalado masivo. Se consiguen las ventajas de publicación y suscripción a los mensajes sin la sobrecarga que supone la configuración de la infraestructura necesaria.

![Logotipo de Event Grid](./media/event-grid-logo.png)

Entre las principales características de Event Grid se incluyen:

- Enrutamiento de eventos totalmente administrado.
- Entrega de eventos casi en tiempo real a escala.
- Amplia cobertura dentro y fuera de Azure.

## <a name="scenarios"></a>Escenarios

Event Grid aborda distintos escenarios. En esta sección se tratan tres de los más habituales.

### <a name="ops-automation"></a>Automatización de operaciones

![Automatización de operaciones](./media/ops-automation.png)

Event Grid puede ayudar a acelerar la automatización y a simplificar la aplicación de directivas enviando una notificación a [Azure Automation](https://docs.microsoft.com/azure/automation) cuando la infraestructura está aprovisionada.

### <a name="application-integration"></a>Integración de aplicaciones

![Integración de aplicaciones](./media/app-integration.png)

Puede usar Event Grid para conectar la aplicación a otros servicios. Mediante los protocolos HTTP estándar, incluso las aplicaciones heredadas se pueden modificar fácilmente para publicar mensajes de Event Grid. Los webhooks están disponibles para que otros servicios y plataformas utilicen mensajes de Event Grid.

### <a name="serverless-apps"></a>Aplicaciones sin servidor

![Aplicaciones sin servidor](./media/serverless-apps.png)

Event Grid puede desencadenar funciones de Azure, aplicaciones lógicas o su propio código personalizado. Una ventaja importante del uso de Event Grid es que utiliza un mecanismo de *inserción* para enviar mensajes cuando se producen eventos. La arquitectura de inserción consume menos recursos y se escala mejor que los mecanismos de *sondeo*. El sondeo debe comprobar si hay actualizaciones a intervalos regulares.

## <a name="event-grid-vs-other-azure-messaging-services"></a>Comparación de Event Grid con otros servicios de mensajería de Azure

Azure proporciona varios servicios de mensajería, incluido [Event Hubs](https://docs.microsoft.com/azure/event-hubs) y [Service Bus](https://docs.microsoft.com/azure/service-bus-messaging). Cada uno está diseñado para abordar un conjunto específico de casos de uso. El siguiente diagrama proporciona una introducción general de las diferencias entre los servicios.

![Comparación de servicios de mensajería de Azure](./media/azure-messaging-services.png)

Para ver una comparación más detallada, consulte [Comparación de los servicios de mensajería](https://docs.microsoft.com/azure/event-grid/compare-messaging-services).

## <a name="performance-targets"></a>Destinos del rendimiento

Con Event Grid puede disponer de las siguientes garantías de rendimiento:

- Latencia de un extremo a otro de subsegundos en el percentil 99.
- disponibilidad del 99,99%.
- 10 millones de eventos por segundo y región.
- 100 millones de suscripciones por región.
- Latencia del publicador de 50 ms.
- 24 horas de reintento con retroceso exponencial para la entrega garantizada en la ventana de tiempo de 1 día.
- Conmutación por error regional transparente.

## <a name="event-grid-schema"></a>Esquema de Event Grid

Event Grid usa un esquema estándar para encapsular eventos personalizados. El esquema es como un sobre que envuelve el elemento de datos personalizado. Este es un ejemplo de mensaje de Event Grid:

```json
[{
    "id": "03e24f21-a955-43cc-8921-1f61a6081ce0",
    "eventType": "myCustomEvent",
    "subject": "foo/bar/12",
    "eventTime": "2018-09-22T10:36:01+00:00",
    "data": {
        "favoriteColor": "blue",
        "favoriteAnimal": "panther",
        "favoritePlanet": "Jupiter"
    },
    "dataVersion": "1.0"
}]
```

Todo lo relacionado con el mensaje es estándar excepto la propiedad `data`. Puede inspeccionar el mensaje y usar `eventType` y `dataVersion` para deserializar la parte personalizada de la carga útil.

## <a name="azure-resources"></a>recursos de Azure

Una ventaja importante del uso de Event Grid son los mensajes automáticos que genera Azure. En Azure, los recursos se publican automáticamente en un *tema* que le permite suscribirse a varios eventos. En la tabla siguiente se enumeran los tipos de recursos, los tipos de mensajes y los eventos que están disponibles automáticamente.

| Recurso de Azure | Tipo de evento. | Descripción |
| -------------- | ---------- | ----------- |
| Suscripción a Azure | Microsoft.Resources.ResourceWriteSuccess | Se genera cuando una operación de actualización o de creación de un recurso se realiza correctamente. |
| | Microsoft.Resources.ResourceWriteFailure | Se genera cuando una operación de actualización o de creación de un recurso da error. |
| | Microsoft.Resources.ResourceWriteCancel | Se genera cuando se cancela una operación de actualización o de creación de un recurso. |
|  | Microsoft.Resources.ResourceDeleteSuccess | Se genera cuando una operación de eliminación de un recurso tiene éxito. |
|  | Microsoft.Resources.ResourceDeleteFailure | Se genera cuando una operación de eliminación de un recurso da error. |
| | Microsoft.Resources.ResourceDeleteCancel | Se genera cuando se cancela una operación de eliminación de un recurso. Este evento sucede cuando se cancela la implementación de una plantilla. |
| Blob Storage | Microsoft.Storage.BlobCreated | Se genera cuando se crea un blob. |
| | Microsoft.Storage.BlobDeleted | Se genera cuando se elimina un blob. |
| Centros de eventos | Microsoft.EventHub.CaptureFileCreated | Se genera cuando se crea un archivo de Capture.
| IoT Hub | Microsoft.Devices.DeviceCreated | Se publica cuando se registra un dispositivo en una instancia de IoT Hub. |
| | Microsoft.Devices.DeviceDeleted | Se publica cuando se elimina un dispositivo de una instancia de IoT Hub. |
| Grupos de recursos | Microsoft.Resources.ResourceWriteSuccess | Se genera cuando una operación de actualización o de creación de un recurso se realiza correctamente. |
| | Microsoft.Resources.ResourceWriteFailure | Se genera cuando una operación de actualización o de creación de un recurso da error. |
| | Microsoft.Resources.ResourceWriteCancel | Se genera cuando se cancela una operación de actualización o de creación de un recurso. |
| | Microsoft.Resources.ResourceDeleteSuccess | Se genera cuando una operación de eliminación de un recurso tiene éxito. |
| | Microsoft.Resources.ResourceDeleteFailure | Se genera cuando una operación de eliminación de un recurso da error. |
| | Microsoft.Resources.ResourceDeleteCancel | Se genera cuando se cancela una operación de eliminación de un recurso. Este evento sucede cuando se cancela la implementación de una plantilla. |

Para más información, consulte [Esquema de eventos de Azure Event Grid](https://docs.microsoft.com/azure/event-grid/event-schema).

Puede acceder a Event Grid desde cualquier tipo de aplicación, incluso uno que se ejecute de forma local.

## <a name="conclusion"></a>Conclusión

En este capítulo ha conocido más información sobre la plataforma sin servidor de Azure que se compone de Azure Functions, Logic Apps y Event Grid. Puede usar estos recursos para compilar una arquitectura de aplicación totalmente sin servidor o crear una solución híbrida que interactúe con otros recursos en la nube y servidores locales. En combinación con una plataforma de datos sin servidor, como [Azure SQL](https://docs.microsoft.com/azure/sql-database) o [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/introduction), puede crear aplicaciones nativas en la nube totalmente administradas.

## <a name="recommended-resources"></a>Recursos recomendados

- [Planes de App Service](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)
- [Application Insights](https://docs.microsoft.com/azure/application-insights)
- [Application Insights Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)
- [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102) (Migración de aplicaciones a la nube con Azure Functions sin servidor)
- [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview)
- [Esquema de eventos de Azure Event Grid](https://docs.microsoft.com/azure/event-grid/event-schema)
- [Azure Event Hubs](https://docs.microsoft.com/azure/event-hubs)
- [Documentación de Azure Functions](https://docs.microsoft.com/azure/azure-functions)
- [Conceptos básicos sobre los enlaces y desencadenadores de Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)
- [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps)
- [Azure Service Bus](https://docs.microsoft.com/azure/service-bus-messaging)
- [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)
- [Conexión a orígenes de datos locales con la puerta de enlace de datos local de Azure](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)
- [Creación de su primera función en Azure Portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)
- [Crear la primera función desde la CLI de Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)
- [Creación de la primera función mediante Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)
- [Lenguajes que admite Functions](https://docs.microsoft.com/azure/azure-functions/supported-languages)
- [Supervisión de Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)

>[!div class="step-by-step"]
>[Anterior](logic-apps.md)
>[Siguiente](durable-azure-functions.md)
