---
title: Registro con el SDK de Azure para .NET
description: Aprenda a habilitar el registro con las bibliotecas de cliente de Azure SDK para .NET
ms.date: 03/20/2020
ms.custom: azure-sdk-dotnet
ms.author: casoper
author: camsoper
ms.openlocfilehash: b277045a60ef5cc065d77dad84878872dedc963e
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "81433227"
---
# <a name="logging-with-the-azure-sdk-for-net"></a>Registro con el SDK de Azure para .NET

Las bibliotecas de cliente de [Azure SDK](https://azure.microsoft.com/downloads/) para .NET incluyen la capacidad de registrar operaciones de biblioteca de cliente. Esto le permite supervisar las solicitudes de E/S y las respuestas que las bibliotecas de cliente realizan en los servicios de Azure. Normalmente, los registros se usan para depurar o diagnosticar problemas de comunicación. En este artículo se describen tres enfoques para habilitar el registro con El SDK de Azure para .NET:

- Inicie sesión en la ventana de la consola
- Registro en seguimientos de diagnóstico de .NET
- Configurar el registro personalizado

> [!IMPORTANT]
> Este artículo se aplica a las bibliotecas de cliente que usan las versiones más recientes del SDK de Azure para .NET. Para ver si se admite una biblioteca, consulte la lista de [versiones más recientes](https://azure.github.io/azure-sdk/releases/latest/index.html)del SDK de Azure. Si la aplicación usa una versión anterior de las bibliotecas de cliente del SDK de Azure, consulte las instrucciones específicas de la documentación del servicio correspondiente.

## <a name="log-information"></a>Información de registro

El SDK registra la siguiente información, desinfectando los valores de encabezado y consulta de parámetros para quitar datos personales.

Entrada de registro de solicitud HTTP:

- Identificador único
- HTTP method
- URI
- Encabezados de solicitud saliente

Entrada de registro de respuesta HTTP:

- Duración de la operación de E/S (tiempo transcurrido)
- Id. de solicitud
- Código de estado HTTP
- Frase de razón HTTP
- Encabezados de respuesta
- Información de error, cuando corresponda

Para el contenido de solicitud y respuesta:

- Secuencia de contenido como texto o bytes en función del encabezado Content-Type.
     > [! NOTA: el registro de contenido está deshabilitado de forma predeterminada. Para habilitarlo, `Diagnostics.IsLoggingContentEnabled` `true` establezca `ClientOptions`en .

Los registros de eventos son la salida generalmente en uno de estos tres niveles:

- Información para eventos de solicitud y respuesta
- Advertencia de errores
- Detallado para mensajes detallados y registro de contenido

## <a name="enable-logging-with-built-in-methods"></a>Habilite el registro con métodos integrados

Las bibliotecas de cliente de Azure SDK para .NET registran eventos en Seguimiento de eventos para Windows (ETW) a través de la [ `EventSource` clase,](/dotnet/api/system.diagnostics.tracing.eventsource)que es típica de .NET. Los orígenes de eventos le permiten usar el registro estructurado en el código de la aplicación con una sobrecarga de rendimiento mínima. Para obtener acceso a estos registros de eventos, debe registrar los detectores de eventos.

El SDK `Azure.Core.Diagnostics.AzureEventSourceListener` incluye la clase (definida en el paquete NuGet de Azure.Core), que `CreateConsoleLogger` contiene `CreateTraceLogger`dos métodos estáticos que simplifican el registro completo de la aplicación .NET: y . Estos métodos toman un parámetro opcional que especifica un nivel de registro.

### <a name="log-to-the-console-window"></a>Inicie sesión en la ventana de la consola

Un principio principal de las bibliotecas de cliente de Azure SDK para .NET es simplificar la capacidad de ver registros completos en tiempo real. El `CreateConsoleLogger` método le permite enviar registros a la ventana de la consola con una sola línea de código:

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateConsoleLogger();
```

### <a name="log-to-diagnostic-traces"></a>Registro en los seguimientos de diagnóstico

Si implementa agentes de escucha `CreateTraceLogger` de seguimiento, puede usar el método[`System.Diagnostics.Tracing`](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing)para iniciar sesión en el mecanismo de seguimiento de eventos estándar de .NET ( ). Para obtener más información sobre el seguimiento de eventos en .NET, vea [Agentes de escucha](https://docs.microsoft.com/dotnet/framework/debug-trace-profile/trace-listeners)de seguimiento . En este ejemplo se especifica un nivel de registro detallado:

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateTraceLogger(EventLevel.Verbose);
```

## <a name="configure-custom-logging"></a>Configurar el registro personalizado

Como se mencionó anteriormente, debe registrar los detectores de eventos para recibir mensajes de registro del SDK de Azure para .NET. Si no desea implementar el registro completo mediante uno de los métodos `AzureEventSourceListener` simplificados anteriores, puede construir una instancia de la clase y pasarle una función de devolución de llamada que escriba. Este método recibirá mensajes de registro que puede procesar sin necesidad. Además, al construir la instancia, puede especificar los niveles de registro que desea incluir.

En el ejemplo siguiente se crea un detector de eventos que inicia sesión en la consola con un mensaje personalizado y se filtra a los eventos principales de Azure del nivel detallado.

```csharp
using AzureEventSourceListener listener = new AzureEventSourceListener((e, message) =>
    {
        // Only log messages from Azure-Core event source
        if (e.EventSource.Name == "Azure-Core")
        {
            Console.WriteLine($"{DateTime.Now} {message}");
        }
    },
    level: EventLevel.Verbose);
```

## <a name="next-steps"></a>Pasos siguientes

- [Habilitar el registro de diagnósticos para las aplicaciones de Azure App Service](https://docs.microsoft.com/azure/app-service/troubleshoot-diagnostic-logs)
- Revise las opciones de auditoría y registro de [seguridad de Azure](https://docs.microsoft.com/azure/security/fundamentals/log-audit)
- Aprenda a trabajar con [los registros](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview) de la plataforma Azure
- Obtenga más información sobre el registro y el seguimiento de [.NET Core](https://docs.microsoft.com/dotnet/core/diagnostics/logging-tracing)
