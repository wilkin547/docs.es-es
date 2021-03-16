---
title: Registro de alto rendimiento en .NET
author: IEvangelist
description: Obtenga información sobre cómo usar LoggerMessage para crear delegados almacenables en caché que requieren menos asignaciones de objetos que los escenarios de registro de alto rendimiento.
ms.author: dapine
ms.date: 01/04/2021
ms.openlocfilehash: 0031ff7a9f70cb0cf724fdf6dfa4fbe0a44af7c1
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2021
ms.locfileid: "102402204"
---
# <a name="high-performance-logging-in-net"></a><span data-ttu-id="8526c-103">Registro de alto rendimiento en .NET</span><span class="sxs-lookup"><span data-stu-id="8526c-103">High-performance logging in .NET</span></span>

<span data-ttu-id="8526c-104">La clase <xref:Microsoft.Extensions.Logging.LoggerMessage> expone la funcionalidad para crear delegados almacenables en caché que requieren menos asignaciones de objetos y una menor sobrecarga computacional en comparación con los [métodos de extensión del registrador](xref:Microsoft.Extensions.Logging.LoggerExtensions), como <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogInformation%2A> y <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogDebug%2A>.</span><span class="sxs-lookup"><span data-stu-id="8526c-104">The <xref:Microsoft.Extensions.Logging.LoggerMessage> class exposes functionality to create cacheable delegates that require fewer object allocations and reduced computational overhead compared to [logger extension methods](xref:Microsoft.Extensions.Logging.LoggerExtensions), such as <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogInformation%2A> and <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogDebug%2A>.</span></span> <span data-ttu-id="8526c-105">Para escenarios de registro de alto rendimiento, use el patrón <xref:Microsoft.Extensions.Logging.LoggerMessage>.</span><span class="sxs-lookup"><span data-stu-id="8526c-105">For high-performance logging scenarios, use the <xref:Microsoft.Extensions.Logging.LoggerMessage> pattern.</span></span>

<span data-ttu-id="8526c-106"><xref:Microsoft.Extensions.Logging.LoggerMessage> proporciona las siguientes ventajas de rendimiento frente a los métodos de extensión del registrador:</span><span class="sxs-lookup"><span data-stu-id="8526c-106"><xref:Microsoft.Extensions.Logging.LoggerMessage> provides the following performance advantages over Logger extension methods:</span></span>

- <span data-ttu-id="8526c-107">Los métodos de extensión del registrador requieren la conversión boxing de tipos de valor, como `int`, en `object`.</span><span class="sxs-lookup"><span data-stu-id="8526c-107">Logger extension methods require "boxing" (converting) value types, such as `int`, into `object`.</span></span> <span data-ttu-id="8526c-108">El patrón <xref:Microsoft.Extensions.Logging.LoggerMessage> impide la conversión boxing mediante métodos de extensión y campos <xref:System.Action> estáticos con parámetros fuertemente tipados.</span><span class="sxs-lookup"><span data-stu-id="8526c-108">The <xref:Microsoft.Extensions.Logging.LoggerMessage> pattern avoids boxing by using static <xref:System.Action> fields and extension methods with strongly-typed parameters.</span></span>
- <span data-ttu-id="8526c-109">Los métodos de extensión del registrador deben analizar la plantilla de mensaje (cadena de formato con nombre) cada vez que se escribe un mensaje de registro.</span><span class="sxs-lookup"><span data-stu-id="8526c-109">Logger extension methods must parse the message template (named format string) every time a log message is written.</span></span> <span data-ttu-id="8526c-110"><xref:Microsoft.Extensions.Logging.LoggerMessage> solo necesita analizar una vez una plantilla cuando se define el mensaje.</span><span class="sxs-lookup"><span data-stu-id="8526c-110"><xref:Microsoft.Extensions.Logging.LoggerMessage> only requires parsing a template once when the message is defined.</span></span>

<span data-ttu-id="8526c-111">En la aplicación de ejemplo se muestran características <xref:Microsoft.Extensions.Logging.LoggerMessage> con un servicio de trabajo de procesamiento de cola prioritario.</span><span class="sxs-lookup"><span data-stu-id="8526c-111">The sample app demonstrates <xref:Microsoft.Extensions.Logging.LoggerMessage> features with a priority queue processing worker service.</span></span> <span data-ttu-id="8526c-112">La aplicación procesa los elementos de trabajo por orden de prioridad.</span><span class="sxs-lookup"><span data-stu-id="8526c-112">The app processes work items in priority order.</span></span> <span data-ttu-id="8526c-113">A medida que se producen estas operaciones, se generan mensajes de registro mediante el patrón <xref:Microsoft.Extensions.Logging.LoggerMessage>.</span><span class="sxs-lookup"><span data-stu-id="8526c-113">As these operations occur, log messages are generated using the <xref:Microsoft.Extensions.Logging.LoggerMessage> pattern.</span></span>

