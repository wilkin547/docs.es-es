---
title: Información general sobre EventPipe
description: Obtenga información sobre EventPipe y cómo usarlo para hacer un seguimiento de las aplicaciones .NET con el fin de diagnosticar problemas de rendimiento.
ms.date: 11/09/2020
ms.topic: overview
ms.openlocfilehash: 00378c4f409b307afa9183e40de6078cdafd3ae7
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820623"
---
# <a name="eventpipe"></a>EventPipe

EventPipe es un componente en tiempo de ejecución similar a ETW o LTTng que se puede usar para recopilar datos de seguimiento. El objetivo de EventPipe es permitir a los desarrolladores de .NET realizar un seguimiento sencillo de sus aplicaciones .NET sin tener que depender de componentes nativos del sistema operativo específicos de la plataforma como ETW o LTTng.

EventPipe es el mecanismo subyacente de muchas de las herramientas de diagnóstico y se puede usar para consumir eventos emitidos por el entorno de ejecución, así como eventos personalizados escritos con [EventSource](xref:System.Diagnostics.Tracing.EventSource).

Este artículo es una introducción general a EventPipe que describe cuándo y cómo usar EventPipe y cómo configurarlo para que se adapte mejor a sus necesidades.

## <a name="eventpipe-basics"></a>Aspectos básicos de EventPipe

EventPipe agrega eventos emitidos por componentes en tiempo de ejecución (por ejemplo, el compilador Just-in-Time o el recolector de elementos no utilizados) y eventos escritos desde instancias de [EventSource](xref:System.Diagnostics.Tracing.EventSource) en las bibliotecas y el código de usuario.

