---
title: Azure Event Grid - aplicaciones sin servidor
description: Azure Event Grid es una solución sin servidor para la entrega de eventos confiable y el enrutamiento a gran escala en un modelo de pago por evento.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 240542014a34235aea9fd0f8162748749f23eacf
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143667"
---
# <a name="event-grid"></a>Cuadrícula de eventos

[Azure Event Grid](/azure-event-grid/overview) proporciona infraestructura sin servidor para las aplicaciones basadas en eventos. Puede publicar en Event Grid desde cualquier origen y consumir mensajes desde cualquier plataforma. Event Grid también tiene compatibilidad integrada para eventos de recursos de Azure para simplificar la integración con sus aplicaciones. Por ejemplo, puede suscribirse a eventos para notificar a la aplicación cuando se carga un archivo de blob storage. La aplicación, a continuación, puede publicar un mensaje de cuadrícula de eventos personalizados que se consume en otra nube o aplicaciones locales. Event Grid se creó para controlar de forma confiable escala masiva. Obtenga las ventajas de publicar y suscribirse a mensajes sin la sobrecarga de configurar la infraestructura necesaria.

![Logotipo de la cuadrícula de eventos](./media/event-grid-logo.png)

Las principales características de event grid incluyen:

* Enrutamiento de eventos totalmente administrado.
* Cerca de la entrega de eventos en tiempo real a escala.
* Amplia cobertura tanto dentro como fuera de Azure.

## <a name="scenarios"></a>Escenarios

Event Grid aborda varios escenarios diferentes. En esta sección se trata tres de las más comunes.

### <a name="ops-automation"></a>Automatización de operaciones

![Automatización de operaciones](./media/ops-automation.png)

