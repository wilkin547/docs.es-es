---
title: Proveedores de eventos conocidos en .NET
description: Revise los proveedores y los eventos publicados por las bibliotecas y el entorno de ejecución de .NET.
ms.topic: reference
ms.date: 12/21/2020
ms.openlocfilehash: 37aa9551397bb3e3e8858a1289ddc3921327b722
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102105172"
---
# <a name="well-known-event-providers-in-net"></a>Proveedores de eventos conocidos en .NET

Las bibliotecas y el entorno de ejecución de .NET escriben eventos de diagnóstico a través de varios proveedores de eventos. En función de sus necesidades de diagnóstico, puede elegir los proveedores adecuados que quiere habilitar. En este artículo se describen algunos de los proveedores de eventos que se usan con más frecuencia en las bibliotecas y en el entorno de ejecución de .NET.

## <a name="coreclr"></a>CoreCLR

### <a name="microsoft-windows-dotnetruntime-provider"></a>Proveedor "Microsoft-Windows-DotNETRuntime"

Este proveedor emite varios eventos desde el entorno de ejecución de .NET, incluidos eventos de recolección de elementos no utilizados (GC), eventos de cargador, eventos Just-In-Time (JIT), eventos de excepción y otros. Obtenga más información sobre cada evento de este proveedor en la [lista de eventos del proveedor del entorno de ejecución](../../fundamentals/diagnostics/runtime-events.md).

### <a name="microsoft-dotnetcore-sampleprofiler-provider"></a>Proveedor "Microsoft-DotNETCore-SampleProfiler"

Este proveedor proporciona eventos del entorno de ejecución de .NET y se usa para el muestreo de la CPU para pilas de llamadas administradas. Cuando está habilitado, captura una instantánea de la pila de llamadas administrada de cada subproceso cada 10 milisegundos. Para habilitar esta captura, debe especificar un <xref:System.Diagnostics.Tracing.EventLevel> (nivel de evento) `Informational` o superior.

## <a name="framework-libraries"></a>Bibliotecas del marco

### <a name="microsoft-extensions-dependencyinjection-provider"></a>Proveedor "Microsoft-Extensions-DependencyInjection"

Este proveedor registra información de DependencyInjection. En la tabla siguiente se muestran los eventos que registra el proveedor `Microsoft-Extensions-DependencyInjection`:

|Nombre del evento|Nivel|Descripción|
|----------|-----|-----------|
|`CallSiteBuilt`|Detallado (5)|Se ha creado un sitio de llamada.|
|`ServiceResolved`|Detallado (5)|Se ha resuelto un servicio.|
|`ExpressionTreeGenerated`|Detallado (5)|Se ha generado un árbol de expresión.|
|`DynamicMethodBuilt`|Detallado (5)|Se ha compilado un método dinámico (<xref:System.Reflection.Emit.DynamicMethod>).|

### <a name="systembuffersarraypooleventsource-provider"></a>Proveedor "System.Buffers.ArrayPoolEventSource"

Este proveedor registra información de ArrayPool. En la siguiente tabla se muestran los eventos que registra `ArrayPoolEventSource`:

|Nombre del evento|Nivel|Descripción|
|----------|-----|-----------|
|`BufferRented`|Detallado (5)|Un búfer se ha alquilado correctamente.|
|`BufferAllocated`|Informativo (4)|El grupo ha asignado un búfer.|
|`BufferReturned`|Detallado (5)|Se ha devuelto un búfer al grupo.|
|`BufferTrimmed`|Informativo (4)|Se ha intentado liberar un búfer por inactividad o por falta de memoria.|
|`BufferTrimPoll`|Informativo (4)|Se está realizando una comprobación para recortar los búferes.|

### <a name="systemnethttp-provider"></a>Proveedor "System.Net.Http"

Este proveedor registra información de la pila HTTP. En la siguiente tabla se muestran los eventos que registra el proveedor `System.Net.Http`:

|Nombre del evento|Nivel|Descripción|
|----------|-----|-----------|
|RequestStart|Informativo (4)|Se ha iniciado una solicitud HTTP.|
|RequestStop|Informativo (4)|Ha finalizado una solicitud HTTP.|
|RequestFailed|Error (2)|Se ha producido un error en una solicitud HTTP.|
|ConnectionEstablished|Informativo (4)|Se ha establecido una conexión HTTP.|
|ConnectionClosed|Informativo (4)|Se ha cerrado una conexión HTTP.|
|RequestLeftQueue|Informativo (4)|Una solicitud HTTP ha abandonado la cola de solicitudes.|
|RequestHeadersStart|Informativo (4)|Se ha iniciado una solicitud HTTP para el encabezado.|
|RequestHeaderStop|Informativo (4)|Ha finalizado una solicitud HTTP para el encabezado.|
|RequestContentStart|Informativo (4)|Se ha iniciado una solicitud HTTP para el contenido.|
|RequestContentStop|Informativo (4)|Ha finalizado una solicitud HTTP para el contenido.|
|ResponseHeadersStart|Informativo (4)|Se ha iniciado una respuesta HTTP para el encabezado.|
|ResponseHeaderStop|Informativo (4)|Ha finalizado una respuesta HTTP para el encabezado.|
|ResponseContentStart|Informativo (4)|Se ha iniciado una respuesta HTTP para el contenido.|
|ResponseContentStop|Informativo (4)|Ha finalizado una respuesta HTTP para el contenido.|

