---
title: Registro con Azure SDK para .NET
description: Obtenga más información sobre cómo habilitar el registro con las bibliotecas cliente de Azure SDK para .NET
ms.date: 03/20/2020
ms.custom: azure-sdk-dotnet
ms.author: casoper
author: camsoper
ms.openlocfilehash: 5a1fb35aeca034a7cdd1caa813a3839919a5f926
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174883"
---
# <a name="logging-with-the-azure-sdk-for-net"></a>Registro con Azure SDK para .NET

Las bibliotecas cliente de [Azure SDK](https://azure.microsoft.com/downloads/) para .NET incluyen la posibilidad de registrar operaciones de la biblioteca cliente. Esto le permite supervisar las solicitudes de E/S y las respuestas que las bibliotecas cliente realizan en los servicios de Azure. Normalmente, los registros se usan para depurar o diagnosticar problemas de comunicación. En este artículo se describen tres métodos para habilitar el registro con Azure SDK para .NET:

- Inicio de sesión en la ventana de consola
- Registro en seguimientos de diagnósticos de .NET
- Configuración del registro personalizado

> [!IMPORTANT]
> Este artículo se aplica a las bibliotecas cliente que usan las versiones más recientes de Azure SDK para .NET. Para ver si se admite una biblioteca, consulte la lista de [versiones más recientes del SDK de Azure](https://azure.github.io/azure-sdk/releases/latest/index.html). Si su aplicación usa una versión anterior de las bibliotecas cliente del SDK de Azure, consulte las instrucciones específicas de la documentación del servicio correspondiente.

## <a name="log-information"></a>Información de registro

El SDK registra la siguiente información, depurando los valores de encabezado y consulta de los parámetros para quitar datos personales.

Entrada del registro de solicitudes HTTP:

- Id. único
- HTTP method
- Identificador URI
- Encabezados de solicitudes salientes

Entrada del registro de respuestas HTTP:

- Duración de la operación de E/S (tiempo transcurrido)
- Id. de solicitud
- Código de estado HTTP
- Oración de motivo HTTP
- Encabezados de respuesta
- Información de error, cuando proceda

Para el contenido de la solicitud y la respuesta:

- Flujo de contenido como texto o bytes, según el encabezado Content-Type.
     > Nota: El registro de contenido está deshabilitado de manera predeterminada. Para habilitarlo, cambie `Diagnostics.IsLoggingContentEnabled` a `true` en `ClientOptions`.

Los registros de eventos se generan normalmente en uno de estos tres niveles:

- Información para eventos de solicitud y respuesta
- Advertencia para errores
- Detallado para mensajes detallados y registro de contenido

## <a name="enable-logging-with-built-in-methods"></a>Habilitación del registro con métodos integrados

Las bibliotecas cliente de Azure SDK para .NET registran eventos en Seguimiento de eventos para Windows (ETW) mediante la [clase `EventSource`](/dotnet/api/system.diagnostics.tracing.eventsource), que es habitual para .NET. Los orígenes de eventos permiten usar el registro estructurado en el código de aplicación con una sobrecarga de rendimiento mínima. Para obtener acceso a estos registros de eventos, debe registrar agentes de escucha de eventos.

El SDK incluye la clase `Azure.Core.Diagnostics.AzureEventSourceListener` (definida en el paquete Azure.Core NuGet), que contiene dos métodos estáticos que simplifican el registro completo de la aplicación .NET: `CreateConsoleLogger` y `CreateTraceLogger`. Estos métodos adoptan un parámetro opcional que especifica un nivel de registro.

### <a name="log-to-the-console-window"></a>Inicio de sesión en la ventana de consola

Un principio básico de las bibliotecas cliente de Azure SDK para .NET es simplificar la capacidad de ver registros completos en tiempo real. El método `CreateConsoleLogger` permite enviar registros a la ventana de la consola con una sola línea de código:

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateConsoleLogger();
```

### <a name="log-to-diagnostic-traces"></a>Registro para el seguimiento de diagnósticos

Si implementa agentes de escucha de seguimiento, puede usar el método `CreateTraceLogger` para registrarse en el mecanismo de seguimiento de eventos estándar de .NET ([`System.Diagnostics.Tracing`](/dotnet/api/system.diagnostics.tracing)). Para obtener más información sobre el seguimiento de eventos en .NET, vea [Agentes de escucha de seguimiento](/dotnet/framework/debug-trace-profile/trace-listeners). En este ejemplo se especifica un nivel de registro detallado:

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateTraceLogger(EventLevel.Verbose);
```

## <a name="configure-custom-logging"></a>Configuración del registro personalizado

Como se mencionó anteriormente, debe registrar los agentes de escucha de eventos para recibir mensajes de registro de Azure SDK para .NET. Si no quiere implementar un registro completo con uno de los métodos simplificados anteriores, puede construir una instancia de la clase `AzureEventSourceListener` y pasarle una función de devolución de llamada que usted mismo escriba. Este método recibirá mensajes de registro que se pueden procesar en caso que sea necesario. Además, cuando se crea la instancia, se pueden especificar los niveles de registro que se van a incluir.

En el ejemplo siguiente, se crea un agente de escucha de eventos que se registra en la consola con un mensaje personalizado y se filtra a los eventos principales de Azure del nivel detallado.

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

- [Habilitar el registro de diagnósticos para las aplicaciones en Azure App Service](/azure/app-service/troubleshoot-diagnostic-logs)
- Revisar las opciones de [auditoría y registro de seguridad de Azure](/azure/security/fundamentals/log-audit)
- Más información sobre cómo trabajar con los [registros de la plataforma de Azure](/azure/azure-monitor/platform/platform-logs-overview)
- Más información sobre el [registro y el seguimiento de.NET Core](/dotnet/core/diagnostics/logging-tracing)