Event Grid puede ayudar a la automatización de la velocidad y simplificar el cumplimiento de directivas mediante la notificación a [Azure Automation](https://docs.microsoft.com/azure/automation) cuando se aprovisiona la infraestructura.

### <a name="application-integration"></a>Integración de aplicaciones

![Integración de aplicaciones](./media/app-integration.png)

Puede usar Event Grid para conectar la aplicación a otros servicios. Mediante los protocolos HTTP estándar, las aplicaciones heredadas incluso pueden modificarse fácilmente para publicar mensajes de Event Grid. Enlaces Web están disponibles para otros servicios y plataformas para consumir mensajes de Event Grid.

### <a name="serverless-apps"></a>Aplicaciones sin servidor

![Aplicaciones sin servidor](./media/serverless-apps.png)

Event Grid puede desencadenarse Azure Functions, Logic Apps o su propio código personalizado. Una ventaja importante del uso de Event Grid es que usa un *inserción* mecanismo para enviar mensajes cuando se producen eventos. La arquitectura de inserción consume menos recursos y se escala mejor que *sondeo* mecanismos. Sondeo debe comprobar si las actualizaciones de manera periódica.

## <a name="event-grid-vs-other-azure-messaging-services"></a>Cuadrícula de eventos frente a otros servicios de mensajes de Azure

Azure proporciona varios servicios de mensajes, como [Event Hubs](https://docs.microsoft.com/azure/event-hubs) y [Service Bus](https://docs.microsoft.com/azure/service-bus-messaging). Cada uno está diseñado para abordar un conjunto específico de casos de uso. El diagrama siguiente proporciona una descripción general de las diferencias entre los servicios.

![Comparación de mensajería de Azure](./media/azure-messaging-services.png)

Para obtener una comparación más detallada, consulte [Compare los servicios de mensajes](https://docs.microsoft.com/azure/event-grid/compare-messaging-services).

## <a name="performance-targets"></a>Objetivos de rendimiento

Con Event Grid puede sacar partido del rendimiento de las siguiente garantías:

* Latencia de extremo a otro en el percentil 99 de subsegundos.
* disponibilidad del 99,99%.
* 10 millones de eventos por segundo por región.
* suscripciones de 100 millones por región.
* latencia de 50 ms. publisher.
* 24 horas de reintento con retroceso exponencial para garantizar la entrega en la ventana de 1 día.
* Conmutación por error regional transparente.

## <a name="event-grid-schema"></a>Esquema de Event Grid

Event Grid usa un esquema estándar para encapsular los eventos personalizados. El esquema es como un envolvente que contiene el elemento de datos personalizados. Este es un mensaje de Event Grid de ejemplo:

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

Todo lo relacionado con el mensaje es estándar, excepto el `data` propiedad. Puede inspeccionar el mensaje y utilizar el `eventType` y `dataVersion` para deserializar la parte de la carga personalizada.

## <a name="azure-resources"></a>recursos de Azure

Una ventaja importante del uso de Event Grid es los mensajes automática generados por Azure. En Azure, recursos publican automáticamente en un *tema* que le permite suscribirse para varios eventos. En la tabla siguiente se enumera los tipos de recursos, tipos de mensajes y eventos que están disponibles automáticamente.

| Recursos de Azure | Tipo de evento. | Descripción |
| -------------- | ---------- | ----------- |
| Suscripción a Azure | Microsoft.Resources.ResourceWriteSuccess | Se genera cuando un recurso se crea o la operación de actualización se realiza correctamente. |
| | Microsoft.Resources.ResourceWriteFailure | Se genera al crear un recurso o se produce un error en la operación de actualización. |
| | Microsoft.Resources.ResourceWriteCancel | Se genera cuando un recurso crear o actualizar la operación se cancela. |
|  | Microsoft.Resources.ResourceDeleteSuccess | Se genera cuando se realiza correctamente una operación de eliminación de recursos. |
|  | Microsoft.Resources.ResourceDeleteFailure | Se genera cuando se produce un error en una operación de eliminación de recursos. |
| | Microsoft.Resources.ResourceDeleteCancel | Se genera cuando se cancela una operación de eliminación de recursos. Este evento se produce cuando se cancela una implementación de plantilla. |
| Almacenamiento de blobs | Microsoft.Storage.BlobCreated | Se genera cuando se crea un blob. |
| | Microsoft.Storage.BlobDeleted | Se genera cuando se elimina un blob. |
| Centros de eventos | Microsoft.EventHub.CaptureFileCreated | Se genera cuando se crea un archivo de captura.
| Centro de IoT | Microsoft.Devices.DeviceCreated | Se publica cuando se registra un dispositivo a IoT hub. |
| | Microsoft.Devices.DeviceDeleted | Se publica cuando se elimina un dispositivo de IoT hub. |
| Grupos de recursos | Microsoft.Resources.ResourceWriteSuccess | Se genera cuando un recurso se crea o la operación de actualización se realiza correctamente. |
| | Microsoft.Resources.ResourceWriteFailure | Se genera al crear un recurso o se produce un error en la operación de actualización. |
| | Microsoft.Resources.ResourceWriteCancel | Se genera cuando un recurso crear o actualizar la operación se cancela. |
| | Microsoft.Resources.ResourceDeleteSuccess | Se genera cuando se realiza correctamente una operación de eliminación de recursos. |
| | Microsoft.Resources.ResourceDeleteFailure | Se genera cuando se produce un error en una operación de eliminación de recursos. |
| | Microsoft.Resources.ResourceDeleteCancel | Se genera cuando se cancela una operación de eliminación de recursos. Este evento se produce cuando se cancela una implementación de plantilla. |

Para obtener más información, consulte [esquema de eventos de Azure Event Grid](https://docs.microsoft.com/azure/event-grid/event-schema).

Event Grid puede tener acceso desde cualquier tipo de aplicación, incluso uno que se ejecuta en el entorno local.

## <a name="conclusion"></a>Conclusión

En este capítulo, aprendió sobre la plataforma Azure sin servidor que se compone de Azure Functions, Logic Apps y Event Grid. Puede usar estos recursos para crear una arquitectura de aplicación sin servidor completamente, o crear una solución híbrida que interactúa con otros recursos de nube y servidores locales. Combinado con una plataforma de datos sin servidor, como [SQL Azure](https://docs.microsoft.com/azure/sql-database) o [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/introduction), puede compilar aplicaciones nativas en la nube totalmente administrado.

## <a name="recommended-resources"></a>Recursos recomendados

* [Planes de App service](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)
* [Application Insights](https://docs.microsoft.com/azure/application-insights)
* [Análisis de Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)
* [Azure: Traiga su aplicación a la nube con Azure Functions sin servidor](https://channel9.msdn.com/events/Connect/2017/E102)
* [Azure Event Grid](https://docs.microsoft.com/azure/azure-event-grid/overview)
* [Esquema de eventos de Azure Event Grid](https://docs.microsoft.com/azure/event-grid/event-schema)
* [Azure Event Hubs](https://docs.microsoft.com/azure/event-hubs)
* [Documentación de Azure Functions](https://docs.microsoft.com/azure/azure-functions)
* [Conceptos de enlaces y desencadenadores de Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)
* [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps)
* [Azure Service Bus](https://docs.microsoft.com/azure/service-bus-messaging)
* [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)
* [Comparación de functions 1.x y 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions)
* [Conectarse a orígenes de datos locales con puerta de enlace de datos de Azure local](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)
* [Crear su primera función en Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)
* [Cree su primera función mediante la CLI de Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)
* [Cree su primera función mediante Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)
* [Las funciones de idiomas admitidos](https://docs.microsoft.com/azure/azure-functions/supported-languages)
* [Supervisar Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)
* [Trabajar con Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies)

>[!div class="step-by-step"]
>[Anterior](logic-apps.md)
>[Siguiente](durable-azure-functions.md)