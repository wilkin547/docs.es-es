---
title: Subprocesos de primer y segundo plano
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], foreground
- threading [.NET Framework], background
- foreground threads
- background threads
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42ad427fc2c1175c0d9b333aa418aea039f11a35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="foreground-and-background-threads"></a><span data-ttu-id="11d0a-102">Subprocesos de primer y segundo plano</span><span class="sxs-lookup"><span data-stu-id="11d0a-102">Foreground and Background Threads</span></span>
<span data-ttu-id="11d0a-103">Un subproceso administrado es un subproceso en segundo plano o en un subproceso en primer plano.</span><span class="sxs-lookup"><span data-stu-id="11d0a-103">A managed thread is either a background thread or a foreground thread.</span></span> <span data-ttu-id="11d0a-104">Subprocesos en segundo plano son idénticos a los subprocesos de primer plano con una excepción: un subproceso en segundo plano no mantiene el entorno de ejecución administrado.</span><span class="sxs-lookup"><span data-stu-id="11d0a-104">Background threads are identical to foreground threads with one exception: a background thread does not keep the managed execution environment running.</span></span> <span data-ttu-id="11d0a-105">Una vez que todos los subprocesos de primer plano se ha detenido en un proceso administrado (donde el archivo .exe es un ensamblado administrado), el sistema detiene todos los subprocesos en segundo plano y se cierra.</span><span class="sxs-lookup"><span data-stu-id="11d0a-105">Once all foreground threads have been stopped in a managed process (where the .exe file is a managed assembly), the system stops all background threads and shuts down.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11d0a-106">Cuando el tiempo de ejecución detiene un subproceso en segundo plano porque el proceso se va a cerrar, se inicia ninguna excepción en el subproceso.</span><span class="sxs-lookup"><span data-stu-id="11d0a-106">When the runtime stops a background thread because the process is shutting down, no exception is thrown in the thread.</span></span> <span data-ttu-id="11d0a-107">Sin embargo, cuando se detienen los subprocesos porque el <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> método descarga el dominio de aplicación, un <xref:System.Threading.ThreadAbortException> se produce en los subprocesos de primer plano y fondo.</span><span class="sxs-lookup"><span data-stu-id="11d0a-107">However, when threads are stopped because the <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> method unloads the application domain, a <xref:System.Threading.ThreadAbortException> is thrown in both foreground and background threads.</span></span>  
  
 <span data-ttu-id="11d0a-108">Use la <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> propiedad para determinar si un subproceso es un fondo o un subproceso en primer plano, o para cambiar su estado.</span><span class="sxs-lookup"><span data-stu-id="11d0a-108">Use the <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> property to determine whether a thread is a background or a foreground thread, or to change its status.</span></span> <span data-ttu-id="11d0a-109">Un subproceso puede cambiar a un subproceso en segundo plano en cualquier momento estableciendo su <xref:System.Threading.Thread.IsBackground%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="11d0a-109">A thread can be changed to a background thread at any time by setting its <xref:System.Threading.Thread.IsBackground%2A> property to `true`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="11d0a-110">El estado de primer plano o en segundo plano de un subproceso no afectan al resultado de una excepción no controlada en el subproceso.</span><span class="sxs-lookup"><span data-stu-id="11d0a-110">The foreground or background status of a thread does not affect the outcome of an unhandled exception in the thread.</span></span> <span data-ttu-id="11d0a-111">En la versión 2.0 de .NET Framework, una excepción no controlada en subprocesos de primer plano o en segundo plano da lugar a finalización de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="11d0a-111">In the .NET Framework version 2.0, an unhandled exception in either foreground or background threads results in termination of the application.</span></span> <span data-ttu-id="11d0a-112">Vea [excepciones en subprocesos administrados](../../../docs/standard/threading/exceptions-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="11d0a-112">See [Exceptions in Managed Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md).</span></span>  
  
 <span data-ttu-id="11d0a-113">Los subprocesos que pertenecen al grupo de subprocesos administrados (es decir, subprocesos cuya <xref:System.Threading.Thread.IsThreadPoolThread%2A> propiedad es `true`) son subprocesos en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="11d0a-113">Threads that belong to the managed thread pool (that is, threads whose <xref:System.Threading.Thread.IsThreadPoolThread%2A> property is `true`) are background threads.</span></span> <span data-ttu-id="11d0a-114">Todos los subprocesos que entran en el entorno de ejecución administrado desde código no administrado se marcan como subprocesos en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="11d0a-114">All threads that enter the managed execution environment from unmanaged code are marked as background threads.</span></span> <span data-ttu-id="11d0a-115">Todos los subprocesos generados al crear e iniciar un nuevo <xref:System.Threading.Thread> objeto son subprocesos de primer plano predeterminado.</span><span class="sxs-lookup"><span data-stu-id="11d0a-115">All threads generated by creating and starting a new <xref:System.Threading.Thread> object are by default foreground threads.</span></span>  
  
 <span data-ttu-id="11d0a-116">Si utiliza un subproceso para controlar una actividad, como una conexión de socket, establecer su <xref:System.Threading.Thread.IsBackground%2A> propiedad `true` para que el subproceso no impide que el proceso de terminación.</span><span class="sxs-lookup"><span data-stu-id="11d0a-116">If you use a thread to monitor an activity, such as a socket connection, set its <xref:System.Threading.Thread.IsBackground%2A> property to `true` so that the thread does not prevent your process from terminating.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11d0a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="11d0a-117">See Also</span></span>  
 <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadAbortException>
