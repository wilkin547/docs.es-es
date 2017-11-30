---
title: "Cómo: Usar SpinWait para implementar una operación de espera de dos fases"
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
helpviewer_keywords: SpinWait, how to synchronize two-phase wait
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2717ba2d63e4ecf40638c369b66f2c696e396a5e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-spinwait-to-implement-a-two-phase-wait-operation"></a><span data-ttu-id="dee86-102">Cómo: Usar SpinWait para implementar una operación de espera de dos fases</span><span class="sxs-lookup"><span data-stu-id="dee86-102">How to: Use SpinWait to Implement a Two-Phase Wait Operation</span></span>
<span data-ttu-id="dee86-103">En el ejemplo siguiente se muestra cómo utilizar un <xref:System.Threading.SpinWait?displayProperty=nameWithType> objeto para implementar una operación de espera de dos fases.</span><span class="sxs-lookup"><span data-stu-id="dee86-103">The following example shows how to use a <xref:System.Threading.SpinWait?displayProperty=nameWithType> object to implement a two-phase wait operation.</span></span> <span data-ttu-id="dee86-104">En la primera fase, el objeto de sincronización, un `Latch`, gira durante unos ciclos mientras comprueba si el bloqueo esté disponible.</span><span class="sxs-lookup"><span data-stu-id="dee86-104">In the first phase, the synchronization object, a `Latch`, spins for a few cycles while it checks whether the lock has become available.</span></span> <span data-ttu-id="dee86-105">En la segunda fase, si el bloqueo esté disponible, la `Wait` método devuelve sin usar la <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> para realizar la espera; en caso contrario, `Wait` realiza la espera.</span><span class="sxs-lookup"><span data-stu-id="dee86-105">In the second phase, if the lock becomes available, then the `Wait` method returns without using the <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> to perform its wait; otherwise, `Wait` performs the wait.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dee86-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dee86-106">Example</span></span>  
 <span data-ttu-id="dee86-107">Este ejemplo muestra una implementación muy básica de una sincronización de bloqueo temporal primitivo.</span><span class="sxs-lookup"><span data-stu-id="dee86-107">This example shows a very basic implementation of a Latch synchronization primitive.</span></span> <span data-ttu-id="dee86-108">Puede usar esta estructura de datos cuando se espera que los tiempos de espera sean muy cortos.</span><span class="sxs-lookup"><span data-stu-id="dee86-108">You can use this data structure when wait times are expected to be very short.</span></span> <span data-ttu-id="dee86-109">En este ejemplo es solo con fines de demostración.</span><span class="sxs-lookup"><span data-stu-id="dee86-109">This example is for demonstration purposes only.</span></span> <span data-ttu-id="dee86-110">Si necesita funcionalidad de tipo de bloqueo temporal en el programa, considere la posibilidad de usar <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dee86-110">If you require latch-type functionality in your program, consider using <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 <span data-ttu-id="dee86-111">Utiliza el bloqueo la <xref:System.Threading.SpinWait> objeto que se va a girar en su posición solo hasta la siguiente llamada a `SpinOnce` hace que el <xref:System.Threading.SpinWait> para producir el intervalo de tiempo del subproceso.</span><span class="sxs-lookup"><span data-stu-id="dee86-111">The latch uses the <xref:System.Threading.SpinWait> object to spin in place only until the next call to `SpinOnce` causes the <xref:System.Threading.SpinWait> to yield the time slice of the thread.</span></span> <span data-ttu-id="dee86-112">En ese momento, el bloqueo temporal produce su propio cambio de contexto mediante una llamada a <xref:System.Threading.WaitHandle.WaitOne%2A> en el <xref:System.Threading.ManualResetEvent> y pasar el resto del valor de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="dee86-112">At that point, the latch causes its own context switch by calling <xref:System.Threading.WaitHandle.WaitOne%2A> on the <xref:System.Threading.ManualResetEvent> and passing in the remainder of the time-out value.</span></span>  
  
 <span data-ttu-id="dee86-113">La salida del registro muestra la frecuencia con el bloqueo pudo aumentar el rendimiento al adquirir el bloqueo sin utilizar el <xref:System.Threading.ManualResetEvent>.</span><span class="sxs-lookup"><span data-stu-id="dee86-113">The logging output shows how often the Latch was able to increase performance by acquiring the lock without using the <xref:System.Threading.ManualResetEvent>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dee86-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="dee86-114">See Also</span></span>  
 [<span data-ttu-id="dee86-115">SpinWait</span><span class="sxs-lookup"><span data-stu-id="dee86-115">SpinWait</span></span>](../../../docs/standard/threading/spinwait.md)  
 [<span data-ttu-id="dee86-116">Objetos y características de subprocesos</span><span class="sxs-lookup"><span data-stu-id="dee86-116">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
