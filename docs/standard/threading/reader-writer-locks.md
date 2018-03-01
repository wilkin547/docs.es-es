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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d005442ee74b46a0ecb1eaafe214e7190330cfe7
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="reader-writer-locks"></a><span data-ttu-id="11580-102">Bloqueos de lector y escritor</span><span class="sxs-lookup"><span data-stu-id="11580-102">Reader-Writer Locks</span></span>
<span data-ttu-id="11580-103">La clase <xref:System.Threading.ReaderWriterLockSlim> permite que varios subprocesos lean un recurso al mismo tiempo, pero requiere que un subproceso espere a un bloqueo exclusivo para poder escribir en el recurso.</span><span class="sxs-lookup"><span data-stu-id="11580-103">The <xref:System.Threading.ReaderWriterLockSlim> class enables multiple threads to read a resource concurrently, but requires a thread to wait for an exclusive lock in order to write to the resource.</span></span>  
  
 <span data-ttu-id="11580-104">Puede usar <xref:System.Threading.ReaderWriterLockSlim> en la aplicación para proporcionar una sincronización conjunta entre los subprocesos que acceden a un recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="11580-104">You might use a <xref:System.Threading.ReaderWriterLockSlim> in your application to provide cooperative synchronization among threads that access a shared resource.</span></span> <span data-ttu-id="11580-105">Los bloqueos se realizan en <xref:System.Threading.ReaderWriterLockSlim>.</span><span class="sxs-lookup"><span data-stu-id="11580-105">Locks are taken on the <xref:System.Threading.ReaderWriterLockSlim> itself.</span></span>  
  
 <span data-ttu-id="11580-106">Como con cualquier mecanismo de sincronización de subprocesos, debe asegurarse de que ningún subproceso omite el bloqueo proporcionado por <xref:System.Threading.ReaderWriterLockSlim>.</span><span class="sxs-lookup"><span data-stu-id="11580-106">As with any thread synchronization mechanism, you must ensure that no threads bypass the locking that is provided by <xref:System.Threading.ReaderWriterLockSlim>.</span></span> <span data-ttu-id="11580-107">Una manera de asegurarse de esto consiste en diseñar una clase que encapsula el recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="11580-107">One way to ensure this is to design a class that encapsulates the shared resource.</span></span> <span data-ttu-id="11580-108">Esta clase proporcionaría miembros que acceden al recurso compartido privado y que usan una clase privada <xref:System.Threading.ReaderWriterLockSlim> para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="11580-108">This class would provide members that access the private shared resource and that use a private <xref:System.Threading.ReaderWriterLockSlim> for synchronization.</span></span> <span data-ttu-id="11580-109">Para obtener un ejemplo, vea el ejemplo de código de la clase <xref:System.Threading.ReaderWriterLockSlim>.</span><span class="sxs-lookup"><span data-stu-id="11580-109">For an example, see the code example for the <xref:System.Threading.ReaderWriterLockSlim> class.</span></span> <span data-ttu-id="11580-110"><xref:System.Threading.ReaderWriterLockSlim> es lo suficientemente eficaz para sincronizar objetos individuales.</span><span class="sxs-lookup"><span data-stu-id="11580-110"><xref:System.Threading.ReaderWriterLockSlim> is efficient enough to be used to synchronize individual objects.</span></span>  
  
 <span data-ttu-id="11580-111">Estructure la aplicación para minimizar la duración de las operaciones de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="11580-111">Structure your application to minimize the duration of read and write operations.</span></span> <span data-ttu-id="11580-112">Las operaciones de escritura de larga duración afectan al rendimiento porque el bloqueo de escritura es exclusivo.</span><span class="sxs-lookup"><span data-stu-id="11580-112">Long write operations affect throughput directly because the write lock is exclusive.</span></span> <span data-ttu-id="11580-113">Los escritores de espera del bloque de operaciones de lectura de larga duración, y si al menos un subproceso espera el acceso de escritura, los subprocesos que solicitan acceso de lectura también se bloquearán.</span><span class="sxs-lookup"><span data-stu-id="11580-113">Long read operations block waiting writers, and if at least one thread is waiting for write access, threads that request read access will be blocked as well.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11580-114">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] tiene dos bloqueos de lector y escritor, <xref:System.Threading.ReaderWriterLockSlim> y <xref:System.Threading.ReaderWriterLock>.</span><span class="sxs-lookup"><span data-stu-id="11580-114">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] has two reader-writer locks, <xref:System.Threading.ReaderWriterLockSlim> and <xref:System.Threading.ReaderWriterLock>.</span></span> <span data-ttu-id="11580-115"><xref:System.Threading.ReaderWriterLockSlim> se recomienda para todos los nuevos desarrollos.</span><span class="sxs-lookup"><span data-stu-id="11580-115"><xref:System.Threading.ReaderWriterLockSlim> is recommended for all new development.</span></span> <span data-ttu-id="11580-116"><xref:System.Threading.ReaderWriterLockSlim> es similar a <xref:System.Threading.ReaderWriterLock>, pero se han simplificado las reglas para la recursividad y para actualizar y degradar el estado de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="11580-116"><xref:System.Threading.ReaderWriterLockSlim> is similar to <xref:System.Threading.ReaderWriterLock>, but it has simplified rules for recursion and for upgrading and downgrading lock state.</span></span> <span data-ttu-id="11580-117"><xref:System.Threading.ReaderWriterLockSlim> evita muchos casos de interbloqueo potencial.</span><span class="sxs-lookup"><span data-stu-id="11580-117"><xref:System.Threading.ReaderWriterLockSlim> avoids many cases of potential deadlock.</span></span> <span data-ttu-id="11580-118">Además, el rendimiento de <xref:System.Threading.ReaderWriterLockSlim> es significativamente mayor que <xref:System.Threading.ReaderWriterLock>.</span><span class="sxs-lookup"><span data-stu-id="11580-118">In addition, the performance of <xref:System.Threading.ReaderWriterLockSlim> is significantly better than <xref:System.Threading.ReaderWriterLock>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11580-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="11580-119">See Also</span></span>  
 <xref:System.Threading.ReaderWriterLockSlim>  
 <xref:System.Threading.ReaderWriterLock>  
 [<span data-ttu-id="11580-120">Subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="11580-120">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="11580-121">Objetos y características de subprocesos</span><span class="sxs-lookup"><span data-stu-id="11580-121">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