## <a name="define-a-logger-message"></a><span data-ttu-id="8526c-114">Definición de un mensaje del registrador</span><span class="sxs-lookup"><span data-stu-id="8526c-114">Define a logger message</span></span>

<span data-ttu-id="8526c-115">Use [Define(LogLevel, EventId, String)](xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A) para crear un delegado <xref:System.Action> para registrar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="8526c-115">Use [Define(LogLevel, EventId, String)](xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A) to create an <xref:System.Action> delegate for logging a message.</span></span> <span data-ttu-id="8526c-116">Las sobrecargas <xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> permiten pasar hasta seis parámetros de tipo a una cadena de formato con nombre (plantilla).</span><span class="sxs-lookup"><span data-stu-id="8526c-116"><xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> overloads permit passing up to six type parameters to a named format string (template).</span></span>

<span data-ttu-id="8526c-117">La cadena proporcionada al método <xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> es una plantilla y no una cadena interpolada.</span><span class="sxs-lookup"><span data-stu-id="8526c-117">The string provided to the <xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> method is a template and not an interpolated string.</span></span> <span data-ttu-id="8526c-118">Los marcadores de posición se rellenan en el orden en que se especifican los tipos.</span><span class="sxs-lookup"><span data-stu-id="8526c-118">Placeholders are filled in the order that the types are specified.</span></span> <span data-ttu-id="8526c-119">Los nombres de los marcadores de posición en la plantilla deben ser descriptivos y coherentes entre las plantillas.</span><span class="sxs-lookup"><span data-stu-id="8526c-119">Placeholder names in the template should be descriptive and consistent across templates.</span></span> <span data-ttu-id="8526c-120">Sirven como nombres de propiedad en los datos estructurados del registro.</span><span class="sxs-lookup"><span data-stu-id="8526c-120">They serve as property names within structured log data.</span></span> <span data-ttu-id="8526c-121">Se recomienda el uso de la [grafía Pascal](../../standard/design-guidelines/capitalization-conventions.md) para los nombres de los marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="8526c-121">We recommend [Pascal casing](../../standard/design-guidelines/capitalization-conventions.md) for placeholder names.</span></span> <span data-ttu-id="8526c-122">Por ejemplo: `{Item}`, `{DateTime}`.</span><span class="sxs-lookup"><span data-stu-id="8526c-122">For example, `{Item}`, `{DateTime}`.</span></span>

<span data-ttu-id="8526c-123">Cada mensaje de registro es un delegado <xref:System.Action> que se mantiene en un campo estático creado por [LoggerMessage.Define](xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A).</span><span class="sxs-lookup"><span data-stu-id="8526c-123">Each log message is an <xref:System.Action> held in a static field created by [LoggerMessage.Define](xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A).</span></span> <span data-ttu-id="8526c-124">Por ejemplo, la aplicación de ejemplo crea un campo para describir un mensaje de registro para procesar los elementos de trabajo:</span><span class="sxs-lookup"><span data-stu-id="8526c-124">For example, the sample app creates a field to describe a log message for the processing of work items:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="FailedProcessingField":::

<span data-ttu-id="8526c-125">Especifique lo siguiente para el delegado <xref:System.Action>:</span><span class="sxs-lookup"><span data-stu-id="8526c-125">For the <xref:System.Action>, specify:</span></span>

- <span data-ttu-id="8526c-126">El nivel de registro.</span><span class="sxs-lookup"><span data-stu-id="8526c-126">The log level.</span></span>
- <span data-ttu-id="8526c-127">Un identificador de evento único (<xref:Microsoft.Extensions.Logging.EventId>) con el nombre del método de extensión estático.</span><span class="sxs-lookup"><span data-stu-id="8526c-127">A unique event identifier (<xref:Microsoft.Extensions.Logging.EventId>) with the name of the static extension method.</span></span>
- <span data-ttu-id="8526c-128">La plantilla de mensaje (cadena de formato con nombre).</span><span class="sxs-lookup"><span data-stu-id="8526c-128">The message template (named format string).</span></span>

