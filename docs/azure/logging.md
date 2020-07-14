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
# <a name="logging-with-the-azure-sdk-for-net"></a><span data-ttu-id="a6e5a-103">Registro con Azure SDK para .NET</span><span class="sxs-lookup"><span data-stu-id="a6e5a-103">Logging with the Azure SDK for .NET</span></span>

<span data-ttu-id="a6e5a-104">Las bibliotecas cliente de [Azure SDK](https://azure.microsoft.com/downloads/) para .NET incluyen la posibilidad de registrar operaciones de la biblioteca cliente.</span><span class="sxs-lookup"><span data-stu-id="a6e5a-104">The [Azure SDK](https://azure.microsoft.com/downloads/) for .NET client libraries includes the ability to log client library operations.</span></span> <span data-ttu-id="a6e5a-105">Esto le permite supervisar las solicitudes de E/S y las respuestas que las bibliotecas cliente realizan en los servicios de Azure.</span><span class="sxs-lookup"><span data-stu-id="a6e5a-105">This allows you to monitor I/O requests and responses that client libraries are making to Azure services.</span></span> <span data-ttu-id="a6e5a-106">Normalmente, los registros se usan para depurar o diagnosticar problemas de comunicación.</span><span class="sxs-lookup"><span data-stu-id="a6e5a-106">Typically, the logs are used to debug or diagnose communication issues.</span></span> <span data-ttu-id="a6e5a-107">En este artículo se describen tres métodos para habilitar el registro con Azure SDK para .NET:</span><span class="sxs-lookup"><span data-stu-id="a6e5a-107">This article describes three approaches to enable logging with the Azure SDK for .NET:</span></span>

- <span data-ttu-id="a6e5a-108">Inicio de sesión en la ventana de consola</span><span class="sxs-lookup"><span data-stu-id="a6e5a-108">Log to the console window</span></span>
- <span data-ttu-id="a6e5a-109">Registro en seguimientos de diagnósticos de .NET</span><span class="sxs-lookup"><span data-stu-id="a6e5a-109">Log to .NET diagnostics traces</span></span>
- <span data-ttu-id="a6e5a-110">Configuración del registro personalizado</span><span class="sxs-lookup"><span data-stu-id="a6e5a-110">Configure custom logging</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6e5a-111">Este artículo se aplica a las bibliotecas cliente que usan las versiones más recientes de Azure SDK para .NET.</span><span class="sxs-lookup"><span data-stu-id="a6e5a-111">This article applies to client libraries that use the most recent versions of the Azure SDK for .NET.</span></span> <span data-ttu-id="a6e5a-112">Para ver si se admite una biblioteca, consulte la lista de [versiones más recientes del SDK de Azure](https://azure.github.io/azure-sdk/releases/latest/index.html).</span><span class="sxs-lookup"><span data-stu-id="a6e5a-112">To see if a library is supported, refer to the list of [Azure SDK latest releases](https://azure.github.io/azure-sdk/releases/latest/index.html).</span></span> <span data-ttu-id="a6e5a-113">Si su aplicación usa una versión anterior de las bibliotecas cliente del SDK de Azure, consulte las instrucciones específicas de la documentación del servicio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a6e5a-113">If your application is using an older version of the Azure SDK client libraries, refer to specific instructions in the applicable service documentation.</span></span>

## <a name="log-information"></a><span data-ttu-id="a6e5a-114">Información de registro</span><span class="sxs-lookup"><span data-stu-id="a6e5a-114">Log information</span></span>

<span data-ttu-id="a6e5a-115">El SDK registra la siguiente información, depurando los valores de encabezado y consulta de los parámetros para quitar datos personales.</span><span class="sxs-lookup"><span data-stu-id="a6e5a-115">The SDK logs the following information, sanitizing parameter query and header values to remove personal data.</span></span>

<span data-ttu-id="a6e5a-116">Entrada del registro de solicitudes HTTP:</span><span class="sxs-lookup"><span data-stu-id="a6e5a-116">HTTP request log entry:</span></span>

- <span data-ttu-id="a6e5a-117">Id. único</span><span class="sxs-lookup"><span data-stu-id="a6e5a-117">Unique ID</span></span>
- <span data-ttu-id="a6e5a-118">HTTP method</span><span class="sxs-lookup"><span data-stu-id="a6e5a-118">HTTP method</span></span>
- <span data-ttu-id="a6e5a-119">Identificador URI</span><span class="sxs-lookup"><span data-stu-id="a6e5a-119">URI</span></span>
- <span data-ttu-id="a6e5a-120">Encabezados de solicitudes salientes</span><span class="sxs-lookup"><span data-stu-id="a6e5a-120">Outgoing request headers</span></span>

<span data-ttu-id="a6e5a-121">Entrada del registro de respuestas HTTP:</span><span class="sxs-lookup"><span data-stu-id="a6e5a-121">HTTP response log entry:</span></span>

- <span data-ttu-id="a6e5a-122">Duración de la operación de E/S (tiempo transcurrido)</span><span class="sxs-lookup"><span data-stu-id="a6e5a-122">Duration of I/O operation (time elapsed)</span></span>
- <span data-ttu-id="a6e5a-123">Id. de solicitud</span><span class="sxs-lookup"><span data-stu-id="a6e5a-123">Request ID</span></span>
- <span data-ttu-id="a6e5a-124">Código de estado HTTP</span><span class="sxs-lookup"><span data-stu-id="a6e5a-124">HTTP status code</span></span>
- <span data-ttu-id="a6e5a-125">Oración de motivo HTTP</span><span class="sxs-lookup"><span data-stu-id="a6e5a-125">HTTP reason phrase</span></span>
- <span data-ttu-id="a6e5a-126">Encabezados de respuesta</span><span class="sxs-lookup"><span data-stu-id="a6e5a-126">Response headers</span></span>
- <span data-ttu-id="a6e5a-127">Información de error, cuando proceda</span><span class="sxs-lookup"><span data-stu-id="a6e5a-127">Error information, when applicable</span></span>

<span data-ttu-id="a6e5a-128">Para el contenido de la solicitud y la respuesta:</span><span class="sxs-lookup"><span data-stu-id="a6e5a-128">For request and response content:</span></span>

- <span data-ttu-id="a6e5a-129">Flujo de contenido como texto o bytes, según el encabezado Content-Type.</span><span class="sxs-lookup"><span data-stu-id="a6e5a-129">Content stream as text or bytes depending on the Content-Type header.</span></span>
     > <span data-ttu-id="a6e5a-130">Nota: El registro de contenido está deshabilitado de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a6e5a-130">[!NOTE} Content logging is disabled by default.</span></span> <span data-ttu-id="a6e5a-131">Para habilitarlo, cambie `Diagnostics.IsLoggingContentEnabled` a `true` en `ClientOptions`.</span><span class="sxs-lookup"><span data-stu-id="a6e5a-131">To enable it, set `Diagnostics.IsLoggingContentEnabled` to `true` in `ClientOptions`.</span></span>

<span data-ttu-id="a6e5a-132">Los registros de eventos se generan normalmente en uno de estos tres niveles:</span><span class="sxs-lookup"><span data-stu-id="a6e5a-132">Event logs are output usually at one of these three levels:</span></span>

- <span data-ttu-id="a6e5a-133">Información para eventos de solicitud y respuesta</span><span class="sxs-lookup"><span data-stu-id="a6e5a-133">Informational for request and response events</span></span>
- <span data-ttu-id="a6e5a-134">Advertencia para errores</span><span class="sxs-lookup"><span data-stu-id="a6e5a-134">Warning for errors</span></span>
- <span data-ttu-id="a6e5a-135">Detallado para mensajes detallados y registro de contenido</span><span class="sxs-lookup"><span data-stu-id="a6e5a-135">Verbose for detailed messages and content logging</span></span>

## <a name="enable-logging-with-built-in-methods"></a><span data-ttu-id="a6e5a-136">Habilitación del registro con métodos integrados</span><span class="sxs-lookup"><span data-stu-id="a6e5a-136">Enable logging with built-in methods</span></span>

<span data-ttu-id="a6e5a-137">Las bibliotecas cliente de Azure SDK para .NET registran eventos en Seguimiento de eventos para Windows (ETW) mediante la [clase `EventSource`](/dotnet/api/system.diagnostics.tracing.eventsource), que es habitual para .NET.</span><span class="sxs-lookup"><span data-stu-id="a6e5a-137">The Azure SDK for .NET client libraries log events to Event Tracing for Windows (ETW) via the [`EventSource` class](/dotnet/api/system.diagnostics.tracing.eventsource), which is typical for .NET.</span></span> <span data-ttu-id="a6e5a-138">Los orígenes de eventos permiten usar el registro estructurado en el código de aplicación con una sobrecarga de rendimiento mínima.</span><span class="sxs-lookup"><span data-stu-id="a6e5a-138">Event sources allow you to use structured logging in your application code with a minimal performance overhead.</span></span> <span data-ttu-id="a6e5a-139">Para obtener acceso a estos registros de eventos, debe registrar agentes de escucha de eventos.</span><span class="sxs-lookup"><span data-stu-id="a6e5a-139">To gain access to these event logs, you need to register event listeners.</span></span>

<span data-ttu-id="a6e5a-140">El SDK incluye la clase `Azure.Core.Diagnostics.AzureEventSourceListener` (definida en el paquete Azure.Core NuGet), que contiene dos métodos estáticos que simplifican el registro completo de la aplicación .NET: `CreateConsoleLogger` y `CreateTraceLogger`.</span><span class="sxs-lookup"><span data-stu-id="a6e5a-140">The SDK includes the `Azure.Core.Diagnostics.AzureEventSourceListener` class (defined in the Azure.Core NuGet package), which contains two static methods that simplify comprehensive logging for your .NET application: `CreateConsoleLogger` and `CreateTraceLogger`.</span></span> <span data-ttu-id="a6e5a-141">Estos métodos adoptan un parámetro opcional que especifica un nivel de registro.</span><span class="sxs-lookup"><span data-stu-id="a6e5a-141">These methods take an optional parameter that specifies a log level.</span></span>

### <a name="log-to-the-console-window"></a><span data-ttu-id="a6e5a-142">Inicio de sesión en la ventana de consola</span><span class="sxs-lookup"><span data-stu-id="a6e5a-142">Log to the console window</span></span>

<span data-ttu-id="a6e5a-143">Un principio básico de las bibliotecas cliente de Azure SDK para .NET es simplificar la capacidad de ver registros completos en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="a6e5a-143">A core tenet of the Azure SDK for .NET client libraries is to simplify the ability to view comprehensive logs in real time.</span></span> <span data-ttu-id="a6e5a-144">El método `CreateConsoleLogger` permite enviar registros a la ventana de la consola con una sola línea de código:</span><span class="sxs-lookup"><span data-stu-id="a6e5a-144">The `CreateConsoleLogger` method allows you to send logs to the console window with a single line of code:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateConsoleLogger();
```

### <a name="log-to-diagnostic-traces"></a><span data-ttu-id="a6e5a-145">Registro para el seguimiento de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="a6e5a-145">Log to diagnostic traces</span></span>

<span data-ttu-id="a6e5a-146">Si implementa agentes de escucha de seguimiento, puede usar el método `CreateTraceLogger` para registrarse en el mecanismo de seguimiento de eventos estándar de .NET ([`System.Diagnostics.Tracing`](/dotnet/api/system.diagnostics.tracing)).</span><span class="sxs-lookup"><span data-stu-id="a6e5a-146">If you implement trace listeners, you can use the `CreateTraceLogger` method to log to the standard .NET event tracing mechanism ([`System.Diagnostics.Tracing`](/dotnet/api/system.diagnostics.tracing)).</span></span> <span data-ttu-id="a6e5a-147">Para obtener más información sobre el seguimiento de eventos en .NET, vea [Agentes de escucha de seguimiento](/dotnet/framework/debug-trace-profile/trace-listeners).</span><span class="sxs-lookup"><span data-stu-id="a6e5a-147">For more information on event tracing in .NET, see [Trace Listeners](/dotnet/framework/debug-trace-profile/trace-listeners).</span></span> <span data-ttu-id="a6e5a-148">En este ejemplo se especifica un nivel de registro detallado:</span><span class="sxs-lookup"><span data-stu-id="a6e5a-148">This example specifies a log level of verbose:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateTraceLogger(EventLevel.Verbose);
```

## <a name="configure-custom-logging"></a><span data-ttu-id="a6e5a-149">Configuración del registro personalizado</span><span class="sxs-lookup"><span data-stu-id="a6e5a-149">Configure custom logging</span></span>

<span data-ttu-id="a6e5a-150">Como se mencionó anteriormente, debe registrar los agentes de escucha de eventos para recibir mensajes de registro de Azure SDK para .NET.</span><span class="sxs-lookup"><span data-stu-id="a6e5a-150">As mentioned above, you need to register event listeners to receive log messages from the Azure SDK for .NET.</span></span> <span data-ttu-id="a6e5a-151">Si no quiere implementar un registro completo con uno de los métodos simplificados anteriores, puede construir una instancia de la clase `AzureEventSourceListener` y pasarle una función de devolución de llamada que usted mismo escriba.</span><span class="sxs-lookup"><span data-stu-id="a6e5a-151">If you don’t want to implement comprehensive logging using one the simplified methods above, you can construct an instance of the `AzureEventSourceListener` class and pass it a callback function that you write.</span></span> <span data-ttu-id="a6e5a-152">Este método recibirá mensajes de registro que se pueden procesar en caso que sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a6e5a-152">This method will receive log messages that you can process however you need to.</span></span> <span data-ttu-id="a6e5a-153">Además, cuando se crea la instancia, se pueden especificar los niveles de registro que se van a incluir.</span><span class="sxs-lookup"><span data-stu-id="a6e5a-153">In addition, when you construct the instance, you can specify the log levels to include.</span></span>

<span data-ttu-id="a6e5a-154">En el ejemplo siguiente, se crea un agente de escucha de eventos que se registra en la consola con un mensaje personalizado y se filtra a los eventos principales de Azure del nivel detallado.</span><span class="sxs-lookup"><span data-stu-id="a6e5a-154">The following example creates an event listener that logs to the console with a custom message, and is filtered to Azure core events of the level verbose.</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="a6e5a-155">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a6e5a-155">Next steps</span></span>

- [<span data-ttu-id="a6e5a-156">Habilitar el registro de diagnósticos para las aplicaciones en Azure App Service</span><span class="sxs-lookup"><span data-stu-id="a6e5a-156">Enable diagnostics logging for apps in Azure App Service</span></span>](/azure/app-service/troubleshoot-diagnostic-logs)
- <span data-ttu-id="a6e5a-157">Revisar las opciones de [auditoría y registro de seguridad de Azure](/azure/security/fundamentals/log-audit)</span><span class="sxs-lookup"><span data-stu-id="a6e5a-157">Review [Azure security logging and auditing](/azure/security/fundamentals/log-audit) options</span></span>
- <span data-ttu-id="a6e5a-158">Más información sobre cómo trabajar con los [registros de la plataforma de Azure](/azure/azure-monitor/platform/platform-logs-overview)</span><span class="sxs-lookup"><span data-stu-id="a6e5a-158">Learn how to work with [Azure platform logs](/azure/azure-monitor/platform/platform-logs-overview)</span></span>
- <span data-ttu-id="a6e5a-159">Más información sobre el [registro y el seguimiento de.NET Core](/dotnet/core/diagnostics/logging-tracing)</span><span class="sxs-lookup"><span data-stu-id="a6e5a-159">Read more about [.NET Core logging and tracing](/dotnet/core/diagnostics/logging-tracing)</span></span>
