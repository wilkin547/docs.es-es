---
title: Thread.Suspend, recolección de elementos no utilizados y puntos de seguridad
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- suspending threads
- safe points
- threading [.NET Framework], suspending
- threading [.NET Framework], garbage collection
- garbage collection, threads
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc3af01167fe97b701bdb0c7bc37af02d8e8a77c
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45658592"
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a><span data-ttu-id="d43c6-102">Thread.Suspend, recolección de elementos no utilizados y puntos de seguridad</span><span class="sxs-lookup"><span data-stu-id="d43c6-102">Thread.Suspend, Garbage Collection, and Safe Points</span></span>
<span data-ttu-id="d43c6-103">Cuando se llama a <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> en un subproceso, el sistema detecta que la suspensión de un subproceso se ha solicitado y permite la ejecución del subproceso hasta que ha alcanzado un punto seguro antes de suspender realmente el subproceso.</span><span class="sxs-lookup"><span data-stu-id="d43c6-103">When you call <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> on a thread, the system notes that a thread suspension has been requested and allows the thread to execute until it has reached a safe point before actually suspending the thread.</span></span> <span data-ttu-id="d43c6-104">Un punto seguro de un subproceso es un punto en su ejecución en que se puede ejecutar la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d43c6-104">A safe point for a thread is a point in its execution at which garbage collection can be performed.</span></span>  
  
 <span data-ttu-id="d43c6-105">Una vez que se alcanza un punto seguro, el tiempo de ejecución garantiza que el subproceso suspendido no realizará ningún progreso adicional en el código administrado.</span><span class="sxs-lookup"><span data-stu-id="d43c6-105">Once a safe point is reached, the runtime guarantees that the suspended thread will not make any further progress in managed code.</span></span> <span data-ttu-id="d43c6-106">Un subproceso que se ejecuta fuera del código administrado siempre es seguro para la recolección de elementos no utilizados y su ejecución continúa hasta que intenta reanudar la ejecución del código administrado.</span><span class="sxs-lookup"><span data-stu-id="d43c6-106">A thread executing outside managed code is always safe for garbage collection, and its execution continues until it attempts to resume execution of managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d43c6-107">Para realizar una recolección de elementos no utilizados, el tiempo de ejecución debe suspender todos los subprocesos salvo el subproceso que realiza la recolección.</span><span class="sxs-lookup"><span data-stu-id="d43c6-107">In order to perform a garbage collection, the runtime must suspend all the threads except the thread performing the collection.</span></span> <span data-ttu-id="d43c6-108">Cada subproceso debe llevarse a un punto seguro antes de que se pueda suspender.</span><span class="sxs-lookup"><span data-stu-id="d43c6-108">Each thread must be brought to a safe point before it can be suspended.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d43c6-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="d43c6-109">See also</span></span>

- <xref:System.Threading.Thread>  
- <xref:System.GC>  
- [<span data-ttu-id="d43c6-110">Subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="d43c6-110">Threading</span></span>](../../../docs/standard/threading/index.md)  
- [<span data-ttu-id="d43c6-111">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="d43c6-111">Automatic Memory Management</span></span>](../../../docs/standard/automatic-memory-management.md)