<span data-ttu-id="8526c-129">A medida que los elementos de trabajo se quitan de la cola para el procesamiento, la aplicación de servicio de trabajo establece lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8526c-129">As work items are dequeued for processing the worker service app sets the:</span></span>

- <span data-ttu-id="8526c-130">El nivel de registro en <xref:Microsoft.Extensions.Logging.LogLevel.Critical?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8526c-130">Log level to <xref:Microsoft.Extensions.Logging.LogLevel.Critical?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="8526c-131">El identificador de evento en `13` con el nombre del método `FailedToProcessWorkItem`.</span><span class="sxs-lookup"><span data-stu-id="8526c-131">Event id to `13` with the name of the `FailedToProcessWorkItem` method.</span></span>
- <span data-ttu-id="8526c-132">La plantilla de mensaje (cadena de formato con nombre) en una cadena.</span><span class="sxs-lookup"><span data-stu-id="8526c-132">Message template (named format string) to a string.</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="FailedProcessingAssignment":::

<span data-ttu-id="8526c-133">Los almacenes de registro estructurado pueden usar el nombre de evento cuando se suministra con el identificador de evento para enriquecer el registro.</span><span class="sxs-lookup"><span data-stu-id="8526c-133">Structured logging stores may use the event name when it's supplied with the event id to enrich logging.</span></span> <span data-ttu-id="8526c-134">Por ejemplo, [Serilog](https://github.com/serilog/serilog-extensions-logging) usa el nombre de evento.</span><span class="sxs-lookup"><span data-stu-id="8526c-134">For example, [Serilog](https://github.com/serilog/serilog-extensions-logging) uses the event name.</span></span>

<span data-ttu-id="8526c-135">El delegado <xref:System.Action> se invoca mediante un método de extensión fuertemente tipado.</span><span class="sxs-lookup"><span data-stu-id="8526c-135">The <xref:System.Action> is invoked through a strongly-typed extension method.</span></span> <span data-ttu-id="8526c-136">El método `PriorityItemProcessed` registra un mensaje cada vez que se procesa un elemento de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8526c-136">The `PriorityItemProcessed` method logs a message every time a work item is being processed.</span></span> <span data-ttu-id="8526c-137">En cambio, se llama a `FailedToProcessWorkItem` cuando se produce una excepción:</span><span class="sxs-lookup"><span data-stu-id="8526c-137">Whereas, `FailedToProcessWorkItem` is called when (and if) an exception occurs:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Worker.cs" range="18-39" highlight="15-18":::

<span data-ttu-id="8526c-138">Inspeccione la salida de la consola de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="8526c-138">Inspect the app's console output:</span></span>

```console
crit: WorkerServiceOptions.Example.Worker[13]
      Epic failure processing item!
      System.Exception: Failed to verify communications.
         at WorkerServiceOptions.Example.Worker.ExecuteAsync(CancellationToken stoppingToken) in
         ..\Worker.cs:line 27
```

<span data-ttu-id="8526c-139">Para pasar parámetros a un mensaje de registro, defina hasta seis tipos al crear el campo estático.</span><span class="sxs-lookup"><span data-stu-id="8526c-139">To pass parameters to a log message, define up to six types when creating the static field.</span></span> <span data-ttu-id="8526c-140">La aplicación de ejemplo registra los detalles del elemento de trabajo al procesar los elementos definiendo un tipo `WorkItem` para el campo <xref:System.Action>:</span><span class="sxs-lookup"><span data-stu-id="8526c-140">The sample app logs the work item details when processing items by defining a `WorkItem` type for the <xref:System.Action> field:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingItemField":::

<span data-ttu-id="8526c-141">La plantilla de mensaje de registro del delegado recibe sus valores de marcador de posición a partir de los tipos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="8526c-141">The delegate's log message template receives its placeholder values from the types provided.</span></span> <span data-ttu-id="8526c-142">La aplicación de ejemplo define un delegado para agregar un elemento de trabajo cuando el parámetro del elemento es `WorkItem`:</span><span class="sxs-lookup"><span data-stu-id="8526c-142">The sample app defines a delegate for adding a work item where the item parameter is a `WorkItem`:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingItemAssignment":::

<span data-ttu-id="8526c-143">El método de extensión estático para registrar que se está procesando un elemento de trabajo, `PriorityItemProcessed`, recibe el valor de argumento del elemento de trabajo y lo pasa al delegado <xref:System.Action>:</span><span class="sxs-lookup"><span data-stu-id="8526c-143">The static extension method for logging that a work item is being processed, `PriorityItemProcessed`, receives the work item argument value and passes it to the <xref:System.Action> delegate:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingItemMethod":::

