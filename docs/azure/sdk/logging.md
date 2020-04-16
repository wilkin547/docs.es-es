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
# <a name="logging-with-the-azure-sdk-for-net"></a><span data-ttu-id="b2644-103">Registro con el SDK de Azure para .NET</span><span class="sxs-lookup"><span data-stu-id="b2644-103">Logging with the Azure SDK for .NET</span></span>

<span data-ttu-id="b2644-104">Las bibliotecas de cliente de [Azure SDK](https://azure.microsoft.com/downloads/) para .NET incluyen la capacidad de registrar operaciones de biblioteca de cliente.</span><span class="sxs-lookup"><span data-stu-id="b2644-104">The [Azure SDK](https://azure.microsoft.com/downloads/) for .NET client libraries includes the ability to log client library operations.</span></span> <span data-ttu-id="b2644-105">Esto le permite supervisar las solicitudes de E/S y las respuestas que las bibliotecas de cliente realizan en los servicios de Azure.</span><span class="sxs-lookup"><span data-stu-id="b2644-105">This allows you to monitor I/O requests and responses that client libraries are making to Azure services.</span></span> <span data-ttu-id="b2644-106">Normalmente, los registros se usan para depurar o diagnosticar problemas de comunicación.</span><span class="sxs-lookup"><span data-stu-id="b2644-106">Typically, the logs are used to debug or diagnose communication issues.</span></span> <span data-ttu-id="b2644-107">En este artículo se describen tres enfoques para habilitar el registro con El SDK de Azure para .NET:</span><span class="sxs-lookup"><span data-stu-id="b2644-107">This article describes three approaches to enable logging with the Azure SDK for .NET:</span></span>

- <span data-ttu-id="b2644-108">Inicie sesión en la ventana de la consola</span><span class="sxs-lookup"><span data-stu-id="b2644-108">Log to the console window</span></span>
- <span data-ttu-id="b2644-109">Registro en seguimientos de diagnóstico de .NET</span><span class="sxs-lookup"><span data-stu-id="b2644-109">Log to .NET diagnostics traces</span></span>
- <span data-ttu-id="b2644-110">Configurar el registro personalizado</span><span class="sxs-lookup"><span data-stu-id="b2644-110">Configure custom logging</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2644-111">Este artículo se aplica a las bibliotecas de cliente que usan las versiones más recientes del SDK de Azure para .NET.</span><span class="sxs-lookup"><span data-stu-id="b2644-111">This article applies to client libraries that use the most recent versions of the Azure SDK for .NET.</span></span> <span data-ttu-id="b2644-112">Para ver si se admite una biblioteca, consulte la lista de [versiones más recientes](https://azure.github.io/azure-sdk/releases/latest/index.html)del SDK de Azure.</span><span class="sxs-lookup"><span data-stu-id="b2644-112">To see if a library is supported, refer to the list of [Azure SDK latest releases](https://azure.github.io/azure-sdk/releases/latest/index.html).</span></span> <span data-ttu-id="b2644-113">Si la aplicación usa una versión anterior de las bibliotecas de cliente del SDK de Azure, consulte las instrucciones específicas de la documentación del servicio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b2644-113">If your application is using an older version of the Azure SDK client libraries, refer to specific instructions in the applicable service documentation.</span></span>

## <a name="log-information"></a><span data-ttu-id="b2644-114">Información de registro</span><span class="sxs-lookup"><span data-stu-id="b2644-114">Log information</span></span>

<span data-ttu-id="b2644-115">El SDK registra la siguiente información, desinfectando los valores de encabezado y consulta de parámetros para quitar datos personales.</span><span class="sxs-lookup"><span data-stu-id="b2644-115">The SDK logs the following information, sanitizing parameter query and header values to remove personal data.</span></span>

<span data-ttu-id="b2644-116">Entrada de registro de solicitud HTTP:</span><span class="sxs-lookup"><span data-stu-id="b2644-116">HTTP request log entry:</span></span>

- <span data-ttu-id="b2644-117">Identificador único</span><span class="sxs-lookup"><span data-stu-id="b2644-117">Unique ID</span></span>
- <span data-ttu-id="b2644-118">HTTP method</span><span class="sxs-lookup"><span data-stu-id="b2644-118">HTTP method</span></span>
- <span data-ttu-id="b2644-119">URI</span><span class="sxs-lookup"><span data-stu-id="b2644-119">URI</span></span>
- <span data-ttu-id="b2644-120">Encabezados de solicitud saliente</span><span class="sxs-lookup"><span data-stu-id="b2644-120">Outgoing request headers</span></span>

<span data-ttu-id="b2644-121">Entrada de registro de respuesta HTTP:</span><span class="sxs-lookup"><span data-stu-id="b2644-121">HTTP response log entry:</span></span>

- <span data-ttu-id="b2644-122">Duración de la operación de E/S (tiempo transcurrido)</span><span class="sxs-lookup"><span data-stu-id="b2644-122">Duration of I/O operation (time elapsed)</span></span>
- <span data-ttu-id="b2644-123">Id. de solicitud</span><span class="sxs-lookup"><span data-stu-id="b2644-123">Request ID</span></span>
- <span data-ttu-id="b2644-124">Código de estado HTTP</span><span class="sxs-lookup"><span data-stu-id="b2644-124">HTTP status code</span></span>
- <span data-ttu-id="b2644-125">Frase de razón HTTP</span><span class="sxs-lookup"><span data-stu-id="b2644-125">HTTP reason phrase</span></span>
- <span data-ttu-id="b2644-126">Encabezados de respuesta</span><span class="sxs-lookup"><span data-stu-id="b2644-126">Response headers</span></span>
- <span data-ttu-id="b2644-127">Información de error, cuando corresponda</span><span class="sxs-lookup"><span data-stu-id="b2644-127">Error information, when applicable</span></span>

<span data-ttu-id="b2644-128">Para el contenido de solicitud y respuesta:</span><span class="sxs-lookup"><span data-stu-id="b2644-128">For request and response content:</span></span>

- <span data-ttu-id="b2644-129">Secuencia de contenido como texto o bytes en función del encabezado Content-Type.</span><span class="sxs-lookup"><span data-stu-id="b2644-129">Content stream as text or bytes depending on the Content-Type header.</span></span>
     > <span data-ttu-id="b2644-130">[! NOTA: el registro de contenido está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b2644-130">[!NOTE} Content logging is disabled by default.</span></span> <span data-ttu-id="b2644-131">Para habilitarlo, `Diagnostics.IsLoggingContentEnabled` `true` establezca `ClientOptions`en .</span><span class="sxs-lookup"><span data-stu-id="b2644-131">To enable it, set `Diagnostics.IsLoggingContentEnabled` to `true` in `ClientOptions`.</span></span>

<span data-ttu-id="b2644-132">Los registros de eventos son la salida generalmente en uno de estos tres niveles:</span><span class="sxs-lookup"><span data-stu-id="b2644-132">Event logs are output usually at one of these three levels:</span></span>

- <span data-ttu-id="b2644-133">Información para eventos de solicitud y respuesta</span><span class="sxs-lookup"><span data-stu-id="b2644-133">Informational for request and response events</span></span>
- <span data-ttu-id="b2644-134">Advertencia de errores</span><span class="sxs-lookup"><span data-stu-id="b2644-134">Warning for errors</span></span>
- <span data-ttu-id="b2644-135">Detallado para mensajes detallados y registro de contenido</span><span class="sxs-lookup"><span data-stu-id="b2644-135">Verbose for detailed messages and content logging</span></span>

## <a name="enable-logging-with-built-in-methods"></a><span data-ttu-id="b2644-136">Habilite el registro con métodos integrados</span><span class="sxs-lookup"><span data-stu-id="b2644-136">Enable logging with built-in methods</span></span>

<span data-ttu-id="b2644-137">Las bibliotecas de cliente de Azure SDK para .NET registran eventos en Seguimiento de eventos para Windows (ETW) a través de la [ `EventSource` clase,](/dotnet/api/system.diagnostics.tracing.eventsource)que es típica de .NET.</span><span class="sxs-lookup"><span data-stu-id="b2644-137">The Azure SDK for .NET client libraries log events to Event Tracing for Windows (ETW) via the [`EventSource` class](/dotnet/api/system.diagnostics.tracing.eventsource), which is typical for .NET.</span></span> <span data-ttu-id="b2644-138">Los orígenes de eventos le permiten usar el registro estructurado en el código de la aplicación con una sobrecarga de rendimiento mínima.</span><span class="sxs-lookup"><span data-stu-id="b2644-138">Event sources allow you to use structured logging in your application code with a minimal performance overhead.</span></span> <span data-ttu-id="b2644-139">Para obtener acceso a estos registros de eventos, debe registrar los detectores de eventos.</span><span class="sxs-lookup"><span data-stu-id="b2644-139">To gain access to these event logs, you need to register event listeners.</span></span>

<span data-ttu-id="b2644-140">El SDK `Azure.Core.Diagnostics.AzureEventSourceListener` incluye la clase (definida en el paquete NuGet de Azure.Core), que `CreateConsoleLogger` contiene `CreateTraceLogger`dos métodos estáticos que simplifican el registro completo de la aplicación .NET: y .</span><span class="sxs-lookup"><span data-stu-id="b2644-140">The SDK includes the `Azure.Core.Diagnostics.AzureEventSourceListener` class (defined in the Azure.Core NuGet package), which contains two static methods that simplify comprehensive logging for your .NET application: `CreateConsoleLogger` and `CreateTraceLogger`.</span></span> <span data-ttu-id="b2644-141">Estos métodos toman un parámetro opcional que especifica un nivel de registro.</span><span class="sxs-lookup"><span data-stu-id="b2644-141">These methods take an optional parameter that specifies a log level.</span></span>

### <a name="log-to-the-console-window"></a><span data-ttu-id="b2644-142">Inicie sesión en la ventana de la consola</span><span class="sxs-lookup"><span data-stu-id="b2644-142">Log to the console window</span></span>

<span data-ttu-id="b2644-143">Un principio principal de las bibliotecas de cliente de Azure SDK para .NET es simplificar la capacidad de ver registros completos en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="b2644-143">A core tenet of the Azure SDK for .NET client libraries is to simplify the ability to view comprehensive logs in real time.</span></span> <span data-ttu-id="b2644-144">El `CreateConsoleLogger` método le permite enviar registros a la ventana de la consola con una sola línea de código:</span><span class="sxs-lookup"><span data-stu-id="b2644-144">The `CreateConsoleLogger` method allows you to send logs to the console window with a single line of code:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateConsoleLogger();
```

### <a name="log-to-diagnostic-traces"></a><span data-ttu-id="b2644-145">Registro en los seguimientos de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="b2644-145">Log to diagnostic traces</span></span>

<span data-ttu-id="b2644-146">Si implementa agentes de escucha `CreateTraceLogger` de seguimiento, puede usar el método[`System.Diagnostics.Tracing`](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing)para iniciar sesión en el mecanismo de seguimiento de eventos estándar de .NET ( ).</span><span class="sxs-lookup"><span data-stu-id="b2644-146">If you implement trace listeners, you can use the `CreateTraceLogger` method to log to the standard .NET event tracing mechanism ([`System.Diagnostics.Tracing`](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing)).</span></span> <span data-ttu-id="b2644-147">Para obtener más información sobre el seguimiento de eventos en .NET, vea [Agentes de escucha](https://docs.microsoft.com/dotnet/framework/debug-trace-profile/trace-listeners)de seguimiento .</span><span class="sxs-lookup"><span data-stu-id="b2644-147">For more information on event tracing in .NET, see [Trace Listeners](https://docs.microsoft.com/dotnet/framework/debug-trace-profile/trace-listeners).</span></span> <span data-ttu-id="b2644-148">En este ejemplo se especifica un nivel de registro detallado:</span><span class="sxs-lookup"><span data-stu-id="b2644-148">This example specifies a log level of verbose:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateTraceLogger(EventLevel.Verbose);
```

## <a name="configure-custom-logging"></a><span data-ttu-id="b2644-149">Configurar el registro personalizado</span><span class="sxs-lookup"><span data-stu-id="b2644-149">Configure custom logging</span></span>

<span data-ttu-id="b2644-150">Como se mencionó anteriormente, debe registrar los detectores de eventos para recibir mensajes de registro del SDK de Azure para .NET.</span><span class="sxs-lookup"><span data-stu-id="b2644-150">As mentioned above, you need to register event listeners to receive log messages from the Azure SDK for .NET.</span></span> <span data-ttu-id="b2644-151">Si no desea implementar el registro completo mediante uno de los métodos `AzureEventSourceListener` simplificados anteriores, puede construir una instancia de la clase y pasarle una función de devolución de llamada que escriba.</span><span class="sxs-lookup"><span data-stu-id="b2644-151">If you don’t want to implement comprehensive logging using one the simplified methods above, you can construct an instance of the `AzureEventSourceListener` class and pass it a callback function that you write.</span></span> <span data-ttu-id="b2644-152">Este método recibirá mensajes de registro que puede procesar sin necesidad.</span><span class="sxs-lookup"><span data-stu-id="b2644-152">This method will receive log messages that you can process however you need to.</span></span> <span data-ttu-id="b2644-153">Además, al construir la instancia, puede especificar los niveles de registro que desea incluir.</span><span class="sxs-lookup"><span data-stu-id="b2644-153">In addition, when you construct the instance, you can specify the log levels to include.</span></span>

<span data-ttu-id="b2644-154">En el ejemplo siguiente se crea un detector de eventos que inicia sesión en la consola con un mensaje personalizado y se filtra a los eventos principales de Azure del nivel detallado.</span><span class="sxs-lookup"><span data-stu-id="b2644-154">The following example creates an event listener that logs to the console with a custom message, and is filtered to Azure core events of the level verbose.</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="b2644-155">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b2644-155">Next steps</span></span>

- [<span data-ttu-id="b2644-156">Habilitar el registro de diagnósticos para las aplicaciones de Azure App Service</span><span class="sxs-lookup"><span data-stu-id="b2644-156">Enable diagnostics logging for apps in Azure App Service</span></span>](https://docs.microsoft.com/azure/app-service/troubleshoot-diagnostic-logs)
- <span data-ttu-id="b2644-157">Revise las opciones de auditoría y registro de [seguridad de Azure](https://docs.microsoft.com/azure/security/fundamentals/log-audit)</span><span class="sxs-lookup"><span data-stu-id="b2644-157">Review [Azure security logging and auditing](https://docs.microsoft.com/azure/security/fundamentals/log-audit) options</span></span>
- <span data-ttu-id="b2644-158">Aprenda a trabajar con [los registros](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview) de la plataforma Azure</span><span class="sxs-lookup"><span data-stu-id="b2644-158">Learn how to work with [Azure platform logs](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview)</span></span>
- <span data-ttu-id="b2644-159">Obtenga más información sobre el registro y el seguimiento de [.NET Core](https://docs.microsoft.com/dotnet/core/diagnostics/logging-tracing)</span><span class="sxs-lookup"><span data-stu-id="b2644-159">Read more about [.NET Core logging and tracing](https://docs.microsoft.com/dotnet/core/diagnostics/logging-tracing)</span></span>