Luego los eventos se serializan y pueden escribirse directamente en un archivo o consumirse por medio de un puerto de diagnóstico desde fuera de proceso. En Windows, los puertos de diagnóstico se implementan como elementos `NamedPipe`. En plataformas que no son de Windows, como Linux o macOS, se implementan mediante sockets de dominio Unix. Para obtener más información sobre el puerto de diagnóstico y cómo interactuar con él mediante su protocolo de comunicación entre procesos personalizado, vea la [documentación del protocolo IPC de diagnóstico](https://github.com/dotnet/diagnostics/blob/master/documentation/design-docs/ipc-protocol.md).

Luego EventPipe escribe los eventos serializados en el formato de archivo `.nettrace`, ya sea como una secuencia mediante puertos de diagnóstico o directamente en un archivo. Para obtener más información sobre el formato de serialización de EventPipe, vea la [documentación de formato de EventPipe](https://github.com/microsoft/perfview/blob/master/src/TraceEvent/EventPipe/EventPipeFormat.md).

## <a name="eventpipe-vs-etwlttng"></a>EventPipe frente a ETW/LTTng

EventPipe forma parte del entorno de ejecución .NET (CoreCLR) y está diseñado para funcionar de la misma manera en todas las plataformas compatibles con .NET Core. Esto permite que herramientas de seguimiento basadas en EventPipe, como `dotnet-counters`, `dotnet-gcdump` y `dotnet-trace`, funcionen sin problemas entre plataformas.

Pero, dado que EventPipe es un componente integrado en tiempo de ejecución, su ámbito se limita al código administrado y al propio entorno de ejecución. EventPipe no se puede usar para realizar el seguimiento de algunos eventos de nivel inferior, como resolver la pila de código nativo u obtener distintos eventos de kernel. Si usa interoperabilidad de C/C++ en la aplicación, quiere realizar un seguimiento del propio entorno de ejecución (que está escrito en C++) o quiere un diagnóstico más profundo sobre el comportamiento de la aplicación que requiera eventos de kernel (es decir, eventos de cambio de contexto de subprocesos nativos), debe usar ETW o [perf/LTTng](./trace-perfcollect-lttng.md).

Otra diferencia importante entre EventPipe y ETW/LTTng es el requisito de privilegios de administrador o raíz. Para realizar el seguimiento de una aplicación mediante ETW o LTTng, debe ser administrador o raíz. Con EventPipe puede realizar un seguimiento de las aplicaciones siempre que el seguimiento (por ejemplo, `dotnet-trace`) se ejecute como el mismo usuario que el que ha iniciado la aplicación.

En la tabla siguiente se presenta un resumen de las diferencias entre EventPipe y ETW/LTTng.

|Característica|EventPipe|ETW|LTTng|
|-------|---------|---|-----------|
|Multiplataforma|Sí|No (solo en Windows)|No (solo en distribuciones Linux compatibles)|
|Requiere privilegios de administrador o raíz|No|Sí|Sí|
|Puede obtener eventos de SO o kernel|No|Sí|Sí|
|Puede resolver pilas de llamadas nativas|No|Sí|Sí|

## <a name="use-eventpipe-to-trace-your-net-application"></a>Uso de EventPipe para el seguimiento de la aplicación .NET

Puede usar EventPipe para realizar un seguimiento de la aplicación .NET de muchas maneras:

* Use alguna de las [herramientas de diagnóstico](#tools-that-use-eventpipe) que se basan en EventPipe.

* Use la biblioteca [Microsoft.Diagnostics.NETCore.Client](https://github.com/dotnet/diagnostics/blob/master/documentation/diagnostics-client-library-instructions.md) para escribir su propia herramienta a fin de configurar e iniciar las sesiones de EventPipe por sí mismo.

* Use [variables de entorno](#trace-using-environment-variables) para iniciar EventPipe.

Después de haber creado un archivo `nettrace` que contenga los eventos de EventPipe, puede verlo en [`PerfView`](https://github.com/Microsoft/perfview#perfview-overview) o Visual Studio. En las plataformas que no son de Windows, puede convertir el archivo `nettrace` a un formato de seguimiento de `speedscope` o `Chromium` mediante el comando [`dotnet-trace convert`](./dotnet-trace.md#dotnet-trace-convert) y verlo con [`speedscope`](https://www.speedscope.app/) o Chrome DevTools.

También puede analizar los seguimientos de EventPipe mediante programación con [TraceEvent](https://github.com/Microsoft/perfview/blob/master/documentation/TraceEvent/TraceEventLibrary.md).

### <a name="tools-that-use-eventpipe"></a>Herramientas que usan EventPipe

Esta es la forma más sencilla de usar EventPipe para realizar un seguimiento de la aplicación. Para obtener más información sobre cómo usar cada una de estas herramientas, vea la documentación de cada una de ellas.

* [dotnet-counters](./dotnet-counters.md) permite supervisar y recopilar diversas métricas emitidas por el entorno de ejecución .NET y las bibliotecas principales, así como métricas personalizadas que se pueden escribir.

* [dotnet-gcdump](./dotnet-gcdump.md) permite recopilar volcados de memoria del montón de GC de procesos en vivo para analizar el montón administrado de una aplicación.

* [dotnet-trace](./dotnet-trace.md) permite recopilar seguimientos de aplicaciones para analizar el rendimiento.

## <a name="trace-using-environment-variables"></a>Seguimiento mediante variables de entorno

El mecanismo preferido para usar EventPipe es `dotnet-trace` o la biblioteca `Microsoft.Diagnostics.NETCore.Client`,

pero puede usar las siguientes variables de entorno para configurar una sesión de EventPipe en una aplicación y hacer que escriba el seguimiento directamente en un archivo. Para detener el seguimiento, salga de la aplicación.

* `COMPlus_EnableEventPipe`: establezca en `1` para iniciar una sesión de EventPipe que escriba directamente en un archivo. El valor predeterminado es `0`.

* `COMPlus_EventPipeOutputPath`: ruta de acceso al archivo de seguimiento de EventPipe de salida cuando está configurado para ejecutarse mediante `COMPlus_EnableEventPipe`. El valor predeterminado es `trace.nettrace`, que se crea en el mismo directorio desde el que se ejecuta la aplicación.

* `COMPlus_CircularBufferMB`: tamaño del búfer interno usado por EventPipe cuando se configura para ejecutarse mediante `COMPlus_EnableEventPipe`.

* `COMPlus_EventPipeConfig`: establece la configuración de sesión de EventPipe al iniciar una sesión de EventPipe con `COMPlus_EnableEventPipe`.

  La sintaxis es la siguiente:

  `<provider>:<keyword>:<level>`

  También puede especificar varios proveedores si los concatena con una coma:

  `<provider1>:<keyword1>:<level1>,<provider2>:<keyword2>:<level2>`

  Si no se establece esta variable de entorno sino que EventPipe se habilita por medio de `COMPlus_EnableEventPipe`, comienza el seguimiento mediante la habilitación de los siguientes proveedores con las siguientes palabras clave y niveles:

  - `Microsoft-Windows-DotNETRuntime:4c14fccbd:5`
  - `Microsoft-Windows-DotNETRuntimePrivate:4002000b:5`
  - `Microsoft-DotNETCore-SampleProfiler:0:5`