<span data-ttu-id="8526c-144">En el método `ExecuteAsync` del servicio de trabajo, se llama a `PriorityItemProcessed` para registrar el mensaje:</span><span class="sxs-lookup"><span data-stu-id="8526c-144">In the worker service's `ExecuteAsync` method, `PriorityItemProcessed` is called to log the message:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Worker.cs" range="18-39" highlight="12":::

<span data-ttu-id="8526c-145">Inspeccione la salida de la consola de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="8526c-145">Inspect the app's console output:</span></span>

```console
info: WorkerServiceOptions.Example.Worker[1]
      Processing priority item: Priority-Extreme (50db062a-9732-4418-936d-110549ad79e4): 'Verify communications'
```

## <a name="define-logger-message-scope"></a><span data-ttu-id="8526c-146">Definición del ámbito del mensaje del registrador</span><span class="sxs-lookup"><span data-stu-id="8526c-146">Define logger message scope</span></span>

<span data-ttu-id="8526c-147">El método [DefineScope(string)](xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A) crea un delegado <xref:System.Func%601> para definir un [ámbito de registro](logging.md#log-scopes).</span><span class="sxs-lookup"><span data-stu-id="8526c-147">The [DefineScope(string)](xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A) method creates a <xref:System.Func%601> delegate for defining a [log scope](logging.md#log-scopes).</span></span> <span data-ttu-id="8526c-148">Las sobrecargas <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> permiten pasar hasta tres parámetros de tipo a una cadena de formato con nombre (plantilla).</span><span class="sxs-lookup"><span data-stu-id="8526c-148"><xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> overloads permit passing up to three type parameters to a named format string (template).</span></span>

<span data-ttu-id="8526c-149">Al igual que sucede con el método <xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A>, la cadena proporcionada al método <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> es una plantilla y no una cadena interpolada.</span><span class="sxs-lookup"><span data-stu-id="8526c-149">As is the case with the <xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> method, the string provided to the <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> method is a template and not an interpolated string.</span></span> <span data-ttu-id="8526c-150">Los marcadores de posición se rellenan en el orden en que se especifican los tipos.</span><span class="sxs-lookup"><span data-stu-id="8526c-150">Placeholders are filled in the order that the types are specified.</span></span> <span data-ttu-id="8526c-151">Los nombres de los marcadores de posición en la plantilla deben ser descriptivos y coherentes entre las plantillas.</span><span class="sxs-lookup"><span data-stu-id="8526c-151">Placeholder names in the template should be descriptive and consistent across templates.</span></span> <span data-ttu-id="8526c-152">Sirven como nombres de propiedad en los datos estructurados del registro.</span><span class="sxs-lookup"><span data-stu-id="8526c-152">They serve as property names within structured log data.</span></span> <span data-ttu-id="8526c-153">Se recomienda el uso de la [grafía Pascal](../../standard/design-guidelines/capitalization-conventions.md) para los nombres de los marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="8526c-153">We recommend [Pascal casing](../../standard/design-guidelines/capitalization-conventions.md) for placeholder names.</span></span> <span data-ttu-id="8526c-154">Por ejemplo: `{Item}`, `{DateTime}`.</span><span class="sxs-lookup"><span data-stu-id="8526c-154">For example, `{Item}`, `{DateTime}`.</span></span>

<span data-ttu-id="8526c-155">Defina un [ámbito de registro](logging.md#log-scopes) para aplicarlo a una serie de mensajes de registro mediante el método <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A>.</span><span class="sxs-lookup"><span data-stu-id="8526c-155">Define a [log scope](logging.md#log-scopes) to apply to a series of log messages using the <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> method.</span></span> <span data-ttu-id="8526c-156">Habilite `IncludeScopes` en la sección del registrador de la consola de *appsettings.json*:</span><span class="sxs-lookup"><span data-stu-id="8526c-156">Enable `IncludeScopes` in the console logger section of *appsettings.json*:</span></span>

:::code language="json" source="snippets/configuration/worker-service-options/appsettings.json" highlight="3-5":::

<span data-ttu-id="8526c-157">Para crear un ámbito de registro, agregue un campo para que contenga un delegado <xref:System.Func%601> para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="8526c-157">To create a log scope, add a field to hold a <xref:System.Func%601> delegate for the scope.</span></span> <span data-ttu-id="8526c-158">La aplicación de ejemplo crea un campo denominado `_processingWorkScope` (*Internal/LoggerExtensions.cs*):</span><span class="sxs-lookup"><span data-stu-id="8526c-158">The sample app creates a field called `_processingWorkScope` (*Internal/LoggerExtensions.cs*):</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkField":::

<span data-ttu-id="8526c-159">Use <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> para crear el delegado.</span><span class="sxs-lookup"><span data-stu-id="8526c-159">Use <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> to create the delegate.</span></span> <span data-ttu-id="8526c-160">Pueden especificarse hasta tres tipos para usarlos como argumentos de plantilla cuando se invoca el delegado.</span><span class="sxs-lookup"><span data-stu-id="8526c-160">Up to three types can be specified for use as template arguments when the delegate is invoked.</span></span> <span data-ttu-id="8526c-161">La aplicación de ejemplo usa una plantilla de mensaje que incluye la fecha y hora en que se inició el procesamiento:</span><span class="sxs-lookup"><span data-stu-id="8526c-161">The sample app uses a message template that includes the date time in which processing started:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkAssignment":::

<span data-ttu-id="8526c-162">Proporcione un método de extensión estático para el mensaje de registro.</span><span class="sxs-lookup"><span data-stu-id="8526c-162">Provide a static extension method for the log message.</span></span> <span data-ttu-id="8526c-163">Incluya todos los parámetros de tipo para propiedades con nombre que aparezcan en la plantilla de mensaje.</span><span class="sxs-lookup"><span data-stu-id="8526c-163">Include any type parameters for named properties that appear in the message template.</span></span> <span data-ttu-id="8526c-164">La aplicación de ejemplo adopta `DateTime` para una marca de tiempo personalizada para el registro y devuelve `_processingWorkScope`:</span><span class="sxs-lookup"><span data-stu-id="8526c-164">The sample app takes in a `DateTime` for a custom time stamp to log and returns `_processingWorkScope`:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkMethod":::

<span data-ttu-id="8526c-165">El ámbito encapsula las llamadas a la extensión de registro en un bloque [using](../../csharp/language-reference/keywords/using-statement.md):</span><span class="sxs-lookup"><span data-stu-id="8526c-165">The scope wraps the logging extension calls in a [using](../../csharp/language-reference/keywords/using-statement.md) block:</span></span>

:::code language="csharp" source="snippets/configuration/worker-service-options/Worker.cs" range="18-39" highlight="4":::

<span data-ttu-id="8526c-166">Inspeccione los mensajes de registro en la salida de la consola de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8526c-166">Inspect the log messages in the app's console output.</span></span> <span data-ttu-id="8526c-167">El resultado siguiente muestra el orden de prioridad de los mensajes de registro con el mensaje de ámbito de registro incluido:</span><span class="sxs-lookup"><span data-stu-id="8526c-167">The following result shows priority ordering of log messages with the log scope message included:</span></span>

```console
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Extreme (f5090ede-a337-4041-b914-f6bc0db5ae64): 'Verify communications'
info: Microsoft.Hosting.Lifetime[0]
      Application started. Press Ctrl+C to shut down.
info: Microsoft.Hosting.Lifetime[0]
      Hosting environment: Development
info: Microsoft.Hosting.Lifetime[0]
      Content root path: ..\worker-service-options
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-High (496d440f-2007-4391-b179-09d75ab52373): 'Validate collection'
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Medium (dea9e3f4-d7df-46d2-b7cd-5e0232eb98a5): 'Propagate selections'
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Medium (089d7f0d-da72-4b55-92fe-57b147838056): 'Enter pooling [contention]'
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Low (6e68c4be-089f-4450-9080-1ea63fcbb686): 'Health check network'
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Deferred (6f324134-6bb6-455f-81d4-553ab307c421): 'Ping weather service'
info: WorkerServiceOptions.Example.Worker[1]
      => Processing work, started at: 09/25/2020 14:30:45
      Processing priority item: Priority-Deferred (37bf736c-7a26-4a2a-9e56-e89bcf3b8f35): 'Set process state'
```

## <a name="see-also"></a><span data-ttu-id="8526c-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="8526c-168">See also</span></span>

- [<span data-ttu-id="8526c-169">Registro en .NET</span><span class="sxs-lookup"><span data-stu-id="8526c-169">Logging in .NET</span></span>](logging.md)
