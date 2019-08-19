---
title: Aplicaciones sin servidor Azure Event Grid
description: Azure Event Grid es una solución sin servidor para la entrega y el enrutamiento confiables de eventos a escala masiva en un modelo de pago por evento.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 4970130ede0c96c645129ee6c8c7d54cb1114042
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577578"
---
# <a name="event-grid"></a>Event Grid

[Azure Event Grid](/azure/event-grid/overview) proporciona una infraestructura sin servidor para las aplicaciones basadas en eventos. Puede publicar en Event Grid desde cualquier origen y consumir mensajes desde cualquier plataforma. Event Grid también tiene compatibilidad integrada con los eventos de los recursos de Azure para simplificar la integración con sus aplicaciones. Por ejemplo, puede suscribirse a eventos de BLOB Storage para notificar a la aplicación cuando se carga un archivo. A continuación, la aplicación puede publicar un mensaje de Event Grid personalizado consumido por otras aplicaciones locales o en la nube. Event Grid se creó para controlar de forma confiable el escalado masivo. Se obtienen las ventajas de publicar y suscribirse a los mensajes sin la sobrecarga que supone la configuración de la infraestructura necesaria.

![Event Grid logotipo](./media/event-grid-logo.png)

Las principales características de Event Grid incluyen:

* Enrutamiento de eventos totalmente administrado.
* Entrega de eventos casi en tiempo real a escala.
* Cobertura amplia tanto dentro como fuera de Azure.

## <a name="scenarios"></a>Escenarios

Event Grid aborda distintos escenarios. En esta sección se tratan tres de las más comunes.

### <a name="ops-automation"></a>Automatización de operaciones

![Automatización de operaciones](./media/ops-automation.png)

