---
title: 'Información general de las herramientas de diagnóstico: .NET Core'
description: Información general de las herramientas y técnicas disponibles para diagnosticar las aplicaciones de .NET Core.
ms.date: 07/16/2020
ms.topic: overview
ms.openlocfilehash: 9836ea11e7f17d6ed6e04bcba8bc0ed851bb368f
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102105289"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a>¿Qué herramientas de diagnóstico están disponibles en .NET Core?

El comportamiento del software no siempre es el esperado, pero .NET Core tiene herramientas y API que lo ayudarán a diagnosticar estos problemas de manera rápida y eficaz.

Este artículo lo ayuda a encontrar las distintas herramientas que necesita.

## <a name="managed-debuggers"></a>Depuradores administrados

Los [depuradores administrados](managed-debuggers.md) le permiten interactuar con el programa. Pausar, ejecutar de manera incremental, examinar y reanudar le proporcionan información sobre el comportamiento del código. Un depurador es la primera opción para diagnosticar problemas funcionales que se pueden reproducir de manera fácil.

## <a name="logging-and-tracing"></a>Registro y seguimiento

El [registro y seguimiento](logging-tracing.md) son técnicas relacionadas. Hacen referencia a la instrumentación del código para crear archivos de registro. Los archivos registran los detalles de lo que hace un programa. Estos detalles se pueden usar para diagnosticar los problemas más complejos. Cuando se combinan con marcas de tiempo, estas técnicas también son valiosas para investigaciones de rendimiento.

## <a name="metrics"></a>Métricas

Los elementos [EventCounter](event-counters.md) permiten escribir métricas para identificar y supervisar los problemas de rendimiento. Las métricas incurren en una carga de rendimiento menor en comparación con el seguimiento, lo que las hace más convenientes para una supervisión de rendimiento permanente. El entorno de ejecución y las bibliotecas de .NET publican varios [elementos EventCounter conocidos](available-counters.md) que también puede supervisar.

## <a name="unit-testing"></a>Pruebas unitarias

Las [pruebas unitarias](../testing/index.md) son un componente clave de la integración continua y la implementación de software de alta calidad. Las pruebas unitarias están diseñadas para brindarle una advertencia temprana cuando se daña algo.

## <a name="dumps"></a>Volcados

Un [volcado](./dumps.md) es un archivo que contiene una instantánea del proceso en el momento de la creación. Pueden ser útiles para examinar el estado de la aplicación con fines de depuración.

## <a name="symbols"></a>Símbolos

Los [símbolos](./symbols.md) son una asignación entre el código de origen y el binario que produce el compilador. Los depuradores de .NET suelen usarlos para resolver números de línea de origen, nombres de variables locales y otros tipos de información de diagnóstico.

## <a name="collect-diagnostics-in-containers"></a>Recopilación de diagnósticos en contenedores

Las herramientas de diagnóstico que se usan en los entornos de Linux que no están en contenedores también se pueden utilizar para [recopilar diagnósticos en contenedores](diagnostics-in-containers.md). Solo es necesario realizar algunos cambios en la utilización para asegurarse de que las herramientas funcionan en un contenedor de Docker.

## <a name="net-core-diagnostic-global-tools"></a>Herramientas globales de diagnóstico de .NET Core

### <a name="dotnet-counters"></a>dotnet-counters

[dotnet-counters](dotnet-counters.md) es una herramienta diseñada para la investigación del rendimiento y la supervisión del estado de primer nivel. Permite observar los valores del contador de rendimiento que se publican a través de la API <xref:System.Diagnostics.Tracing.EventCounter>. Por ejemplo, puede supervisar rápidamente elementos como el uso de la CPU o la tasa de excepciones que se generan en su aplicación .NET Core.

### <a name="dotnet-dump"></a>dotnet-dump

La herramienta [dotnet-dump](dotnet-dump.md) permite recopilar y analizar los volcados de Windows y Linux sin necesidad de un depurador nativo.

### <a name="dotnet-gcdump"></a>dotnet-gcdump

La herramienta [dotnet-gcdump](dotnet-gcdump.md) permite recopilar volcados de memoria de GC (recolector de elementos no utilizados) de procesos de .NET dinámicos.

### <a name="dotnet-trace"></a>dotnet-trace

.NET Core incluye lo que se denomina `EventPipe`, a través del cual se exponen los datos de diagnóstico. La herramienta [dotnet-trace](dotnet-trace.md) permite consumir datos interesantes sobre la generación de perfiles a partir de su aplicación, lo cual puede resultar útil para analizar la causa principal de que una aplicación se ejecute con lentitud.

### <a name="dotnet-symbol"></a>dotnet-symbol

[dotnet-symbol](dotnet-symbol.md) descarga archivos (símbolos, DAC/DBI, archivos de host, etc.) necesarios para abrir un volcado de núcleo o minivolcado. Use esta herramienta si necesita símbolos y módulos para depurar un archivo de volcado capturado en otro equipo.

### <a name="dotnet-sos"></a>dotnet-sos

[dotnet-sos](dotnet-sos.md) instala la [extensión de depuración de SOS](sos-debugging-extension.md) en Linux y macOS (también en Windows si usa [Windbg/cdb](/windows-hardware/drivers/debugger/debugger-download-tools)).

### <a name="perfcollect"></a>PerfCollect

[PerfCollect](trace-perfcollect-lttng.md) es un script de bash que se puede usar para recopilar seguimientos con `perf` y `LTTng` para un análisis de rendimiento más detallado de las aplicaciones .NET que se ejecutan en distribuciones de Linux.

## <a name="net-core-diagnostics-tutorials"></a>Tutoriales de diagnóstico de .NET Core

### <a name="debug-a-memory-leak"></a>Depuración de una fuga de memoria

[Tutorial: Depuración de una fuga de memoria](debug-memory-leak.md) le guía a través de la búsqueda de una fuga de memoria. La herramienta [dotnet-counters](dotnet-counters.md) se usa para confirmar la fuga, y la herramienta [dotnet-dump](dotnet-dump.md), para diagnosticarla.

### <a name="debug-high-cpu-usage"></a>Depuración del uso elevado de CPU

[Tutorial: Depuración del uso elevado de CPU](debug-highcpu.md) le guía a través de la investigación del uso elevado de CPU. Utiliza la herramienta [dotnet-counters](dotnet-counters.md) para confirmar ese uso elevado. A continuación, se explica el uso del [seguimiento de la utilidad de análisis del rendimiento (`dotnet-trace`)](dotnet-trace.md) o de Linux `perf` para recopilar y ver el perfil de uso de la CPU.

### <a name="debug-deadlock"></a>Depuración de interbloqueo

[Tutorial: Depuración de interbloqueo](debug-deadlock.md) muestra cómo usar la herramienta [dotnet-dump](dotnet-dump.md) para investigar los subprocesos y bloqueos.

### <a name="debug-a-stackoverflow"></a>Depuración de StackOverflow

[Tutorial: Depuración de StackOverflow](debug-stackoverflow.md) muestra cómo depurar un elemento <xref:System.StackOverflowException> en Linux.

### <a name="debug-linux-dumps"></a>Depuración de volcados de Linux

[Depuración de volcados de Linux](debug-linux-dumps.md) explica cómo recopilar y analizar volcados en Linux.

### <a name="measure-performance-using-eventcounters"></a>Medición del rendimiento mediante EventCounters

[Tutorial: Medición del rendimiento mediante EventCounters en .NET](event-counter-perf.md) muestra cómo usar la API <xref:System.Diagnostics.Tracing.EventCounter> para medir el rendimiento de la aplicación .NET.
