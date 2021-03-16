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
# <a name="high-performance-logging-in-net"></a>Registro de alto rendimiento en .NET

La clase <xref:Microsoft.Extensions.Logging.LoggerMessage> expone la funcionalidad para crear delegados almacenables en caché que requieren menos asignaciones de objetos y una menor sobrecarga computacional en comparación con los [métodos de extensión del registrador](xref:Microsoft.Extensions.Logging.LoggerExtensions), como <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogInformation%2A> y <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogDebug%2A>. Para escenarios de registro de alto rendimiento, use el patrón <xref:Microsoft.Extensions.Logging.LoggerMessage>.

<xref:Microsoft.Extensions.Logging.LoggerMessage> proporciona las siguientes ventajas de rendimiento frente a los métodos de extensión del registrador:

- Los métodos de extensión del registrador requieren la conversión boxing de tipos de valor, como `int`, en `object`. El patrón <xref:Microsoft.Extensions.Logging.LoggerMessage> impide la conversión boxing mediante métodos de extensión y campos <xref:System.Action> estáticos con parámetros fuertemente tipados.
- Los métodos de extensión del registrador deben analizar la plantilla de mensaje (cadena de formato con nombre) cada vez que se escribe un mensaje de registro. <xref:Microsoft.Extensions.Logging.LoggerMessage> solo necesita analizar una vez una plantilla cuando se define el mensaje.

En la aplicación de ejemplo se muestran características <xref:Microsoft.Extensions.Logging.LoggerMessage> con un servicio de trabajo de procesamiento de cola prioritario. La aplicación procesa los elementos de trabajo por orden de prioridad. A medida que se producen estas operaciones, se generan mensajes de registro mediante el patrón <xref:Microsoft.Extensions.Logging.LoggerMessage>.

## <a name="define-a-logger-message"></a>Definición de un mensaje del registrador

Use [Define(LogLevel, EventId, String)](xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A) para crear un delegado <xref:System.Action> para registrar un mensaje. Las sobrecargas <xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> permiten pasar hasta seis parámetros de tipo a una cadena de formato con nombre (plantilla).

La cadena proporcionada al método <xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A> es una plantilla y no una cadena interpolada. Los marcadores de posición se rellenan en el orden en que se especifican los tipos. Los nombres de los marcadores de posición en la plantilla deben ser descriptivos y coherentes entre las plantillas. Sirven como nombres de propiedad en los datos estructurados del registro. Se recomienda el uso de la [grafía Pascal](../../standard/design-guidelines/capitalization-conventions.md) para los nombres de los marcadores de posición. Por ejemplo: `{Item}`, `{DateTime}`.

Cada mensaje de registro es un delegado <xref:System.Action> que se mantiene en un campo estático creado por [LoggerMessage.Define](xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A). Por ejemplo, la aplicación de ejemplo crea un campo para describir un mensaje de registro para procesar los elementos de trabajo:

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="FailedProcessingField":::

Especifique lo siguiente para el delegado <xref:System.Action>:

- El nivel de registro.
- Un identificador de evento único (<xref:Microsoft.Extensions.Logging.EventId>) con el nombre del método de extensión estático.
- La plantilla de mensaje (cadena de formato con nombre).

A medida que los elementos de trabajo se quitan de la cola para el procesamiento, la aplicación de servicio de trabajo establece lo siguiente:

- El nivel de registro en <xref:Microsoft.Extensions.Logging.LogLevel.Critical?displayProperty=nameWithType>.
- El identificador de evento en `13` con el nombre del método `FailedToProcessWorkItem`.
- La plantilla de mensaje (cadena de formato con nombre) en una cadena.

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="FailedProcessingAssignment":::

