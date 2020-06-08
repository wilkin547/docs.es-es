---
title: Subprocesos de primer y segundo plano
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], foreground
- threading [.NET Framework], background
- foreground threads
- background threads
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
ms.openlocfilehash: 5e7ec9e2c2a5ba3de1b4518cea15eb5f512640d3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84279690"
---
# <a name="foreground-and-background-threads"></a><span data-ttu-id="61910-102">Subprocesos de primer y segundo plano</span><span class="sxs-lookup"><span data-stu-id="61910-102">Foreground and Background Threads</span></span>
<span data-ttu-id="61910-103">Un subproceso administrado es un subproceso en segundo plano o un subproceso en primer plano.</span><span class="sxs-lookup"><span data-stu-id="61910-103">A managed thread is either a background thread or a foreground thread.</span></span> <span data-ttu-id="61910-104">Los subprocesos en segundo plano son idénticos a los subprocesos en primer plano con una excepción: un subproceso en segundo plano no mantiene el entorno de ejecución administrado en ejecución.</span><span class="sxs-lookup"><span data-stu-id="61910-104">Background threads are identical to foreground threads with one exception: a background thread does not keep the managed execution environment running.</span></span> <span data-ttu-id="61910-105">Una vez que todos los subprocesos en primer plano se han detenido en un proceso administrado (donde el archivo .exe es un ensamblado administrado), el sistema detiene todos los subprocesos en segundo plano y se cierra.</span><span class="sxs-lookup"><span data-stu-id="61910-105">Once all foreground threads have been stopped in a managed process (where the .exe file is a managed assembly), the system stops all background threads and shuts down.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="61910-106">Cuando el tiempo de ejecución detiene un subproceso en segundo plano porque el proceso se va a cerrar, no se inicia ninguna excepción en el subproceso.</span><span class="sxs-lookup"><span data-stu-id="61910-106">When the runtime stops a background thread because the process is shutting down, no exception is thrown in the thread.</span></span> <span data-ttu-id="61910-107">Sin embargo, cuando se detienen los subprocesos porque el método <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> descarga el dominio de aplicación, se produce <xref:System.Threading.ThreadAbortException> en los subprocesos en primer y segundo plano.</span><span class="sxs-lookup"><span data-stu-id="61910-107">However, when threads are stopped because the <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> method unloads the application domain, a <xref:System.Threading.ThreadAbortException> is thrown in both foreground and background threads.</span></span>  
  
 <span data-ttu-id="61910-108">Use la propiedad <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> para determinar si un subproceso es de primer o segundo plano o para cambiar su estado.</span><span class="sxs-lookup"><span data-stu-id="61910-108">Use the <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> property to determine whether a thread is a background or a foreground thread, or to change its status.</span></span> <span data-ttu-id="61910-109">Un subproceso puede cambiar a un subproceso en segundo plano en cualquier momento estableciendo su propiedad <xref:System.Threading.Thread.IsBackground%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="61910-109">A thread can be changed to a background thread at any time by setting its <xref:System.Threading.Thread.IsBackground%2A> property to `true`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="61910-110">El estado de primer o segundo plano de un subproceso no afecta al resultado de una excepción no controlada del subproceso.</span><span class="sxs-lookup"><span data-stu-id="61910-110">The foreground or background status of a thread does not affect the outcome of an unhandled exception in the thread.</span></span> <span data-ttu-id="61910-111">En la versión 2.0 de .NET Framework, una excepción no controlada de subprocesos en primer o segundo plano resulta en la terminación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="61910-111">In the .NET Framework version 2.0, an unhandled exception in either foreground or background threads results in termination of the application.</span></span> <span data-ttu-id="61910-112">Vea [Excepciones en subprocesos administrados](exceptions-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="61910-112">See [Exceptions in Managed Threads](exceptions-in-managed-threads.md).</span></span>  
  
 <span data-ttu-id="61910-113">Los subprocesos que pertenecen al grupo de subprocesos administrados (es decir, subprocesos cuya propiedad <xref:System.Threading.Thread.IsThreadPoolThread%2A> es `true`) son subprocesos en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="61910-113">Threads that belong to the managed thread pool (that is, threads whose <xref:System.Threading.Thread.IsThreadPoolThread%2A> property is `true`) are background threads.</span></span> <span data-ttu-id="61910-114">Todos los subprocesos que entran en el entorno de ejecución administrado desde el código no administrado se marcan como subprocesos en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="61910-114">All threads that enter the managed execution environment from unmanaged code are marked as background threads.</span></span> <span data-ttu-id="61910-115">Todos los subprocesos generados al crear e iniciar un nuevo objeto <xref:System.Threading.Thread> son subprocesos de primer plano predeterminados.</span><span class="sxs-lookup"><span data-stu-id="61910-115">All threads generated by creating and starting a new <xref:System.Threading.Thread> object are by default foreground threads.</span></span>  
  
 <span data-ttu-id="61910-116">Si utiliza un subproceso para controlar una actividad, como una conexión de socket, establezca su propiedad <xref:System.Threading.Thread.IsBackground%2A> en `true` para que el subproceso no impida la terminación del proceso.</span><span class="sxs-lookup"><span data-stu-id="61910-116">If you use a thread to monitor an activity, such as a socket connection, set its <xref:System.Threading.Thread.IsBackground%2A> property to `true` so that the thread does not prevent your process from terminating.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61910-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="61910-117">See also</span></span>

- <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>
- <xref:System.Threading.Thread>
- <xref:System.Threading.ThreadAbortException>