### <a name="systemnetnameresolution-provider"></a>Proveedor "System.Net.NameResolution"

Este proveedor registra información relacionada con la resolución de nombres de dominio. En la siguiente tabla se muestran los eventos que registra `System.Net.NameResolution`:

|Nombre del evento|Nivel|Descripción|
|----------|-----|-----------|
|`ResolutionStart`|Informativo (4)|Se ha iniciado una resolución de nombres de dominio.|
|`ResolutionStop`|Informativo (4)|Ha finalizado una resolución de nombres de dominio.|
|`ResolutionFailed`|Informativo (4)|No se ha podido resolver el nombre de dominio.|

### <a name="systemnetsockets-provider"></a>Proveedor "System.Net.Sockets"

Este proveedor registra información de <xref:System.Net.Sockets.Socket>. En la siguiente tabla se muestran los eventos que registra el proveedor `System.Net.Sockets`:

|Nombre del evento|Nivel|Descripción|
|----------|-----|-----------|
|`ConnectStart`|Informativo (4)|Se ha iniciado un intento de iniciar una conexión de socket.|
|`ConnectStop`|Informativo (4)|Ha finalizado un intento de iniciar una conexión de socket.|
|`ConnectFailed`|Informativo (4)|Se ha producido un error al tratar de iniciar una conexión de socket.|
|`AcceptStart`|Informativo (4)|Se ha iniciado un intento de aceptar una conexión de socket.|
|`AcceptStop`|Informativo (4)|Ha finalizado un intento de aceptar una conexión de socket.|
|`AcceptFailed`|Informativo (4)|Se ha producido un error al tratar de aceptar una conexión de socket.|

### <a name="systemthreadingtaskstpleventsource-provider"></a>Proveedor "System.Threading.Tasks.TplEventSource"

Este proveedor registra información sobre la [biblioteca TPL](../../standard/parallel-programming/task-parallel-library-tpl.md), como los eventos del Programador de tareas. En la siguiente tabla se muestran los eventos que registra `TplEventSource`:

|Nombre del evento|Palabra clave|Nivel|Descripción|
|----------|-------|-----|-----------|
|`TaskScheduled`|`TaskTransfer`(`0x1`)<br /><br />`Tasks`(`0x2`)|Informativo (4)|Un objeto <xref:System.Threading.Tasks.Task> se ha puesto en cola en el Programador de tareas.|
|`TaskStarted`|`Tasks`(`0x2`)|Informativo (4)|Se ha iniciado la ejecución de un objeto <xref:System.Threading.Tasks.Task>.|
|`TaskCompleted`|`TaskStops`(`0x40`)|Informativo (4)|Un objeto <xref:System.Threading.Tasks.Task> ha terminado de ejecutarse.|
|`TaskWaitBegin`|`TaskTransfer`(`0x1`)<br /><br />`TaskWait`(`0x2`)|Informativo (4)|Se desencadena cuando se inicia una espera implícita o explícita para la finalización de un objeto <xref:System.Threading.Tasks.Task>.|
|`TaskWaitEnd`|`Tasks`(`0x2`)|Detallado (5)|Se desencadena cuando se devuelve la espera para la finalización de un objeto <xref:System.Threading.Tasks.Task>.|
|`TaskWaitContinuationStarted`|`Tasks`(`0x2`)|Detallado (5)|Se desencadena cuando se inicia el trabajo (método) asociado a un objeto `TaskWaitEnd`.|
|`TaskWaitContinuationCompleted`|`TaskStops`(`0x40`)|Detallado (5)|Se desencadena cuando se completa el trabajo (método) asociado a un objeto `TaskWaitEnd`.|
|`AwaitTaskContinuationScheduled`|`TaskTransfer`(`0x1`)<br /><br />`Tasks`(`0x2`)|Informativo (4)|Se desencadena cuando se programa una continuación asincrónica para un objeto <xref:System.Threading.Tasks.Task>.|

## <a name="aspnet-core"></a>ASP.NET Core

ASP.NET Core también proporciona varios eventos para ayudarle a diagnosticar problemas en la pila de ASP.NET Core.

Para obtener más información sobre los eventos en ASP.NET Core y cómo consumirlos, consulte el artículo [Registros en .NET Core y ASP.NET Core](/aspnet/core/fundamentals/logging/).

## <a name="entity-framework-core"></a>Entity Framework Core

EF Core también proporciona eventos para ayudarle a diagnosticar problemas en EF Core.

Para obtener más información sobre los eventos en EFCore y cómo consumirlos, consulte [Eventos de .NET en EF Core](/ef/core/logging-events-diagnostics/events).
