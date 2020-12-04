---
title: Eventos en tiempo de ejecución
description: Revise los eventos de diagnóstico emitidos por el tiempo de ejecución de .NET (CoreCLR) que se pueden usar con ETW, LTTng o EventPipe.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- runtime events (CoreCLR)
- ETW, EventPipe runtime events (CoreCLR)
ms.openlocfilehash: 33fa7275ce40934ce043b4d0dba5749c37515755
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "96594705"
---
# <a name="net-runtime-events"></a><span data-ttu-id="45966-103">Eventos de tiempo de ejecución de .NET</span><span class="sxs-lookup"><span data-stu-id="45966-103">.NET runtime events</span></span>

<span data-ttu-id="45966-104">El entorno de tiempo de ejecución de .NET (CoreCLR) emite varios eventos que se pueden usar para diagnosticar problemas con la aplicación .NET que se pueden consumir a través de varios mecanismos como `ETW` , `LTTng` y `EventPipe` .</span><span class="sxs-lookup"><span data-stu-id="45966-104">The .NET runtime (CoreCLR) emits various events that can be used to diagnose issues with your .NET application that can be consumed via various mechanisms such as `ETW`, `LTTng`, and `EventPipe`.</span></span>

<span data-ttu-id="45966-105">Este documento sirve como referencia en los eventos desencadenados por el tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="45966-105">This document serves as a reference on the events that are fired by .NET Core runtime.</span></span>

<span data-ttu-id="45966-106">Para eventos en tiempo de ejecución en .NET Framework, vea [eventos ETW de CLR](../../framework/performance/clr-etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="45966-106">For runtime events in .NET Framework, see [CLR ETW Events](../../framework/performance/clr-etw-events.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="45966-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="45966-107">In this section</span></span>

<span data-ttu-id="45966-108">[Eventos de contención](runtime-contention-events.md)</span><span class="sxs-lookup"><span data-stu-id="45966-108">[Contention Events](runtime-contention-events.md)</span></span>\
<span data-ttu-id="45966-109">Estos eventos recopilan información acerca de las contenciones de bloqueo de monitor.</span><span class="sxs-lookup"><span data-stu-id="45966-109">These events collect information about monitor lock contentions.</span></span>

<span data-ttu-id="45966-110">[Eventos de recolección de elementos no utilizados](runtime-garbage-collection-events.md)</span><span class="sxs-lookup"><span data-stu-id="45966-110">[Garbage Collection Events](runtime-garbage-collection-events.md)</span></span>\
<span data-ttu-id="45966-111">Estos eventos recopilan información sobre la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="45966-111">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="45966-112">Ayudan en el diagnóstico y la depuración, incluida la determinación de cuántas veces se realizó la recolección de elementos no utilizados, cuánta memoria se liberó durante la recolección de elementos no utilizados, etc.</span><span class="sxs-lookup"><span data-stu-id="45966-112">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, etc.</span></span>

<span data-ttu-id="45966-113">[Eventos de excepción](runtime-exception-events.md)</span><span class="sxs-lookup"><span data-stu-id="45966-113">[Exception Events](runtime-exception-events.md)</span></span>\
<span data-ttu-id="45966-114">Estos eventos en tiempo de ejecución capturan información sobre las excepciones que se producen.</span><span class="sxs-lookup"><span data-stu-id="45966-114">These runtime events capture information about exceptions that are thrown.</span></span>

<span data-ttu-id="45966-115">[Eventos de interoperabilidad](runtime-interop-events.md)</span><span class="sxs-lookup"><span data-stu-id="45966-115">[Interop Events](runtime-interop-events.md)</span></span>\
<span data-ttu-id="45966-116">Estos eventos en tiempo de ejecución capturan información sobre la generación de código auxiliar del lenguaje intermedio común (CIL).</span><span class="sxs-lookup"><span data-stu-id="45966-116">These runtime events capture information about Common Intermediate Language (CIL) stub generation.</span></span>

<span data-ttu-id="45966-117">[Eventos de cargador y enlazador](runtime-loader-binder-events.md)</span><span class="sxs-lookup"><span data-stu-id="45966-117">[Loader and Binder Events](runtime-loader-binder-events.md)</span></span>\
<span data-ttu-id="45966-118">Estos eventos recopilan información relacionada con la carga y descarga de ensamblados y módulos.</span><span class="sxs-lookup"><span data-stu-id="45966-118">These events collect information relating to loading and unloading assemblies and modules.</span></span>

<span data-ttu-id="45966-119">[Eventos de método](runtime-method-events.md)</span><span class="sxs-lookup"><span data-stu-id="45966-119">[Method Events](runtime-method-events.md)</span></span>\
<span data-ttu-id="45966-120">Estos eventos recopilan información que es específica de los métodos.</span><span class="sxs-lookup"><span data-stu-id="45966-120">These events collect information that is specific to methods.</span></span> <span data-ttu-id="45966-121">La carga de estos eventos es necesaria para la resolución de símbolos.</span><span class="sxs-lookup"><span data-stu-id="45966-121">The payload of these events is required for symbol resolution.</span></span> <span data-ttu-id="45966-122">Además, estos eventos proporcionan información útil como el número de veces que se llama a un método.</span><span class="sxs-lookup"><span data-stu-id="45966-122">In addition, these events provide helpful information such as the number of times a method was called.</span></span>

<span data-ttu-id="45966-123">[Eventos de subproceso](runtime-thread-events.md)</span><span class="sxs-lookup"><span data-stu-id="45966-123">[Thread Events](runtime-thread-events.md)</span></span>\
<span data-ttu-id="45966-124">Estos eventos recopilan información sobre los subprocesos de E/S y de trabajo.</span><span class="sxs-lookup"><span data-stu-id="45966-124">These events collect information about worker and I/O threads.</span></span>

<span data-ttu-id="45966-125">[Eventos de tipo](runtime-type-events.md)</span><span class="sxs-lookup"><span data-stu-id="45966-125">[Type Events](runtime-type-events.md)</span></span>\
<span data-ttu-id="45966-126">Estos eventos recopilan información sobre el sistema de tipos.</span><span class="sxs-lookup"><span data-stu-id="45966-126">These events collect information about the type system.</span></span>
