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
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="6ea83-103">¿Qué herramientas de diagnóstico están disponibles en .NET Core?</span><span class="sxs-lookup"><span data-stu-id="6ea83-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="6ea83-104">El comportamiento del software no siempre es el esperado, pero .NET Core tiene herramientas y API que lo ayudarán a diagnosticar estos problemas de manera rápida y eficaz.</span><span class="sxs-lookup"><span data-stu-id="6ea83-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="6ea83-105">Este artículo lo ayuda a encontrar las distintas herramientas que necesita.</span><span class="sxs-lookup"><span data-stu-id="6ea83-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggers"></a><span data-ttu-id="6ea83-106">Depuradores administrados</span><span class="sxs-lookup"><span data-stu-id="6ea83-106">Managed debuggers</span></span>

<span data-ttu-id="6ea83-107">Los [depuradores administrados](managed-debuggers.md) le permiten interactuar con el programa.</span><span class="sxs-lookup"><span data-stu-id="6ea83-107">[Managed debuggers](managed-debuggers.md) allow you to interact with your program.</span></span> <span data-ttu-id="6ea83-108">Pausar, ejecutar de manera incremental, examinar y reanudar le proporcionan información sobre el comportamiento del código.</span><span class="sxs-lookup"><span data-stu-id="6ea83-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="6ea83-109">Un depurador es la primera opción para diagnosticar problemas funcionales que se pueden reproducir de manera fácil.</span><span class="sxs-lookup"><span data-stu-id="6ea83-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracing"></a><span data-ttu-id="6ea83-110">Registro y seguimiento</span><span class="sxs-lookup"><span data-stu-id="6ea83-110">Logging and tracing</span></span>

<span data-ttu-id="6ea83-111">El [registro y seguimiento](logging-tracing.md) son técnicas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="6ea83-111">[Logging and tracing](logging-tracing.md) are related techniques.</span></span> <span data-ttu-id="6ea83-112">Hacen referencia a la instrumentación del código para crear archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="6ea83-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="6ea83-113">Los archivos registran los detalles de lo que hace un programa.</span><span class="sxs-lookup"><span data-stu-id="6ea83-113">The files record the details of what a program does.</span></span> <span data-ttu-id="6ea83-114">Estos detalles se pueden usar para diagnosticar los problemas más complejos.</span><span class="sxs-lookup"><span data-stu-id="6ea83-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="6ea83-115">Cuando se combinan con marcas de tiempo, estas técnicas también son valiosas para investigaciones de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="6ea83-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testing"></a><span data-ttu-id="6ea83-116">Pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="6ea83-116">Unit testing</span></span>

<span data-ttu-id="6ea83-117">Las [pruebas unitarias](../testing/index.md) son un componente clave de la integración continua y la implementación de software de alta calidad.</span><span class="sxs-lookup"><span data-stu-id="6ea83-117">[Unit testing](../testing/index.md) is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="6ea83-118">Las pruebas unitarias están diseñadas para brindarle una advertencia temprana cuando se daña algo.</span><span class="sxs-lookup"><span data-stu-id="6ea83-118">Unit tests are designed to give you an early warning when you break something.</span></span>

## <a name="net-core-dotnet-diagnostic-global-tools"></a><span data-ttu-id="6ea83-119">Herramientas globales de diagnóstico de dotnet de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6ea83-119">.NET Core dotnet diagnostic Global Tools</span></span>

### <a name="dotnet-counters"></a><span data-ttu-id="6ea83-120">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="6ea83-120">dotnet-counters</span></span>

<span data-ttu-id="6ea83-121">[dotnet-counters](dotnet-counters.md) es una herramienta diseñada para la investigación del rendimiento y la supervisión del estado de primer nivel.</span><span class="sxs-lookup"><span data-stu-id="6ea83-121">[dotnet-counters](dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span> <span data-ttu-id="6ea83-122">Permite observar los valores del contador de rendimiento que se publican a través de la API <xref:System.Diagnostics.Tracing.EventCounter>.</span><span class="sxs-lookup"><span data-stu-id="6ea83-122">It observes performance counter values published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="6ea83-123">Por ejemplo, puede supervisar rápidamente elementos como el uso de la CPU o la tasa de excepciones que se generan en su aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6ea83-123">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application.</span></span>

### <a name="dotnet-dump"></a><span data-ttu-id="6ea83-124">dotnet-dump</span><span class="sxs-lookup"><span data-stu-id="6ea83-124">dotnet-dump</span></span>

<span data-ttu-id="6ea83-125">La herramienta [dotnet-dump](dotnet-dump.md) permite recopilar y analizar los volcados de Windows y Linux sin necesidad de un depurador nativo.</span><span class="sxs-lookup"><span data-stu-id="6ea83-125">The [dotnet-dump](dotnet-dump.md) tool is a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

### <a name="dotnet-trace"></a><span data-ttu-id="6ea83-126">dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="6ea83-126">dotnet-trace</span></span>

<span data-ttu-id="6ea83-127">.NET Core incluye lo que se denomina `EventPipe`, a través del cual se exponen los datos de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="6ea83-127">.NET Core includes what is called the `EventPipe` through which diagnostics data is exposed.</span></span> <span data-ttu-id="6ea83-128">La herramienta [dotnet-trace](dotnet-trace.md) permite consumir datos interesantes sobre la generación de perfiles a partir de su aplicación, lo cual puede resultar útil para analizar la causa principal de que una aplicación se ejecute con lentitud.</span><span class="sxs-lookup"><span data-stu-id="6ea83-128">The [dotnet-trace](dotnet-trace.md) tool allows you to consume interesting profiling data from your app that can help in scenarios where you need to root cause apps running slow.</span></span>

## <a name="net-core-diagnostics-tutorials"></a><span data-ttu-id="6ea83-129">Tutoriales de diagnóstico de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6ea83-129">.NET Core diagnostics tutorials</span></span>

### <a name="debug-a-memory-leak"></a><span data-ttu-id="6ea83-130">Depuración de una fuga de memoria</span><span class="sxs-lookup"><span data-stu-id="6ea83-130">Debug a memory leak</span></span>

<span data-ttu-id="6ea83-131">[Tutorial: Depuración de una fuga de memoria](debug-memory-leak.md) le guía a través de la búsqueda de una fuga de memoria.</span><span class="sxs-lookup"><span data-stu-id="6ea83-131">[Tutorial: Debug a memory leak](debug-memory-leak.md) walks through finding a memory leak.</span></span> <span data-ttu-id="6ea83-132">La herramienta [dotnet-counters](dotnet-counters.md) se usa para confirmar la fuga, y la herramienta [dotnet-dump](dotnet-dump.md), para diagnosticarla.</span><span class="sxs-lookup"><span data-stu-id="6ea83-132">The [dotnet-counters](dotnet-counters.md) tool is used to confirm the leak and the [dotnet-dump](dotnet-dump.md) tool is used to diagnose the leak.</span></span>
