---
title: "Cómo: Sincronizar operaciones simultáneas con una clase Barrier"
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
helpviewer_keywords: Barrier, how to use
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0b2e32fe3cec30a4da7467447aee625dfe7e379b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-synchronize-concurrent-operations-with-a-barrier"></a><span data-ttu-id="a2c9b-102">Cómo: Sincronizar operaciones simultáneas con una clase Barrier</span><span class="sxs-lookup"><span data-stu-id="a2c9b-102">How to: Synchronize Concurrent Operations with a Barrier</span></span>
<span data-ttu-id="a2c9b-103">En el ejemplo siguiente se muestra cómo sincronizar tareas simultáneas con una <xref:System.Threading.Barrier>.</span><span class="sxs-lookup"><span data-stu-id="a2c9b-103">The following example shows how to synchronize concurrent tasks with a <xref:System.Threading.Barrier>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2c9b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a2c9b-104">Example</span></span>  
 <span data-ttu-id="a2c9b-105">El propósito del programa siguiente es para contar cuántas iteraciones (o fases) son necesarios para dos subprocesos busquen cada uno su mitad de la solución en la misma fase utilizando un algoritmo de aleatoriedad para reorganizar las palabras.</span><span class="sxs-lookup"><span data-stu-id="a2c9b-105">The purpose of the following program is to count how many iterations (or phases) are required for two threads to each find their half of the solution on the same phase by using a randomizing algorithm to reshuffle the words.</span></span> <span data-ttu-id="a2c9b-106">Después de que cada subproceso se ordenan aleatoriamente sus palabras, la operación de barrera de posterior a la fase compara los dos resultados para ver si la frase completa se ha representado en el orden correcto de las palabras.</span><span class="sxs-lookup"><span data-stu-id="a2c9b-106">After each thread has shuffled its words, the barrier post-phase operation compares the two results to see if the complete sentence has been rendered in correct word order.</span></span>  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 <span data-ttu-id="a2c9b-107">A <xref:System.Threading.Barrier> es un objeto que impide que las tareas individuales en una operación paralela continúen hasta que todas las tareas alcancen la barrera.</span><span class="sxs-lookup"><span data-stu-id="a2c9b-107">A <xref:System.Threading.Barrier> is an object that prevents individual tasks in a parallel operation from continuing until all tasks reach the barrier.</span></span> <span data-ttu-id="a2c9b-108">Resulta útil cuando se produce una operación en paralelo en fases y cada fase requiere sincronización entre las tareas.</span><span class="sxs-lookup"><span data-stu-id="a2c9b-108">It is useful when a parallel operation occurs in phases, and each phase requires synchronization between tasks.</span></span> <span data-ttu-id="a2c9b-109">En este ejemplo, hay dos fases para la operación.</span><span class="sxs-lookup"><span data-stu-id="a2c9b-109">In this example, there are two phases to the operation.</span></span> <span data-ttu-id="a2c9b-110">En la primera fase, cada tarea rellena su sección del búfer con datos.</span><span class="sxs-lookup"><span data-stu-id="a2c9b-110">In the first phase, each task fills its section of the buffer with data.</span></span> <span data-ttu-id="a2c9b-111">Cuando cada tarea termina de rellenar su sección, la tarea señala la barrera que está listo para continuar y, a continuación, espera.</span><span class="sxs-lookup"><span data-stu-id="a2c9b-111">When each task finishes filling its section, the task signals the barrier that it is ready to continue, and then waits.</span></span> <span data-ttu-id="a2c9b-112">Cuando todas las tareas han señalizado la barrera, se desbloquean y comienza la segunda fase.</span><span class="sxs-lookup"><span data-stu-id="a2c9b-112">When all tasks have signaled the barrier, they are unblocked and the second phase starts.</span></span> <span data-ttu-id="a2c9b-113">La barrera es necesaria porque la segunda fase requiere que cada tarea tenga acceso a todos los datos que se ha generado para este punto.</span><span class="sxs-lookup"><span data-stu-id="a2c9b-113">The barrier is necessary because the second phase requires that each task have access to all the data that has been generated to this point.</span></span> <span data-ttu-id="a2c9b-114">Sin la barrera, las primeras tareas en completarse que pueden intentar leer de búferes que no se completaron aún por otras tareas.</span><span class="sxs-lookup"><span data-stu-id="a2c9b-114">Without the barrier, the first tasks to complete might try to read from buffers that have not been filled in yet by other tasks.</span></span> <span data-ttu-id="a2c9b-115">Puede sincronizar cualquier número de fases de esta manera.</span><span class="sxs-lookup"><span data-stu-id="a2c9b-115">You can synchronize any number of phases in this manner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2c9b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2c9b-116">See Also</span></span>  
 [<span data-ttu-id="a2c9b-117">Estructuras de datos para la programación paralela</span><span class="sxs-lookup"><span data-stu-id="a2c9b-117">Data Structures for Parallel Programming</span></span>](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)
