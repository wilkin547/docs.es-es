---
title: Objetos y características de subprocesos
ms.date: 10/01/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f25609bc3c4dd829c66a1a4514b7f1121f9c0909
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2019
ms.locfileid: "55759033"
---
# <a name="threading-objects-and-features"></a><span data-ttu-id="2f04f-102">Objetos y características de subprocesos</span><span class="sxs-lookup"><span data-stu-id="2f04f-102">Threading objects and features</span></span>

<span data-ttu-id="2f04f-103">Junto con la clase <xref:System.Threading.Thread?displayProperty=nameWithType>, .NET proporciona una serie de clases que le ayudarán a desarrollar aplicaciones multiproceso.</span><span class="sxs-lookup"><span data-stu-id="2f04f-103">Along with the <xref:System.Threading.Thread?displayProperty=nameWithType> class, .NET provides a number of classes that help you develop multithreaded applications.</span></span> <span data-ttu-id="2f04f-104">En los siguientes artículos encontrará información general sobre estas clases:</span><span class="sxs-lookup"><span data-stu-id="2f04f-104">The following articles provide overview of those classes:</span></span>

|<span data-ttu-id="2f04f-105">Title</span><span class="sxs-lookup"><span data-stu-id="2f04f-105">Title</span></span>|<span data-ttu-id="2f04f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f04f-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="2f04f-107">Grupo de subprocesos administrado</span><span class="sxs-lookup"><span data-stu-id="2f04f-107">The managed thread pool</span></span>](the-managed-thread-pool.md)|<span data-ttu-id="2f04f-108">Describe cómo usar la clase <xref:System.Threading.ThreadPool?displayProperty=nameWithType>, que proporciona un grupo de subprocesos de trabajo administrados por .NET.</span><span class="sxs-lookup"><span data-stu-id="2f04f-108">Describes the <xref:System.Threading.ThreadPool?displayProperty=nameWithType> class, which provides a pool of worker threads that are managed by .NET.</span></span>|  
|<span data-ttu-id="2f04f-109">[Timers](timers.md) (Temporizadores)</span><span class="sxs-lookup"><span data-stu-id="2f04f-109">[Timers](timers.md)</span></span>|<span data-ttu-id="2f04f-110">Describe los temporizadores de .NET que se pueden usar en un entorno multiproceso.</span><span class="sxs-lookup"><span data-stu-id="2f04f-110">Describes .NET timers that can be used in a multithreaded environment.</span></span>|
|[<span data-ttu-id="2f04f-111">Información general sobre las primitivas de sincronización</span><span class="sxs-lookup"><span data-stu-id="2f04f-111">Overview of synchronization primitives</span></span>](overview-of-synchronization-primitives.md)|<span data-ttu-id="2f04f-112">Describe los tipos que se pueden usar para sincronizar el acceso a un recurso compartido o la interacción del subproceso de control.</span><span class="sxs-lookup"><span data-stu-id="2f04f-112">Describes types that can be used to synchronize access to a shared resource or control thread interaction.</span></span>|
|[<span data-ttu-id="2f04f-113">EventWaitHandle</span><span class="sxs-lookup"><span data-stu-id="2f04f-113">EventWaitHandle</span></span>](eventwaithandle.md)|<span data-ttu-id="2f04f-114">Describe la clase <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>, que representa un evento de sincronización de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="2f04f-114">Describes the <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> class, which represents a thread synchronization event.</span></span>|
|[<span data-ttu-id="2f04f-115">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="2f04f-115">CountdownEvent</span></span>](countdownevent.md)|<span data-ttu-id="2f04f-116">Describe la clase <xref:System.Threading.CountdownEvent?displayProperty=nameWithType>, que representa un evento de sincronización de subprocesos que se establece cuando su recuento es cero.</span><span class="sxs-lookup"><span data-stu-id="2f04f-116">Describes the <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> class, which represents a thread synchronization event that becomes set when its count is zero.</span></span>|
|<span data-ttu-id="2f04f-117">[Mutexes](mutexes.md) (Clases Mutex)</span><span class="sxs-lookup"><span data-stu-id="2f04f-117">[Mutexes](mutexes.md)</span></span>|<span data-ttu-id="2f04f-118">Describe la clase <xref:System.Threading.Mutex?displayProperty=nameWithType>, que concede acceso exclusivo a un recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="2f04f-118">Describes the <xref:System.Threading.Mutex?displayProperty=nameWithType> class, which grants exclusive access to a shared resource.</span></span>|
|<span data-ttu-id="2f04f-119">[Semaphore and SemaphoreSlim](semaphore-and-semaphoreslim.md) (Clases Semaphore y SemaphoreSlim)</span><span class="sxs-lookup"><span data-stu-id="2f04f-119">[Semaphore and SemaphoreSlim](semaphore-and-semaphoreslim.md)</span></span>|<span data-ttu-id="2f04f-120">Describe la clase <xref:System.Threading.Semaphore?displayProperty=nameWithType>, que limita el número de subprocesos que pueden tener acceso a un recurso compartido o grupo de recursos simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="2f04f-120">Describes the <xref:System.Threading.Semaphore?displayProperty=nameWithType> class, which limits number of threads that can access a shared resource or a pool of resources concurrently.</span></span>|
|<span data-ttu-id="2f04f-121">[Barrier](barrier.md) (Barrera)</span><span class="sxs-lookup"><span data-stu-id="2f04f-121">[Barrier](barrier.md)</span></span>|<span data-ttu-id="2f04f-122">Describe la clase <xref:System.Threading.Barrier?displayProperty=nameWithType>, que implementa el patrón de barrera para coordinar los subprocesos en las operaciones por fases.</span><span class="sxs-lookup"><span data-stu-id="2f04f-122">Describes the <xref:System.Threading.Barrier?displayProperty=nameWithType> class, which implements the barrier pattern for coordination of threads in phased operations.</span></span>|
|[<span data-ttu-id="2f04f-123">SpinLock</span><span class="sxs-lookup"><span data-stu-id="2f04f-123">SpinLock</span></span>](spinlock.md)|<span data-ttu-id="2f04f-124">Describe la estructura <xref:System.Threading.SpinLock?displayProperty=nameWithType>, que es una alternativa ligera a la clase <xref:System.Threading.Monitor?displayProperty=nameWithType> para algunos escenarios de bloqueo de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="2f04f-124">Describes the <xref:System.Threading.SpinLock?displayProperty=nameWithType> structure, which is a lightweight alternative to the <xref:System.Threading.Monitor?displayProperty=nameWithType> class for certain low-level locking scenarios.</span></span>|
|[<span data-ttu-id="2f04f-125">SpinWait</span><span class="sxs-lookup"><span data-stu-id="2f04f-125">SpinWait</span></span>](spinwait.md)|<span data-ttu-id="2f04f-126">Describe la estructura <xref:System.Threading.SpinWait?displayProperty=nameWithType>, que proporciona compatibilidad para la espera basada en ciclos.</span><span class="sxs-lookup"><span data-stu-id="2f04f-126">Describes the <xref:System.Threading.SpinWait?displayProperty=nameWithType> structure, which provides support for spin-based waiting.</span></span>|

## <a name="see-also"></a><span data-ttu-id="2f04f-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f04f-127">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- [<span data-ttu-id="2f04f-128">Uso de subprocesos y subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="2f04f-128">Using threads and threading</span></span>](using-threads-and-threading.md)
- [<span data-ttu-id="2f04f-129">Asynchronous File I/O</span><span class="sxs-lookup"><span data-stu-id="2f04f-129">Asynchronous File I/O</span></span>](../io/asynchronous-file-i-o.md)
- [<span data-ttu-id="2f04f-130">Programación en paralelo</span><span class="sxs-lookup"><span data-stu-id="2f04f-130">Parallel Programming</span></span>](../parallel-programming/index.md)
- [<span data-ttu-id="2f04f-131">Biblioteca TPL</span><span class="sxs-lookup"><span data-stu-id="2f04f-131">Task Parallel Library (TPL)</span></span>](../parallel-programming/task-parallel-library-tpl.md)