Event Grid puede ayudar a acelerar la automatización y a simplificar el cumplimiento de directivas mediante la notificación de [Azure Automation](https://docs.microsoft.com/azure/automation) cuando se aprovisiona la infraestructura.

### <a name="application-integration"></a>Integración de aplicaciones

![Integración de aplicaciones](./media/app-integration.png)

Puede usar Event Grid para conectar la aplicación a otros servicios. Mediante los protocolos HTTP estándar, incluso las aplicaciones heredadas se pueden modificar fácilmente para publicar mensajes de Event Grid. Los webhooks están disponibles para que otros servicios y plataformas utilicen mensajes Event Grid.

### <a name="serverless-apps"></a>Aplicaciones sin servidor

![Aplicaciones sin servidor](./media/serverless-apps.png)

Event Grid puede desencadenar Azure Functions, Logic Apps o su propio código personalizado. Una ventaja importante del uso de Event Grid es que utiliza un mecanismo de *extracción* para enviar mensajes cuando se producen eventos. La arquitectura de extracción utiliza menos recursos y escala mejor que los mecanismos de sondeo. El sondeo debe comprobar si hay actualizaciones a intervalos regulares.

## <a name="event-grid-vs-other-azure-messaging-services"></a>Event Grid frente a otros servicios de mensajería de Azure

Azure proporciona varios servicios de mensajería, como [Event hubs](https://docs.microsoft.com/azure/event-hubs) y [Service Bus](https://docs.microsoft.com/azure/service-bus-messaging). Cada uno está diseñado para abordar un conjunto específico de casos de uso. En el siguiente diagrama se proporciona información general de alto nivel sobre las diferencias entre los servicios.

![Comparación de mensajería de Azure](./media/azure-messaging-services.png)

Para obtener una comparación más detallada, consulte comparación de los [servicios de mensajería](https://docs.microsoft.com/azure/event-grid/compare-messaging-services).

## <a name="performance-targets"></a>Objetivos de rendimiento

Con Event Grid puede aprovechar las siguientes garantías de rendimiento:

* Latencia de un extremo a otro en el percentil valores percentil.
* 99,99% de disponibilidad.
* 10 millones eventos por segundo por región.
* 100 millones suscripciones por región.
* 50: latencia de Ms Publisher.
* reintento de 24 horas con el retroceso exponencial para la entrega garantizada en la ventana de 1 día.
* Conmutación por error regional transparente.

## <a name="event-grid-schema"></a>Esquema de Event Grid

Event Grid usa un esquema estándar para ajustar los eventos personalizados. El esquema es como un sobre que contiene el elemento de datos personalizado. Este es un ejemplo Event Grid mensaje:

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

Todo lo relacionado con el mensaje es estándar `data` excepto la propiedad. Puede inspeccionar el mensaje y usar `eventType` y `dataVersion` para deserializar la parte personalizada de la carga útil.

## <a name="azure-resources"></a>Recursos de Azure

Una ventaja importante del uso de Event Grid son los mensajes automáticos que genera Azure. En Azure, los recursos se publican automáticamente en un *tema* que le permite suscribirse a varios eventos. En la tabla siguiente se enumeran los tipos de recursos, los tipos de mensajes y los eventos que están disponibles automáticamente.

| Recurso de Azure | Tipo de evento | DESCRIPCIÓN |
| -------------- | ---------- | ----------- |
| Suscripción de Azure | Microsoft.Resources.ResourceWriteSuccess | Se genera cuando una operación de creación o actualización de recursos se realiza correctamente. |
| | Microsoft.Resources.ResourceWriteFailure | Se genera cuando se produce un error en una operación de creación o actualización de recursos. |
| | Microsoft.Resources.ResourceWriteCancel | Se genera cuando se cancela una operación de creación o actualización de recursos. |
|  | Microsoft.Resources.ResourceDeleteSuccess | Se genera cuando una operación de eliminación de recursos se realiza correctamente. |
|  | Microsoft.Resources.ResourceDeleteFailure | Se genera cuando se produce un error en una operación de eliminación de recursos. |
| | Microsoft.Resources.ResourceDeleteCancel | Se genera cuando se cancela una operación de eliminación de recursos. Este evento se produce cuando se cancela una implementación de plantilla. |
| Almacenamiento de blobs | Microsoft.Storage.BlobCreated | Se genera cuando se crea un BLOB. |
| | Microsoft.Storage.BlobDeleted | Se genera cuando se elimina un BLOB. |
| Centros de eventos | Microsoft.EventHub.CaptureFileCreated | Se genera cuando se crea un archivo de captura.
| IoT Hub | Microsoft.Devices.DeviceCreated | Se publica cuando se registra un dispositivo en una instancia de IoT Hub. |
| | Microsoft.Devices.DeviceDeleted | Se publica cuando se elimina un dispositivo de una instancia de IoT Hub. |
| Grupos de recursos | Microsoft.Resources.ResourceWriteSuccess | Se genera cuando una operación de creación o actualización de recursos se realiza correctamente. |
| | Microsoft.Resources.ResourceWriteFailure | Se genera cuando se produce un error en una operación de creación o actualización de recursos. |
| | Microsoft.Resources.ResourceWriteCancel | Se genera cuando se cancela una operación de creación o actualización de recursos. |
| | Microsoft.Resources.ResourceDeleteSuccess | Se genera cuando una operación de eliminación de recursos se realiza correctamente. |
| | Microsoft.Resources.ResourceDeleteFailure | Se genera cuando se produce un error en una operación de eliminación de recursos. |
| | Microsoft.Resources.ResourceDeleteCancel | Se genera cuando se cancela una operación de eliminación de recursos. Este evento se produce cuando se cancela una implementación de plantilla. |

Para obtener más información, vea [Azure Event Grid esquema de eventos](https://docs.microsoft.com/azure/event-grid/event-schema).

Puede tener acceso a Event Grid desde cualquier tipo de aplicación, incluso uno que se ejecute de forma local.

## <a name="conclusion"></a>Conclusión

En este capítulo ha aprendido sobre la plataforma sin servidor de Azure que se compone de Azure Functions, Logic Apps y Event Grid. Puede usar estos recursos para compilar una arquitectura de aplicación totalmente sin servidor o crear una solución híbrida que interactúe con otros recursos en la nube y servidores locales. Combinado con una plataforma de datos sin servidor como [Azure SQL](https://docs.microsoft.com/azure/sql-database) o [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/introduction), puede compilar aplicaciones nativas en la nube totalmente administradas.

## <a name="recommended-resources"></a>Recursos recomendados

* [Planes de App Service](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)
* [Application Insights](https://docs.microsoft.com/azure/application-insights)
* [Application Insights Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)
* [Azure Lleve su aplicación a la nube con Azure Functions sin servidor](https://channel9.msdn.com/events/Connect/2017/E102)
* [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview)
* [Azure Event Grid esquema de eventos](https://docs.microsoft.com/azure/event-grid/event-schema)
* [Event Hubs de Azure](https://docs.microsoft.com/azure/event-hubs)
* [Azure Functions documentación](https://docs.microsoft.com/azure/azure-functions)
* [Conceptos de Azure Functions desencadenadores y enlaces](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)
* [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps)
* [Azure Service Bus](https://docs.microsoft.com/azure/service-bus-messaging)
* [Table Storage de Azure](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)
* [Compare las funciones 1. x y 2. x](https://docs.microsoft.com/azure/azure-functions/functions-versions)
* [Conexión a orígenes de datos locales con la puerta de enlace de datos local de Azure](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)
* [Cree su primera función en el Azure Portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)
* [Cree su primera función mediante el CLI de Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)
* [Creación de la primera función mediante Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)
* [Lenguajes compatibles con funciones](https://docs.microsoft.com/azure/azure-functions/supported-languages)
* [Supervisar Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)
* [Trabajar con Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies)

>[!div class="step-by-step"]
>[Anterior](logic-apps.md)
>[Siguiente](durable-azure-functions.md)
