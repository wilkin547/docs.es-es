---
title: "Cómo: Habilitar el modo de seguimiento de subproceso en el bloqueo SpinLock"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca5f1b6eace7a24a6bbb7fd541858246828fa757
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a><span data-ttu-id="fdb62-102">Cómo: Habilitar el modo de seguimiento de subproceso en el bloqueo SpinLock</span><span class="sxs-lookup"><span data-stu-id="fdb62-102">How to: Enable Thread-Tracking Mode in SpinLock</span></span>
<span data-ttu-id="fdb62-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType>es un bloqueo de exclusión mutua bajo nivel que se puede usar para escenarios que tienen los tiempos de espera muy breve.</span><span class="sxs-lookup"><span data-stu-id="fdb62-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType> is a low-level mutual exclusion lock that you can use for scenarios that have very short wait times.</span></span> <span data-ttu-id="fdb62-104"><xref:System.Threading.SpinLock>no es reentrante.</span><span class="sxs-lookup"><span data-stu-id="fdb62-104"><xref:System.Threading.SpinLock> is not re-entrant.</span></span> <span data-ttu-id="fdb62-105">Después de que un subproceso entra en el bloqueo, debe salir correctamente el bloqueo antes de que pueda introducir de nuevo.</span><span class="sxs-lookup"><span data-stu-id="fdb62-105">After a thread enters the lock, it must exit the lock correctly before it can enter again.</span></span> <span data-ttu-id="fdb62-106">Por lo general, cualquier intento de volver a entrar en el bloqueo produciría un interbloqueo y los interbloqueos pueden ser muy difíciles de depurar.</span><span class="sxs-lookup"><span data-stu-id="fdb62-106">Typically, any attempt to re-enter the lock would cause deadlock, and deadlocks can be very difficult to debug.</span></span> <span data-ttu-id="fdb62-107">Como ayuda para el desarrollo, <xref:System.Threading.SpinLock?displayProperty=nameWithType> admite un modo de seguimiento de subprocesos que provoca que se produce cuando un subproceso intenta volver a entrar en un bloqueo que ya tenía una excepción.</span><span class="sxs-lookup"><span data-stu-id="fdb62-107">As an aid to development, <xref:System.Threading.SpinLock?displayProperty=nameWithType> supports a thread-tracking mode that causes an exception to be thrown when a thread attempts to re-enter a lock that it already holds.</span></span> <span data-ttu-id="fdb62-108">Esto le permite que localizar con mayor facilidad el punto en el que el bloqueo no se cerró correctamente.</span><span class="sxs-lookup"><span data-stu-id="fdb62-108">This lets you more easily locate the point at which the lock was not exited correctly.</span></span> <span data-ttu-id="fdb62-109">Puede activar el modo de seguimiento de subprocesos mediante el uso de la <xref:System.Threading.SpinLock> constructor que toma un valor booleano de entrada y pasando un argumento de entrada de `true`.</span><span class="sxs-lookup"><span data-stu-id="fdb62-109">You can turn on thread-tracking mode by using the <xref:System.Threading.SpinLock> constructor that takes a Boolean input parameter, and passing in an argument of `true`.</span></span> <span data-ttu-id="fdb62-110">Después de completar las fases de pruebas y desarrollo, desactiva el modo de seguimiento de subprocesos para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="fdb62-110">After you complete the development and testing phases, turn off thread-tracking mode for better performance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdb62-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdb62-111">Example</span></span>  
 <span data-ttu-id="fdb62-112">En el ejemplo siguiente se muestra el modo de seguimiento de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="fdb62-112">The following example demonstrates thread-tracking mode.</span></span> <span data-ttu-id="fdb62-113">Las líneas que salen correctamente del bloqueo están comentadas para simular un error de código que hace que uno de los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="fdb62-113">The lines that correctly exit the lock are commented out to simulate a coding error that causes one of the following results:</span></span>  
  
-   <span data-ttu-id="fdb62-114">Se produce una excepción si el <xref:System.Threading.SpinLock> se creó mediante un argumento de `true` (`True` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="fdb62-114">An exception is thrown if the <xref:System.Threading.SpinLock> was created by using an argument of `true` (`True` in Visual Basic).</span></span>  
  
-   <span data-ttu-id="fdb62-115">Produce un interbloqueo si el <xref:System.Threading.SpinLock> se creó mediante un argumento de `false` (`False` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="fdb62-115">Deadlock if the <xref:System.Threading.SpinLock> was created by using an argument of `false` (`False` in Visual Basic).</span></span>  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="fdb62-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdb62-116">See Also</span></span>  
 [<span data-ttu-id="fdb62-117">SpinLock</span><span class="sxs-lookup"><span data-stu-id="fdb62-117">SpinLock</span></span>](../../../docs/standard/threading/spinlock.md)
