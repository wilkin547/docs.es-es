---
title: 'Cómo: Usar SpinWait para implementar una operación de espera de dos fases'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinWait, how to synchronize two-phase wait
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
ms.openlocfilehash: e5d58067f70706294308952b9f7cfbf69fa89a58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728490"
---
# <a name="how-to-use-spinwait-to-implement-a-two-phase-wait-operation"></a><span data-ttu-id="33b3a-102">Cómo: Usar SpinWait para implementar una operación de espera de dos fases</span><span class="sxs-lookup"><span data-stu-id="33b3a-102">How to: Use SpinWait to Implement a Two-Phase Wait Operation</span></span>

<span data-ttu-id="33b3a-103">En el ejemplo siguiente se muestra cómo utilizar un objeto <xref:System.Threading.SpinWait?displayProperty=nameWithType> para implementar una operación de espera de dos fases.</span><span class="sxs-lookup"><span data-stu-id="33b3a-103">The following example shows how to use a <xref:System.Threading.SpinWait?displayProperty=nameWithType> object to implement a two-phase wait operation.</span></span> <span data-ttu-id="33b3a-104">En la primera fase, el objeto de sincronización, `Latch`, gira durante unos ciclos mientras comprueba si el bloqueo está disponible.</span><span class="sxs-lookup"><span data-stu-id="33b3a-104">In the first phase, the synchronization object, a `Latch`, spins for a few cycles while it checks whether the lock has become available.</span></span> <span data-ttu-id="33b3a-105">En la segunda fase, si el bloqueo está disponible, el método `Wait` realiza la devolución sin usar <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> para la espera; en caso contrario, `Wait` realiza la espera.</span><span class="sxs-lookup"><span data-stu-id="33b3a-105">In the second phase, if the lock becomes available, then the `Wait` method returns without using the <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> to perform its wait; otherwise, `Wait` performs the wait.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33b3a-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33b3a-106">Example</span></span>  

 <span data-ttu-id="33b3a-107">En este ejemplo se muestra una implementación muy básica de un elemento primitivo de sincronización de bloqueo temporal.</span><span class="sxs-lookup"><span data-stu-id="33b3a-107">This example shows a very basic implementation of a Latch synchronization primitive.</span></span> <span data-ttu-id="33b3a-108">Puede usar esta estructura de datos cuando se prevé que los tiempos de espera sean muy cortos.</span><span class="sxs-lookup"><span data-stu-id="33b3a-108">You can use this data structure when wait times are expected to be very short.</span></span> <span data-ttu-id="33b3a-109">Este ejemplo solamente sirve de demostración.</span><span class="sxs-lookup"><span data-stu-id="33b3a-109">This example is for demonstration purposes only.</span></span> <span data-ttu-id="33b3a-110">Si necesita una funcionalidad de tipo de bloqueo temporal en el programa, considere la posibilidad de usar <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="33b3a-110">If you require latch-type functionality in your program, consider using <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 <span data-ttu-id="33b3a-111">El bloqueo temporal usa el objeto <xref:System.Threading.SpinWait> para girar in situ hasta que la siguiente llamada a `SpinOnce` da lugar a que <xref:System.Threading.SpinWait> produzca el intervalo de tiempo del subproceso.</span><span class="sxs-lookup"><span data-stu-id="33b3a-111">The latch uses the <xref:System.Threading.SpinWait> object to spin in place only until the next call to `SpinOnce` causes the <xref:System.Threading.SpinWait> to yield the time slice of the thread.</span></span> <span data-ttu-id="33b3a-112">En ese momento, el bloqueo temporal produce su propio cambio de contexto mediante una llamada a <xref:System.Threading.WaitHandle.WaitOne%2A> en <xref:System.Threading.ManualResetEvent> y pasa el resto del valor de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="33b3a-112">At that point, the latch causes its own context switch by calling <xref:System.Threading.WaitHandle.WaitOne%2A> on the <xref:System.Threading.ManualResetEvent> and passing in the remainder of the time-out value.</span></span>  
  
 <span data-ttu-id="33b3a-113">La salida del registro muestra la frecuencia con que el bloqueo temporal pudo aumentar el rendimiento mediante la adquisición del bloqueo sin usar <xref:System.Threading.ManualResetEvent>.</span><span class="sxs-lookup"><span data-stu-id="33b3a-113">The logging output shows how often the Latch was able to increase performance by acquiring the lock without using the <xref:System.Threading.ManualResetEvent>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33b3a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="33b3a-114">See also</span></span>

- [<span data-ttu-id="33b3a-115">SpinWait</span><span class="sxs-lookup"><span data-stu-id="33b3a-115">SpinWait</span></span>](spinwait.md)
- [<span data-ttu-id="33b3a-116">Objetos y características de subprocesos</span><span class="sxs-lookup"><span data-stu-id="33b3a-116">Threading Objects and Features</span></span>](threading-objects-and-features.md)
