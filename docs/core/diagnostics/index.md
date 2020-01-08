---
title: 'Información general de las herramientas de diagnóstico: .NET Core'
description: Información general de las herramientas y técnicas disponibles para diagnosticar las aplicaciones de .NET Core.
author: sdmaclea
ms.author: stmaclea
ms.date: 12/17/2019
ms.topic: overview
ms.openlocfilehash: 20374c53769bf19901b042e0909175718665b523
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75341480"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a>¿Qué herramientas de diagnóstico están disponibles en .NET Core?

El comportamiento del software no siempre es el esperado, pero .NET Core tiene herramientas y API que lo ayudarán a diagnosticar estos problemas de manera rápida y eficaz.

Este artículo lo ayuda a encontrar las distintas herramientas que necesita.

## <a name="managed-debuggers"></a>Depuradores administrados

Los [depuradores administrados](managed-debuggers.md) le permiten interactuar con el programa. Pausar, ejecutar de manera incremental, examinar y reanudar le proporcionan información sobre el comportamiento del código. Un depurador es la primera opción para diagnosticar problemas funcionales que se pueden reproducir de manera fácil.

## <a name="logging-and-tracing"></a>Registro y seguimiento

El [registro y seguimiento](logging-tracing.md) son técnicas relacionadas. Hacen referencia a la instrumentación del código para crear archivos de registro. Los archivos registran los detalles de lo que hace un programa. Estos detalles se pueden usar para diagnosticar los problemas más complejos. Cuando se combinan con marcas de tiempo, estas técnicas también son valiosas para investigaciones de rendimiento.

## <a name="unit-testing"></a>Pruebas unitarias

Las [pruebas unitarias](../testing/index.md) son un componente clave de la integración continua y la implementación de software de alta calidad. Las pruebas unitarias están diseñadas para brindarle una advertencia temprana cuando se daña algo.

## <a name="net-core-dotnet-diagnostic-global-tools"></a>Herramientas globales de diagnóstico de dotnet de .NET Core

### <a name="dotnet-counters"></a>dotnet-counters

[dotnet-counters](dotnet-counters.md) es una herramienta diseñada para la investigación del rendimiento y la supervisión del estado de primer nivel. Permite observar los valores del contador de rendimiento que se publican a través de la API <xref:System.Diagnostics.Tracing.EventCounter>. Por ejemplo, puede supervisar rápidamente elementos como el uso de la CPU o la tasa de excepciones que se generan en su aplicación .NET Core.

### <a name="dotnet-dump"></a>dotnet-dump

La herramienta [dotnet-dump](dotnet-dump.md) permite recopilar y analizar los volcados de Windows y Linux sin necesidad de un depurador nativo.

### <a name="dotnet-trace"></a>dotnet-trace

.NET Core incluye lo que se denomina `EventPipe`, a través del cual se exponen los datos de diagnóstico. La herramienta [dotnet-trace](dotnet-trace.md) permite consumir datos interesantes sobre la generación de perfiles a partir de su aplicación, lo cual puede resultar útil para analizar la causa principal de que una aplicación se ejecute con lentitud.

## <a name="net-core-diagnostics-tutorials"></a>Tutoriales de diagnóstico de .NET Core

### <a name="debug-a-memory-leak"></a>Depuración de una fuga de memoria

[Tutorial: Depuración de una fuga de memoria](debug-memory-leak.md) le guía a través de la búsqueda de una fuga de memoria. La herramienta [dotnet-counters](dotnet-counters.md) se usa para confirmar la fuga, y la herramienta [dotnet-dump](dotnet-dump.md), para diagnosticarla.
