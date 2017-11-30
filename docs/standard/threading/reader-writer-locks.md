---
title: Bloqueos de lector y escritor
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ReaderWriterLock class, about ReaderWriterLock class
- threading [.NET Framework], ReaderWriterLock class
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: df06e83165906199774f99de4140ace9b7396cbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="reader-writer-locks"></a><span data-ttu-id="59214-102">Bloqueos de lector y escritor</span><span class="sxs-lookup"><span data-stu-id="59214-102">Reader-Writer Locks</span></span>
<span data-ttu-id="59214-103">La <xref:System.Threading.ReaderWriterLockSlim> clase permite que varios subprocesos leer un recurso al mismo tiempo, pero requiere que un subproceso debe esperar a un bloqueo exclusivo para poder escribir en el recurso.</span><span class="sxs-lookup"><span data-stu-id="59214-103">The <xref:System.Threading.ReaderWriterLockSlim> class enables multiple threads to read a resource concurrently, but requires a thread to wait for an exclusive lock in order to write to the resource.</span></span>  
  
 <span data-ttu-id="59214-104">Puede usar un <xref:System.Threading.ReaderWriterLockSlim> en la aplicación para proporcionar una sincronización conjunta entre los subprocesos que tienen acceso a un recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="59214-104">You might use a <xref:System.Threading.ReaderWriterLockSlim> in your application to provide cooperative synchronization among threads that access a shared resource.</span></span> <span data-ttu-id="59214-105">Los bloqueos se han realizado en el <xref:System.Threading.ReaderWriterLockSlim> propio.</span><span class="sxs-lookup"><span data-stu-id="59214-105">Locks are taken on the <xref:System.Threading.ReaderWriterLockSlim> itself.</span></span>  
  
 <span data-ttu-id="59214-106">Como con cualquier mecanismo de sincronización de subprocesos, debe asegurarse de que ningún subproceso omite el bloqueo proporcionado por <xref:System.Threading.ReaderWriterLockSlim>.</span><span class="sxs-lookup"><span data-stu-id="59214-106">As with any thread synchronization mechanism, you must ensure that no threads bypass the locking that is provided by <xref:System.Threading.ReaderWriterLockSlim>.</span></span> <span data-ttu-id="59214-107">Una manera de asegurarse de esto consiste en diseñar una clase que encapsula el recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="59214-107">One way to ensure this is to design a class that encapsulates the shared resource.</span></span> <span data-ttu-id="59214-108">Esta clase proporcionaría los miembros que tener acceso al recurso compartido privado y que utilicen una privada <xref:System.Threading.ReaderWriterLockSlim> para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="59214-108">This class would provide members that access the private shared resource and that use a private <xref:System.Threading.ReaderWriterLockSlim> for synchronization.</span></span> <span data-ttu-id="59214-109">Para obtener un ejemplo, vea el ejemplo de código para el <xref:System.Threading.ReaderWriterLockSlim> clase.</span><span class="sxs-lookup"><span data-stu-id="59214-109">For an example, see the code example for the <xref:System.Threading.ReaderWriterLockSlim> class.</span></span> <span data-ttu-id="59214-110"><xref:System.Threading.ReaderWriterLockSlim>es lo suficientemente eficaz para sincronizar objetos individuales.</span><span class="sxs-lookup"><span data-stu-id="59214-110"><xref:System.Threading.ReaderWriterLockSlim> is efficient enough to be used to synchronize individual objects.</span></span>  
  
 <span data-ttu-id="59214-111">Estructurar la aplicación para minimizar la duración de lectura y las operaciones de escritura.</span><span class="sxs-lookup"><span data-stu-id="59214-111">Structure your application to minimize the duration of read and write operations.</span></span> <span data-ttu-id="59214-112">Las operaciones de escritura de larga duración afectan al rendimiento porque el bloqueo de escritura es exclusivo.</span><span class="sxs-lookup"><span data-stu-id="59214-112">Long write operations affect throughput directly because the write lock is exclusive.</span></span> <span data-ttu-id="59214-113">Los escritores de espera de bloque de operaciones de lectura de larga duración y, si al menos un subproceso está esperando el acceso de escritura, también se bloquearán los subprocesos que soliciten acceso de lectura.</span><span class="sxs-lookup"><span data-stu-id="59214-113">Long read operations block waiting writers, and if at least one thread is waiting for write access, threads that request read access will be blocked as well.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59214-114">El [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] tiene dos bloqueos de lector y escritor, <xref:System.Threading.ReaderWriterLockSlim> y <xref:System.Threading.ReaderWriterLock>.</span><span class="sxs-lookup"><span data-stu-id="59214-114">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] has two reader-writer locks, <xref:System.Threading.ReaderWriterLockSlim> and <xref:System.Threading.ReaderWriterLock>.</span></span> <span data-ttu-id="59214-115"><xref:System.Threading.ReaderWriterLockSlim>se recomienda para todos los nuevos desarrollos.</span><span class="sxs-lookup"><span data-stu-id="59214-115"><xref:System.Threading.ReaderWriterLockSlim> is recommended for all new development.</span></span> <span data-ttu-id="59214-116"><xref:System.Threading.ReaderWriterLockSlim>es similar a <xref:System.Threading.ReaderWriterLock>, pero se han simplificado las reglas para que la recursividad y para actualizar y degradar el estado de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="59214-116"><xref:System.Threading.ReaderWriterLockSlim> is similar to <xref:System.Threading.ReaderWriterLock>, but it has simplified rules for recursion and for upgrading and downgrading lock state.</span></span> <span data-ttu-id="59214-117"><xref:System.Threading.ReaderWriterLockSlim>evita muchos casos de interbloqueo potencial.</span><span class="sxs-lookup"><span data-stu-id="59214-117"><xref:System.Threading.ReaderWriterLockSlim> avoids many cases of potential deadlock.</span></span> <span data-ttu-id="59214-118">Además, el rendimiento de <xref:System.Threading.ReaderWriterLockSlim> es significativamente mejores que <xref:System.Threading.ReaderWriterLock>.</span><span class="sxs-lookup"><span data-stu-id="59214-118">In addition, the performance of <xref:System.Threading.ReaderWriterLockSlim> is significantly better than <xref:System.Threading.ReaderWriterLock>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59214-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="59214-119">See Also</span></span>  
 <xref:System.Threading.ReaderWriterLockSlim>  
 <xref:System.Threading.ReaderWriterLock>  
 [<span data-ttu-id="59214-120">Subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="59214-120">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="59214-121">Objetos y características de subprocesos</span><span class="sxs-lookup"><span data-stu-id="59214-121">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
