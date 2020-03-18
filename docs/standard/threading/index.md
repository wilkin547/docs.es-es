---
title: Subprocesamiento administrado
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
ms.openlocfilehash: d6b8a0a4e16aa3169888958fa1376bfa61526dbd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73137931"
---
# <a name="managed-threading"></a><span data-ttu-id="de52d-102">Subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="de52d-102">Managed Threading</span></span>
<span data-ttu-id="de52d-103">Tanto si va a desarrollar aplicaciones para equipos con uno o varios procesadores, desea que la aplicación proporcione la interacción con mayor capacidad de respuesta con el usuario, incluso si la aplicación actualmente hace otro trabajo.</span><span class="sxs-lookup"><span data-stu-id="de52d-103">Whether you are developing for computers with one processor or several, you want your application to provide the most responsive interaction with the user, even if the application is currently doing other work.</span></span> <span data-ttu-id="de52d-104">Usar varios subprocesos de ejecución es una de las formas más eficaces de mantener que la aplicación siga respondiendo al usuario y, al mismo tiempo, usar el procesador entre eventos de usuario o durante los mismos.</span><span class="sxs-lookup"><span data-stu-id="de52d-104">Using multiple threads of execution is one of the most powerful ways to keep your application responsive to the user and at the same time make use of the processor in between or even during user events.</span></span> <span data-ttu-id="de52d-105">Si bien esta sección presenta los conceptos básicos del subprocesamiento, se centra en los conceptos del subprocesamiento administrado y su uso.</span><span class="sxs-lookup"><span data-stu-id="de52d-105">While this section introduces the basic concepts of threading, it focuses on managed threading concepts and using managed threading.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="de52d-106">A partir de .NET Framework 4, la programación multiproceso se ha simplificado significativamente con las clases <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md), clases de colecciones simultáneas nuevas en el espacio de nombres <xref:System.Collections.Concurrent?displayProperty=nameWithType> y un nuevo modelo de programación basado en el concepto de tareas en lugar de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="de52d-106">Starting with the .NET Framework 4, multithreaded programming is greatly simplified with the <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> classes, [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md), new concurrent collection classes in the <xref:System.Collections.Concurrent?displayProperty=nameWithType> namespace, and a new programming model that is based on the concept of tasks rather than threads.</span></span> <span data-ttu-id="de52d-107">Para más información, consulte [Parallel Programming](../../../docs/standard/parallel-programming/index.md) (Programación en paralelo).</span><span class="sxs-lookup"><span data-stu-id="de52d-107">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="de52d-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="de52d-108">In This Section</span></span>  
 [<span data-ttu-id="de52d-109">Principios básicos del subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="de52d-109">Managed Threading Basics</span></span>](../../../docs/standard/threading/managed-threading-basics.md)  
 <span data-ttu-id="de52d-110">Proporciona información general sobre el subprocesamiento administrado y describe cuándo usar varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="de52d-110">Provides an overview of managed threading and discusses when to use multiple threads.</span></span>  
  
 [<span data-ttu-id="de52d-111">Usar subprocesos y subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="de52d-111">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)  
 <span data-ttu-id="de52d-112">Explica cómo crear, iniciar, pausar, reanudar y anular subprocesos.</span><span class="sxs-lookup"><span data-stu-id="de52d-112">Explains how to create, start, pause, resume, and abort threads.</span></span>  
  
 [<span data-ttu-id="de52d-113">Procedimientos recomendados para el subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="de52d-113">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 <span data-ttu-id="de52d-114">Se describen los niveles de sincronización, cómo evitar interbloqueos y condiciones de carrera y otros problemas de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="de52d-114">Discusses levels of synchronization, how to avoid deadlocks and race conditions, and other threading issues.</span></span>  
  
 [<span data-ttu-id="de52d-115">Objetos y características de subprocesos</span><span class="sxs-lookup"><span data-stu-id="de52d-115">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 <span data-ttu-id="de52d-116">Describe las clases administradas que puede usar para sincronizar las actividades de subprocesamientos y los datos de objetos accedidos en distintos subprocesos, y proporciona información general sobre los subprocesos de grupos de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="de52d-116">Describes the managed classes you can use to synchronize the activities of threads and the data of objects accessed on different threads, and provides an overview of thread pool threads.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="de52d-117">Referencia</span><span class="sxs-lookup"><span data-stu-id="de52d-117">Reference</span></span>  
 <xref:System.Threading>  
 <span data-ttu-id="de52d-118">Contiene clases para usar y sincronizar subprocesos administrados.</span><span class="sxs-lookup"><span data-stu-id="de52d-118">Contains classes for using and synchronizing managed threads.</span></span>  
  
 <xref:System.Collections.Concurrent>  
 <span data-ttu-id="de52d-119">Contiene clases de colección seguras para usarlas con varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="de52d-119">Contains collection classes that are safe for use with multiple threads.</span></span>  
  
 <xref:System.Threading.Tasks>  
 <span data-ttu-id="de52d-120">Contiene clases para crear y programar tareas de procesamiento simultáneo.</span><span class="sxs-lookup"><span data-stu-id="de52d-120">Contains classes for creating and scheduling concurrent processing tasks.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="de52d-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="de52d-121">Related Sections</span></span>  
 [<span data-ttu-id="de52d-122">Dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="de52d-122">Application Domains</span></span>](../../../docs/framework/app-domains/application-domains.md)  
 <span data-ttu-id="de52d-123">Proporciona información genera sobre los dominios de aplicación y de su uso en Common Language Infrastructure.</span><span class="sxs-lookup"><span data-stu-id="de52d-123">Provides an overview of application domains and their use by the Common Language Infrastructure.</span></span>  
  
 [<span data-ttu-id="de52d-124">Asynchronous File I/O</span><span class="sxs-lookup"><span data-stu-id="de52d-124">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 <span data-ttu-id="de52d-125">Describe las ventajas de rendimiento y el funcionamiento básico de la E/S asincrónica.</span><span class="sxs-lookup"><span data-stu-id="de52d-125">Describes the performance advantages and basic operation of asynchronous I/O.</span></span>  
  
 <span data-ttu-id="de52d-126">[Modelo asincrónico basado en tareas [TAP]](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)</span><span class="sxs-lookup"><span data-stu-id="de52d-126">[Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)</span></span>  
 <span data-ttu-id="de52d-127">Proporciona una introducción del patrón recomendado para programación asincrónica en. NET.</span><span class="sxs-lookup"><span data-stu-id="de52d-127">Provides an overview of the recommended pattern for asynchronous programming in .NET.</span></span>  
  
 [<span data-ttu-id="de52d-128">Llamada a métodos sincrónicos de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="de52d-128">Calling Synchronous Methods Asynchronously</span></span>](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 <span data-ttu-id="de52d-129">Explica cómo llamar a métodos en los subprocesos de grupos de subprocesos con características integradas de delegados.</span><span class="sxs-lookup"><span data-stu-id="de52d-129">Explains how to call methods on thread pool threads using built-in features of delegates.</span></span>  
  
 [<span data-ttu-id="de52d-130">Programación en paralelo</span><span class="sxs-lookup"><span data-stu-id="de52d-130">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 <span data-ttu-id="de52d-131">Describe las bibliotecas de programación en paralelo, las que simplifican el uso de varios subprocesos en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="de52d-131">Describes the parallel programming libraries, which simplify the use of multiple threads in applications.</span></span>  
  
 [<span data-ttu-id="de52d-132">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="de52d-132">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 <span data-ttu-id="de52d-133">Describe un sistema para ejecutar consultas en paralelo a fin de aprovechar los distintos procesadores.</span><span class="sxs-lookup"><span data-stu-id="de52d-133">Describes a system for running queries in parallel, to take advantage of multiple processors.</span></span>
