---
title: 'Información general de las herramientas de diagnóstico: .NET Core'
description: Información general de las herramientas y técnicas disponibles para diagnosticar las aplicaciones de .NET Core.
author: sdmaclea
ms.author: stmaclea
ms.date: 08/05/2019
ms.topic: overview
ms.openlocfilehash: f107d15fa5584bb5a4834b5f11f1096bec7eb749
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974153"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="b729b-103">¿Qué herramientas de diagnóstico están disponibles en .NET Core?</span><span class="sxs-lookup"><span data-stu-id="b729b-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="b729b-104">El comportamiento del software no siempre es el esperado, pero .NET Core tiene herramientas y API que lo ayudarán a diagnosticar estos problemas de manera rápida y eficaz.</span><span class="sxs-lookup"><span data-stu-id="b729b-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="b729b-105">Este artículo lo ayuda a encontrar las distintas herramientas que necesita.</span><span class="sxs-lookup"><span data-stu-id="b729b-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggersmanaged-debuggersmd"></a>[<span data-ttu-id="b729b-106">Depuradores administrados</span><span class="sxs-lookup"><span data-stu-id="b729b-106">Managed debuggers</span></span>](managed-debuggers.md)
<span data-ttu-id="b729b-107">Los depuradores administrados le permiten interactuar con el programa.</span><span class="sxs-lookup"><span data-stu-id="b729b-107">Managed debuggers allow you to interact with your program.</span></span> <span data-ttu-id="b729b-108">Pausar, ejecutar de manera incremental, examinar y reanudar le proporcionan información sobre el comportamiento del código.</span><span class="sxs-lookup"><span data-stu-id="b729b-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="b729b-109">Un depurador es la primera opción para diagnosticar problemas funcionales que se pueden reproducir de manera fácil.</span><span class="sxs-lookup"><span data-stu-id="b729b-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracinglogging-tracingmd"></a>[<span data-ttu-id="b729b-110">Registro y seguimiento</span><span class="sxs-lookup"><span data-stu-id="b729b-110">Logging and tracing</span></span>](logging-tracing.md)
<span data-ttu-id="b729b-111">El registro y seguimiento son técnicas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="b729b-111">Logging and tracing are related techniques.</span></span> <span data-ttu-id="b729b-112">Hacen referencia a la instrumentación del código para crear archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="b729b-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="b729b-113">Los archivos registran los detalles de lo que hace un programa.</span><span class="sxs-lookup"><span data-stu-id="b729b-113">The files record the details of what a program does.</span></span> <span data-ttu-id="b729b-114">Estos detalles se pueden usar para diagnosticar los problemas más complejos.</span><span class="sxs-lookup"><span data-stu-id="b729b-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="b729b-115">Cuando se combinan con marcas de tiempo, estas técnicas también son valiosas para investigaciones de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b729b-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testingtestingindexmd"></a>[<span data-ttu-id="b729b-116">Pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="b729b-116">Unit testing</span></span>](../testing/index.md)
<span data-ttu-id="b729b-117">Las pruebas unitarias son un componente clave de la integración continua y la implementación de software de alta calidad.</span><span class="sxs-lookup"><span data-stu-id="b729b-117">Unit testing is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="b729b-118">Las pruebas unitarias están diseñadas para brindarle una advertencia temprana cuando se daña algo.</span><span class="sxs-lookup"><span data-stu-id="b729b-118">Unit tests are designed to give you an early warning when you break something.</span></span>
