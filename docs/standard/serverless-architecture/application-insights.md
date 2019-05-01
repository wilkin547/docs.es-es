---
title: 'Application Insights: aplicaciones sin servidor'
description: Application Insights es una plataforma de diagnóstico sin servidor que permite a los desarrolladores detectar, evaluar las prioridades y diagnostique problemas en aplicaciones web, aplicaciones móviles, aplicaciones de escritorio y microservicios.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: b4884d483de07c1c2077f7280b6b77c6059572c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051231"
---
# <a name="telemetry-with-application-insights"></a>Datos de telemetría con Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights) es una plataforma de diagnóstico sin servidor que permite a los desarrolladores detectar, evaluar las prioridades y diagnostique problemas en aplicaciones web, aplicaciones móviles, aplicaciones de escritorio y microservicios. Puede activar Application Insights para aplicaciones de función accionando un conmutador en el portal. Application Insights proporciona todas estas funcionalidades sin tener que volver a configurar un servidor o configurar su propia base de datos. Todas las capacidades de Application Insights se proporcionan como un servicio que automáticamente se integra con las aplicaciones.

![Logotipo de Application Insights](./media/application-insights-logo.png)

Agregar Application Insights a las aplicaciones existentes es tan fácil como agregar una clave de instrumentación a la configuración de la aplicación. Con Application Insights, puede:

* Crear gráficos personalizados y alertas basadas en métricas como el número de invocaciones de función, el tiempo necesario para ejecutar una función y excepciones
* Analizar errores y excepciones de servidor
* Profundizar en el rendimiento mediante la operación y medir el tiempo necesario para llamar a las dependencias de terceros
* Supervisar el uso de CPU, memoria y las tasas en todos los servidores que hospedan las aplicaciones de función
* Ver una secuencia en directo de métricas, incluidos el número de solicitudes y la latencia para las aplicaciones de función
* Use [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) para buscar, consultar y crear gráficos personalizados a través de los datos de la función

![Explorador de métricas](./media/metrics-explorer.png)

Además de telemetría integrada, también es posible generar datos de telemetría personalizados. El siguiente fragmento de código crea a un cliente de telemetría personalizada mediante la clave de instrumentación establecido para la aplicación de función:

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

El código siguiente mide cuánto tarda en Insertar una fila nueva en un [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) instancia:

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

Se muestra el gráfico de rendimiento resultante:

![Telemetría personalizada](./media/custom-telemetry.png)

La telemetría personalizada, se muestra el tiempo medio para insertar una fila nueva es 32.6 milisegundos.

Application Insights proporciona una manera eficaz y fácil para registrar la telemetría detallada acerca de las aplicaciones sin servidor. Tiene control total sobre el nivel de seguimiento y registro se proporciona. Puede realizar un seguimiento de estadísticas personalizadas, como la vista de página, dependencias y eventos. Por último, el análisis eficaces le permiten escribir consultas que formular preguntas importantes y generan gráficos e información avanzada.

Para obtener más información, consulte [supervisión de Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).

>[!div class="step-by-step"]
>[Anterior](azure-functions.md)
>[Siguiente](logic-apps.md)