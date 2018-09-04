---
title: Eventos ETW de CLR
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 983c38567667da911132217dcfda37c009dc833c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504134"
---
# <a name="clr-etw-events"></a><span data-ttu-id="09dce-102">Eventos ETW de CLR</span><span class="sxs-lookup"><span data-stu-id="09dce-102">CLR ETW Events</span></span>
<span data-ttu-id="09dce-103">Los temas de esta sección describen los eventos de seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="09dce-103">The topics in this section describe event tracing for Windows (ETW) events.</span></span> <span data-ttu-id="09dce-104">Cada evento tiene una palabra clave y un nivel asociados que se describen en el tema [Palabras clave y niveles ETW de CLR](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="09dce-104">Each event has an associated keyword and level, which are described in the [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md) topic.</span></span> <span data-ttu-id="09dce-105">CLR tiene dos proveedores para los eventos:</span><span class="sxs-lookup"><span data-stu-id="09dce-105">The CLR has two providers for the events:</span></span>  
  
-   <span data-ttu-id="09dce-106">El proveedor en tiempo de ejecución genera eventos en función de las palabras clave (categorías de eventos) que están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="09dce-106">The runtime provider, which raises events depending on which keywords (categories of events) are enabled.</span></span> <span data-ttu-id="09dce-107">El GUID del proveedor en tiempo de ejecución de CLR es e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span><span class="sxs-lookup"><span data-stu-id="09dce-107">The CLR runtime provider GUID is e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span></span>  
  
-   <span data-ttu-id="09dce-108">El proveedor de informe detallado, que es para fines especiales.</span><span class="sxs-lookup"><span data-stu-id="09dce-108">The rundown provider, which has special-purpose uses.</span></span> <span data-ttu-id="09dce-109">El GUID del proveedor de informe detallado de CLR es a669021c-c450-4609-a035-5af59af4df18.</span><span class="sxs-lookup"><span data-stu-id="09dce-109">The CLR rundown provider GUID is a669021c-c450-4609-a035-5af59af4df18.</span></span>  
  
 <span data-ttu-id="09dce-110">Para más información, vea [Proveedores ETW de CLR](../../../docs/framework/performance/clr-etw-providers.md).</span><span class="sxs-lookup"><span data-stu-id="09dce-110">For more information about the providers, see [CLR ETW Providers](../../../docs/framework/performance/clr-etw-providers.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="09dce-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="09dce-111">In This Section</span></span>  
 [<span data-ttu-id="09dce-112">Eventos de información en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="09dce-112">Runtime Information Events</span></span>](../../../docs/framework/performance/runtime-information-etw-events.md)  
 <span data-ttu-id="09dce-113">Capturan información sobre el tiempo de ejecución, lo que incluye la SKU, el número de versión, la manera en que se ha activado el tiempo de ejecución, los parámetros de línea de comandos con los que se ha iniciado, el GUID (si está disponible) y otra información relevante.</span><span class="sxs-lookup"><span data-stu-id="09dce-113">Captures information about the runtime, including the SKU, version number, the manner in which the runtime was activated, the command-line parameters it was started with, the GUID (if applicable), and other relevant information.</span></span>  
  
 [<span data-ttu-id="09dce-114">Evento de excepción Thrown_V1</span><span class="sxs-lookup"><span data-stu-id="09dce-114">Exception Thrown_V1 Event</span></span>](../../../docs/framework/performance/exception-thrown-v1-etw-event.md)  
 <span data-ttu-id="09dce-115">Captura información de excepciones.</span><span class="sxs-lookup"><span data-stu-id="09dce-115">Captures information about exceptions that are thrown.</span></span>  
  
 [<span data-ttu-id="09dce-116">Eventos de contención</span><span class="sxs-lookup"><span data-stu-id="09dce-116">Contention Events</span></span>](../../../docs/framework/performance/contention-etw-events.md)  
 <span data-ttu-id="09dce-117">Capturan información sobre la contención para bloqueos de monitor o nativos que use el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="09dce-117">Captures information about contention for monitor locks or native locks that the runtime uses.</span></span>  
  
 [<span data-ttu-id="09dce-118">Eventos de grupos de subprocesos</span><span class="sxs-lookup"><span data-stu-id="09dce-118">Thread Pool Events</span></span>](../../../docs/framework/performance/thread-pool-etw-events.md)  
 <span data-ttu-id="09dce-119">Capturan información sobre grupos de subprocesos de trabajo y de E/S.</span><span class="sxs-lookup"><span data-stu-id="09dce-119">Captures information about worker thread pools and I/O thread pools.</span></span>  
  
 [<span data-ttu-id="09dce-120">Eventos de cargador</span><span class="sxs-lookup"><span data-stu-id="09dce-120">Loader Events</span></span>](../../../docs/framework/performance/loader-etw-events.md)  
 <span data-ttu-id="09dce-121">Capturan información sobre la carga y descarga de dominios, ensamblados y módulos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="09dce-121">Captures information about loading and unloading application domains, assemblies, and modules.</span></span>  
  
 [<span data-ttu-id="09dce-122">Eventos de método</span><span class="sxs-lookup"><span data-stu-id="09dce-122">Method Events</span></span>](../../../docs/framework/performance/method-etw-events.md)  
 <span data-ttu-id="09dce-123">Capturan información sobre métodos CLR para resolución de símbolo.</span><span class="sxs-lookup"><span data-stu-id="09dce-123">Captures information about CLR methods for symbol resolution.</span></span>  
  
 [<span data-ttu-id="09dce-124">Eventos de recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="09dce-124">Garbage Collection Events</span></span>](../../../docs/framework/performance/garbage-collection-etw-events.md)  
 <span data-ttu-id="09dce-125">Capturan información relativa a la recolección de elementos no utilizados, para facilitar la depuración y el diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="09dce-125">Captures information pertaining to garbage collection, to help in diagnostics and debugging.</span></span>  
  
 [<span data-ttu-id="09dce-126">Eventos de traza JIT</span><span class="sxs-lookup"><span data-stu-id="09dce-126">JIT Tracing Events</span></span>](../../../docs/framework/performance/jit-tracing-etw-events.md)  
 <span data-ttu-id="09dce-127">Capturan información sobre inclusión en línea JIT y llamadas de cola.</span><span class="sxs-lookup"><span data-stu-id="09dce-127">Captures information about just-in-time (JIT) inlining and tail calls.</span></span>  
  
 [<span data-ttu-id="09dce-128">Eventos de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="09dce-128">Interop Events</span></span>](../../../docs/framework/performance/interop-etw-events.md)  
 <span data-ttu-id="09dce-129">Capturan información sobre generación de código auxiliar y almacenamiento en memoria caché del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="09dce-129">Captures information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 [<span data-ttu-id="09dce-130">Eventos ARM</span><span class="sxs-lookup"><span data-stu-id="09dce-130">ARM Events</span></span>](../../../docs/framework/performance/application-domain-resource-monitoring-arm-etw-events.md)  
 <span data-ttu-id="09dce-131">Capturan información de diagnóstico detallada sobre el estado de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="09dce-131">Captures detailed diagnostic information about the state of an application domain.</span></span>  
  
 [<span data-ttu-id="09dce-132">Eventos de seguridad</span><span class="sxs-lookup"><span data-stu-id="09dce-132">Security Events</span></span>](../../../docs/framework/performance/security-etw-events.md)  
 <span data-ttu-id="09dce-133">Capturan información sobre verificación de nombres seguros y Authenticode.</span><span class="sxs-lookup"><span data-stu-id="09dce-133">Captures information about strong name and Authenticode verification.</span></span>  
  
 [<span data-ttu-id="09dce-134">Evento de pila</span><span class="sxs-lookup"><span data-stu-id="09dce-134">Stack Event</span></span>](../../../docs/framework/performance/stack-etw-event.md)  
 <span data-ttu-id="09dce-135">Captura información usada con otros eventos para generar seguimientos de pilas después de que se haya generado un evento.</span><span class="sxs-lookup"><span data-stu-id="09dce-135">Captures information that is used with other events to generate stack traces after an event is raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09dce-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="09dce-136">See Also</span></span>  
 [<span data-ttu-id="09dce-137">Mejorar la depuración y optimización del rendimiento con ETW</span><span class="sxs-lookup"><span data-stu-id="09dce-137">Improve Debugging And Performance Tuning With ETW</span></span>](https://go.microsoft.com/fwlink/?LinkId=179696)  
 [<span data-ttu-id="09dce-138">Blog de rendimiento de Windows</span><span class="sxs-lookup"><span data-stu-id="09dce-138">Windows Performance Blog</span></span>](https://go.microsoft.com/fwlink/?LinkId=179509)  
 [<span data-ttu-id="09dce-139">Controlar el registro de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="09dce-139">Controlling .NET Framework Logging</span></span>](../../../docs/framework/performance/controlling-logging.md)  
 [<span data-ttu-id="09dce-140">Proveedores ETW de CLR</span><span class="sxs-lookup"><span data-stu-id="09dce-140">CLR ETW Providers</span></span>](../../../docs/framework/performance/clr-etw-providers.md)  
 [<span data-ttu-id="09dce-141">Palabras clave y niveles ETW de CLR</span><span class="sxs-lookup"><span data-stu-id="09dce-141">CLR ETW Keywords and Levels</span></span>](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)  
 [<span data-ttu-id="09dce-142">Eventos ETW en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="09dce-142">ETW Events in the Common Language Runtime</span></span>](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)
