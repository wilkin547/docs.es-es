---
title: Utilizar subprocesos y subprocesamiento
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 9b5ec2cd-121b-4d49-b075-222cf26f2344
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5bed13950a29cfa787ef8c9eb2608c6d74dfd49f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="using-threads-and-threading"></a><span data-ttu-id="48504-102">Utilizar subprocesos y subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="48504-102">Using Threads and Threading</span></span>
<span data-ttu-id="48504-103">En los temas de esta sección se explica la creación y administración de subprocesos administrados, cómo pasar datos a subprocesos administrados y recibir resultados devueltos y cómo destruir subprocesos y administrar una clase <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="48504-103">The topics in this section discuss the creation and management of managed threads, how to pass data to managed threads and get results back, and how to destroy threads and handle a <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="48504-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="48504-104">In This Section</span></span>  
 [<span data-ttu-id="48504-105">Crear subprocesos y analizar los datos en el inicio</span><span class="sxs-lookup"><span data-stu-id="48504-105">Creating Threads and Passing Data at Start Time</span></span>](../../../docs/standard/threading/creating-threads-and-passing-data-at-start-time.md)  
 <span data-ttu-id="48504-106">Se explica y muestra la creación de subprocesos administrados, incluso cómo pasar datos a nuevos subprocesos y cómo volver a obtener los datos.</span><span class="sxs-lookup"><span data-stu-id="48504-106">Discusses and demonstrates the creation of managed threads, including how to pass data to new threads and how to get data back.</span></span>  
  
 [<span data-ttu-id="48504-107">Pausar y reanudar subprocesos</span><span class="sxs-lookup"><span data-stu-id="48504-107">Pausing and Resuming Threads</span></span>](../../../docs/standard/threading/pausing-and-resuming-threads.md)  
 <span data-ttu-id="48504-108">Se explican las consecuencias de la pausa y reanudación de subprocesos administrados.</span><span class="sxs-lookup"><span data-stu-id="48504-108">Discusses the ramifications of pausing and resuming managed threads.</span></span>  
  
 [<span data-ttu-id="48504-109">Destruir subprocesos</span><span class="sxs-lookup"><span data-stu-id="48504-109">Destroying Threads</span></span>](../../../docs/standard/threading/destroying-threads.md)  
 <span data-ttu-id="48504-110">Se explican las consecuencias de destruir subprocesos administrados y cómo controlar una clase <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="48504-110">Discusses the ramifications of destroying managed threads, and how to handle a <xref:System.Threading.ThreadAbortException>.</span></span>  
  
 [<span data-ttu-id="48504-111">Planear subprocesos</span><span class="sxs-lookup"><span data-stu-id="48504-111">Scheduling Threads</span></span>](../../../docs/standard/threading/scheduling-threads.md)  
 <span data-ttu-id="48504-112">Se explican las prioridades de subproceso y cómo afectan a la programación de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="48504-112">Discusses thread priorities and how they affect thread scheduling.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="48504-113">Referencia</span><span class="sxs-lookup"><span data-stu-id="48504-113">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="48504-114">Proporciona documentación de referencia para la clase <xref:System.Threading.Thread>, que representa un subproceso administrado, independientemente de que provenga de código no administrado o que se creara en una aplicación administrada.</span><span class="sxs-lookup"><span data-stu-id="48504-114">Provides reference documentation for the <xref:System.Threading.Thread> class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.Threading.ThreadStart>  
 <span data-ttu-id="48504-115">Proporciona documentación de referencia para el delegado <xref:System.Threading.ThreadStart> que representa los procedimientos de subproceso sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="48504-115">Provides reference documentation for the <xref:System.Threading.ThreadStart> delegate that represents parameterless thread procedures.</span></span>  
  
 <xref:System.Threading.ParameterizedThreadStart>  
 <span data-ttu-id="48504-116">Proporciona una manera sencilla para pasar datos a un procedimiento de subproceso, aunque sin tipado fuerte.</span><span class="sxs-lookup"><span data-stu-id="48504-116">Provides an easy way to pass data to a thread procedure, although without strong typing.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="48504-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="48504-117">Related Sections</span></span>  
 [<span data-ttu-id="48504-118">Subprocesos y subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="48504-118">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)  
 <span data-ttu-id="48504-119">Proporciona una introducción a los subprocesos administrados.</span><span class="sxs-lookup"><span data-stu-id="48504-119">Provides an introduction to managed threading.</span></span>