Los almacenes de registro estructurado pueden usar el nombre de evento cuando se suministra con el identificador de evento para enriquecer el registro. Por ejemplo, [Serilog](https://github.com/serilog/serilog-extensions-logging) usa el nombre de evento.

El delegado <xref:System.Action> se invoca mediante un método de extensión fuertemente tipado. El método `PriorityItemProcessed` registra un mensaje cada vez que se procesa un elemento de trabajo. En cambio, se llama a `FailedToProcessWorkItem` cuando se produce una excepción:

:::code language="csharp" source="snippets/configuration/worker-service-options/Worker.cs" range="18-39" highlight="15-18":::

Inspeccione la salida de la consola de la aplicación:

```console
crit: WorkerServiceOptions.Example.Worker[13]
      Epic failure processing item!
      System.Exception: Failed to verify communications.
         at WorkerServiceOptions.Example.Worker.ExecuteAsync(CancellationToken stoppingToken) in
         ..\Worker.cs:line 27
```

Para pasar parámetros a un mensaje de registro, defina hasta seis tipos al crear el campo estático. La aplicación de ejemplo registra los detalles del elemento de trabajo al procesar los elementos definiendo un tipo `WorkItem` para el campo <xref:System.Action>:

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingItemField":::

La plantilla de mensaje de registro del delegado recibe sus valores de marcador de posición a partir de los tipos proporcionados. La aplicación de ejemplo define un delegado para agregar un elemento de trabajo cuando el parámetro del elemento es `WorkItem`:

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingItemAssignment":::

El método de extensión estático para registrar que se está procesando un elemento de trabajo, `PriorityItemProcessed`, recibe el valor de argumento del elemento de trabajo y lo pasa al delegado <xref:System.Action>:

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingItemMethod":::

En el método `ExecuteAsync` del servicio de trabajo, se llama a `PriorityItemProcessed` para registrar el mensaje:

:::code language="csharp" source="snippets/configuration/worker-service-options/Worker.cs" range="18-39" highlight="12":::

Inspeccione la salida de la consola de la aplicación:

```console
info: WorkerServiceOptions.Example.Worker[1]
      Processing priority item: Priority-Extreme (50db062a-9732-4418-936d-110549ad79e4): 'Verify communications'
```

## <a name="define-logger-message-scope"></a>Definición del ámbito del mensaje del registrador

El método [DefineScope(string)](xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A) crea un delegado <xref:System.Func%601> para definir un [ámbito de registro](logging.md#log-scopes). Las sobrecargas <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> permiten pasar hasta tres parámetros de tipo a una cadena de formato con nombre (plantilla).

Al igual que sucede con el método <xref:Microsoft.Extensions.Logging.LoggerMessage.Define%2A>, la cadena proporcionada al método <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> es una plantilla y no una cadena interpolada. Los marcadores de posición se rellenan en el orden en que se especifican los tipos. Los nombres de los marcadores de posición en la plantilla deben ser descriptivos y coherentes entre las plantillas. Sirven como nombres de propiedad en los datos estructurados del registro. Se recomienda el uso de la [grafía Pascal](../../standard/design-guidelines/capitalization-conventions.md) para los nombres de los marcadores de posición. Por ejemplo: `{Item}`, `{DateTime}`.

Defina un [ámbito de registro](logging.md#log-scopes) para aplicarlo a una serie de mensajes de registro mediante el método <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A>. Habilite `IncludeScopes` en la sección del registrador de la consola de *appsettings.json*:

:::code language="json" source="snippets/configuration/worker-service-options/appsettings.json" highlight="3-5":::

Para crear un ámbito de registro, agregue un campo para que contenga un delegado <xref:System.Func%601> para el ámbito. La aplicación de ejemplo crea un campo denominado `_processingWorkScope` (*Internal/LoggerExtensions.cs*):

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkField":::

Use <xref:Microsoft.Extensions.Logging.LoggerMessage.DefineScope%2A> para crear el delegado. Pueden especificarse hasta tres tipos para usarlos como argumentos de plantilla cuando se invoca el delegado. La aplicación de ejemplo usa una plantilla de mensaje que incluye la fecha y hora en que se inició el procesamiento:

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkAssignment":::

Proporcione un método de extensión estático para el mensaje de registro. Incluya todos los parámetros de tipo para propiedades con nombre que aparezcan en la plantilla de mensaje. La aplicación de ejemplo adopta `DateTime` para una marca de tiempo personalizada para el registro y devuelve `_processingWorkScope`:

:::code language="csharp" source="snippets/configuration/worker-service-options/Extensions/LoggerExtensions.cs" id="ProcessingWorkMethod":::

El ámbito encapsula las llamadas a la extensión de registro en un bloque [using](../../csharp/language-reference/keywords/using-statement.md):

:::code language="csharp" source="snippets/configuration/worker-service-options/Worker.cs" range="18-39" highlight="4":::

Inspeccione los mensajes de registro en la salida de la consola de la aplicación. El resultado siguiente muestra el orden de prioridad de los mensajes de registro con el mensaje de ámbito de registro incluido:

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

## <a name="see-also"></a>Vea también

- [Registro en .NET](logging.md)
