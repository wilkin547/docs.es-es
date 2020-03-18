---
title: 'Cómo: Sincronizar operaciones simultáneas con una clase Barrier'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Barrier, how to use
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
ms.openlocfilehash: 33098878764c2f8a8c1f83a122028da40b984243
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73137973"
---
# <a name="how-to-synchronize-concurrent-operations-with-a-barrier"></a><span data-ttu-id="d2242-102">Cómo: Sincronizar operaciones simultáneas con una clase Barrier</span><span class="sxs-lookup"><span data-stu-id="d2242-102">How to: Synchronize Concurrent Operations with a Barrier</span></span>
<span data-ttu-id="d2242-103">En el ejemplo siguiente se muestra cómo sincronizar tareas simultáneas con <xref:System.Threading.Barrier>.</span><span class="sxs-lookup"><span data-stu-id="d2242-103">The following example shows how to synchronize concurrent tasks with a <xref:System.Threading.Barrier>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2242-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d2242-104">Example</span></span>  
 <span data-ttu-id="d2242-105">El propósito del programa siguiente es contar cuántas iteraciones o fases son necesarias para que dos subprocesos busquen cada uno su mitad de la solución en la misma fase utilizando un algoritmo aleatorio para reorganizar las palabras.</span><span class="sxs-lookup"><span data-stu-id="d2242-105">The purpose of the following program is to count how many iterations (or phases) are required for two threads to each find their half of the solution on the same phase by using a randomizing algorithm to reshuffle the words.</span></span> <span data-ttu-id="d2242-106">Después de que cada subproceso haya ordenado sus palabras, la operación de barrera posterior a la fase compara los dos resultados para ver si la oración completa se ha representado en el orden de palabras correcto.</span><span class="sxs-lookup"><span data-stu-id="d2242-106">After each thread has shuffled its words, the barrier post-phase operation compares the two results to see if the complete sentence has been rendered in correct word order.</span></span>  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 <span data-ttu-id="d2242-107"><xref:System.Threading.Barrier> es un objeto que impide que las tareas individuales de una operación paralela continúen hasta que todas las tareas alcancen la barrera.</span><span class="sxs-lookup"><span data-stu-id="d2242-107">A <xref:System.Threading.Barrier> is an object that prevents individual tasks in a parallel operation from continuing until all tasks reach the barrier.</span></span> <span data-ttu-id="d2242-108">Resulta útil cuando se produce una operación paralela en fases y cada fase requiere sincronización entre las tareas.</span><span class="sxs-lookup"><span data-stu-id="d2242-108">It is useful when a parallel operation occurs in phases, and each phase requires synchronization between tasks.</span></span> <span data-ttu-id="d2242-109">En este ejemplo, hay dos fases para la operación.</span><span class="sxs-lookup"><span data-stu-id="d2242-109">In this example, there are two phases to the operation.</span></span> <span data-ttu-id="d2242-110">En la primera fase, cada tarea rellena su sección del búfer con datos.</span><span class="sxs-lookup"><span data-stu-id="d2242-110">In the first phase, each task fills its section of the buffer with data.</span></span> <span data-ttu-id="d2242-111">Cuando cada tarea termina de rellenar su sección, la tarea señala la barrera que está lista para continuar y, a continuación, espera.</span><span class="sxs-lookup"><span data-stu-id="d2242-111">When each task finishes filling its section, the task signals the barrier that it is ready to continue, and then waits.</span></span> <span data-ttu-id="d2242-112">Cuando todas las tareas han señalado la barrera, se desbloquean y comienza la segunda fase.</span><span class="sxs-lookup"><span data-stu-id="d2242-112">When all tasks have signaled the barrier, they are unblocked and the second phase starts.</span></span> <span data-ttu-id="d2242-113">La barrera es necesaria porque la segunda fase requiere que cada tarea tenga acceso a todos los datos generados para este punto.</span><span class="sxs-lookup"><span data-stu-id="d2242-113">The barrier is necessary because the second phase requires that each task have access to all the data that has been generated to this point.</span></span> <span data-ttu-id="d2242-114">Sin la barrera, las primeras tareas en completarse pueden intentar leer de búferes que otras tareas aún no completaron.</span><span class="sxs-lookup"><span data-stu-id="d2242-114">Without the barrier, the first tasks to complete might try to read from buffers that have not been filled in yet by other tasks.</span></span> <span data-ttu-id="d2242-115">Puede sincronizar cualquier número de fases de esta manera.</span><span class="sxs-lookup"><span data-stu-id="d2242-115">You can synchronize any number of phases in this manner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2242-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2242-116">See also</span></span>

- [<span data-ttu-id="d2242-117">Estructuras de datos para la programación paralela</span><span class="sxs-lookup"><span data-stu-id="d2242-117">Data Structures for Parallel Programming</span></span>](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)
