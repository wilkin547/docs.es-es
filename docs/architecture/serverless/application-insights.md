---
title: Aplicaciones sin servidor Application Insights
description: Application Insights es una plataforma de diagnóstico sin servidor que permite a los desarrolladores detectar, evaluar y diagnosticar problemas en aplicaciones Web, aplicaciones móviles, aplicaciones de escritorio y microservicios.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 1f5b99fba448c2c1c12139524ffdcd3708b3c956
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577728"
---
# <a name="telemetry-with-application-insights"></a>Telemetría con Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights) es una plataforma de diagnóstico sin servidor que permite a los desarrolladores detectar, evaluar y diagnosticar problemas en aplicaciones Web, aplicaciones móviles, aplicaciones de escritorio y microservicios. Puede activar Application Insights para las aplicaciones de función simplemente volteando un modificador en el portal. Application Insights proporciona todas estas funcionalidades sin tener que configurar un servidor o configurar su propia base de datos. Todas las funcionalidades de Application Insights se proporcionan como un servicio que se integra automáticamente con sus aplicaciones.

![Application Insights logotipo](./media/application-insights-logo.png)

Agregar Application Insights a las aplicaciones existentes es tan sencillo como agregar una clave de instrumentación a la configuración de la aplicación. Con Application Insights puede:

* Cree gráficos y alertas personalizados basados en métricas como el número de invocaciones de función, el tiempo necesario para ejecutar una función y excepciones.
* Analizar errores y excepciones de servidor
* Profundice en el rendimiento por operación y mida el tiempo que se tarda en llamar a dependencias de terceros
* Supervisar el uso de CPU, la memoria y las tasas en todos los servidores que hospedan las aplicaciones de función
* Visualización de una secuencia en directo de métricas, incluido el recuento de solicitudes y la latencia de las aplicaciones de función
* Usar [análisis](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) para buscar, consultar y crear gráficos personalizados sobre los datos de la función

![Explorador de métricas](./media/metrics-explorer.png)

Además de la telemetría integrada, también es posible generar telemetría personalizada. En el fragmento de código siguiente se crea un cliente de telemetría personalizado mediante la clave de instrumentación establecida para la aplicación de función:

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

El código siguiente mide cuánto tiempo se tarda en insertar una nueva fila en una instancia de [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) :

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

Se muestra el gráfico de rendimiento resultante:

![Telemetría personalizada](./media/custom-telemetry.png)

La telemetría personalizada revela que el tiempo promedio para insertar una nueva fila es de 32,6 milisegundos.

Application Insights proporciona una manera eficaz y cómoda de registrar la telemetría detallada sobre las aplicaciones sin servidor. Tiene control total sobre el nivel de seguimiento y registro que se proporciona. Puede realizar un seguimiento de las estadísticas personalizadas, como los eventos, las dependencias y la vista de página. Por último, el eficaz análisis le permite escribir consultas que formulan preguntas importantes y generan gráficos e información avanzada.

Para obtener más información, vea [Monitor Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).

>[!div class="step-by-step"]
>[Anterior](azure-functions.md)
>[Siguiente](logic-apps.md)
