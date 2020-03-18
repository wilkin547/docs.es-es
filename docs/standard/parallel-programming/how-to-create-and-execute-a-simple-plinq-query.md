---
title: 'Cómo: Crear y ejecutar una consulta PLINQ simple'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create
ms.assetid: 983b4213-bddd-4a44-9262-cbe59186df4c
ms.openlocfilehash: 349cc8d78e9a080d720e09a7e3e5e314752605c7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73106961"
---
# <a name="how-to-create-and-execute-a-simple-plinq-query"></a><span data-ttu-id="a96a3-102">Cómo: Crear y ejecutar una consulta PLINQ simple</span><span class="sxs-lookup"><span data-stu-id="a96a3-102">How to: Create and Execute a Simple PLINQ Query</span></span>
<span data-ttu-id="a96a3-103">En el ejemplo siguiente se muestra cómo crear una consulta Parallel LINQ; para ello, se utiliza el método de extensión <xref:System.Linq.ParallelEnumerable.AsParallel%2A> en la secuencia de origen y se ejecuta la consulta con el método <xref:System.Linq.ParallelEnumerable.ForAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="a96a3-103">The following example shows how to create a simple Parallel LINQ query by using the <xref:System.Linq.ParallelEnumerable.AsParallel%2A> extension method on the source sequence, and executing the query by using the <xref:System.Linq.ParallelEnumerable.ForAll%2A> method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a96a3-104">En esta documentación, se utilizan expresiones lambda para definir delegados en PLINQ.</span><span class="sxs-lookup"><span data-stu-id="a96a3-104">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="a96a3-105">Si no está familiarizado con las expresiones lambda de C# o Visual Basic, consulte [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md) (Expresiones lambda en PLINQ y TPL).</span><span class="sxs-lookup"><span data-stu-id="a96a3-105">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a96a3-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a96a3-106">Example</span></span>  
 [!code-csharp[PLINQ#11](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/create1.cs#11)]
 [!code-vb[PLINQ#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/create1.vb#11)]  
  
 <span data-ttu-id="a96a3-107">En este ejemplo se muestra el patrón básico para la creación y ejecución de cualquier consulta Parallel LINQ cuando el orden de la secuencia de resultado no importa; en general, las consultas desordenadas son más rápidas que las ordenadas.</span><span class="sxs-lookup"><span data-stu-id="a96a3-107">This example demonstrates the basic pattern for creating and executing any Parallel LINQ query when the ordering of the result sequence is not important; unordered queries are generally faster than ordered queries.</span></span> <span data-ttu-id="a96a3-108">La consulta crea particiones del origen, dividiéndolo en tareas que se ejecutan de forma asincrónica en varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="a96a3-108">The query partitions the source into tasks that are executed asynchronously on multiple threads.</span></span> <span data-ttu-id="a96a3-109">El orden en el que se completa cada tarea no depende solo de la cantidad de trabajo necesario para procesar los elementos de la partición, sino también de factores externos como, por ejemplo, el modo en que el sistema operativo programa cada uno de los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="a96a3-109">The order in which each task completes depends not only on the amount of work involved to process the elements in the partition, but also on external factors such as how the operating system schedules each thread.</span></span> <span data-ttu-id="a96a3-110">La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente.</span><span class="sxs-lookup"><span data-stu-id="a96a3-110">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="a96a3-111">Para más información sobre la velocidad, vea [Introducción a la velocidad en PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="a96a3-111">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span> <span data-ttu-id="a96a3-112">Para obtener más información sobre cómo mantener el orden de los elementos de una consulta, vea [Cómo: Controlar la ordenación en una consulta PLINQ](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md).</span><span class="sxs-lookup"><span data-stu-id="a96a3-112">For more information about how to preserve the ordering of elements in a query, see [How to: Control Ordering in a PLINQ Query](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a96a3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a96a3-113">See also</span></span>

- [<span data-ttu-id="a96a3-114">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="a96a3-114">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
