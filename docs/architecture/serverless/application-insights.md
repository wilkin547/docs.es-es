---
title: 'Application Insights: Aplicaciones sin servidor'
description: Application Insights es una plataforma de diagnóstico sin servidor que permite a los desarrolladores detectar, evaluar las prioridades y diagnosticar problemas en aplicaciones web, aplicaciones móviles, aplicaciones de escritorio y microservicios.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 42791b052ebb068c9b7109291e66b30b47e5821f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173326"
---
# <a name="telemetry-with-application-insights"></a>Telemetría con Application Insights

[Application Insights](/azure/application-insights) es una plataforma de diagnóstico sin servidor que permite a los desarrolladores detectar, evaluar las prioridades y diagnosticar problemas en aplicaciones web, aplicaciones móviles, aplicaciones de escritorio y microservicios. Puede activar Application Insights para las aplicaciones de funciones simplemente activando un conmutador en el portal. Application Insights proporciona todas estas funcionalidades sin necesidad de configurar un servidor o de configurar su propia base de datos. Todas las funcionalidades de Application Insights se proporcionan como un servicio que se integra automáticamente con sus aplicaciones.

![Logotipo de Application Insights](./media/application-insights-logo.png)

Agregar Application Insights a las aplicaciones existentes es tan sencillo como agregar una clave de instrumentación a la configuración de la aplicación. Con Application Insights puede:

- Crear gráficos y alertas personalizados basados en métricas como el número de invocaciones de funciones, el tiempo necesario para ejecutar una función y las excepciones
- Analizar errores y excepciones de servidor
- Analizar en profundidad el rendimiento por operación y medir el tiempo que se tarda en llamar a dependencias de terceros
- Supervisar el uso de CPU, la memoria y la velocidad en todos los servidores que hospedan las aplicaciones de funciones
- Ver un streaming en vivo de métricas que incluya el recuento de solicitudes y la latencia de las aplicaciones de funciones
- Usar [Analytics](/azure/application-insights/app-insights-analytics) para buscar, consultar y crear gráficos personalizados con los datos de las funciones

![Explorador de métricas](./media/metrics-explorer.png)

Además de la telemetría integrada, también es posible generar datos de telemetría personalizados. En el fragmento de código siguiente se crea un cliente de telemetría personalizado mediante la clave de instrumentación establecida para la aplicación de funciones:

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

El código siguiente mide cuánto tiempo se tarda en insertar una nueva fila en una instancia de [Azure Table Storage](/azure/cosmos-db/table-storage-overview):

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

Se muestra el gráfico de rendimiento resultante:

![Telemetría personalizada](./media/custom-telemetry.png)

La telemetría personalizada muestra que el tiempo promedio para insertar una nueva fila es de 32,6 milisegundos.

Application Insights proporciona una forma eficaz y cómoda de registrar la telemetría detallada de las aplicaciones sin servidor. Tiene un control total sobre el nivel de seguimiento y registro que se proporciona. Puede realizar un seguimiento de las estadísticas personalizadas como eventos, dependencias y la vista de página. Por último, el potente análisis le permite escribir consultas que formulan preguntas importantes y generan gráficos e información avanzada.

Para más información, consulte [Supervisión de Azure Functions](/azure/azure-functions/functions-monitoring).

>[!div class="step-by-step"]
>[Anterior](azure-functions.md)
>[Siguiente](logic-apps.md)
