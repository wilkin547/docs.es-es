---
title: Procedimiento para crear y ejecutar una consulta PLINQ simple
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create
ms.assetid: 983b4213-bddd-4a44-9262-cbe59186df4c
ms.openlocfilehash: a9c044254423d0f9d266539c728a6604f562e97d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290011"
---
# <a name="how-to-create-and-execute-a-simple-plinq-query"></a><span data-ttu-id="c6d4b-102">Procedimiento para crear y ejecutar una consulta PLINQ simple</span><span class="sxs-lookup"><span data-stu-id="c6d4b-102">How to: Create and Execute a Simple PLINQ Query</span></span>

<span data-ttu-id="c6d4b-103">En el ejemplo de este artículo se muestra cómo crear una consulta sencilla de Parallel Language Integrated Query (LINQ); para ello, se utiliza el método de extensión <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=nameWithType> en la secuencia de origen y se ejecuta la consulta con el método <xref:System.Linq.ParallelEnumerable.ForAll%2A?displayProperty=nameWithTyp>.</span><span class="sxs-lookup"><span data-stu-id="c6d4b-103">The example in this article shows how to create a simple Parallel Language Integrated Query (LINQ) query by using the <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=nameWithType> extension method on the source sequence and executing the query by using the <xref:System.Linq.ParallelEnumerable.ForAll%2A?displayProperty=nameWithTyp> method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c6d4b-104">En esta documentación, se utilizan expresiones lambda para definir delegados en PLINQ.</span><span class="sxs-lookup"><span data-stu-id="c6d4b-104">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="c6d4b-105">Si no está familiarizado con las expresiones lambda de C# o Visual Basic, consulte [Expresiones lambda en PLINQ y TPL](lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="c6d4b-105">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](lambda-expressions-in-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6d4b-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6d4b-106">Example</span></span>  
 [!code-csharp[PLINQ#11](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/create1.cs#11)]
 [!code-vb[PLINQ#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/create1.vb#11)]  
  
 <span data-ttu-id="c6d4b-107">En este ejemplo se muestra el patrón básico para la creación y ejecución de cualquier consulta Parallel LINQ cuando el orden de la secuencia de resultados no importa.</span><span class="sxs-lookup"><span data-stu-id="c6d4b-107">This example demonstrates the basic pattern for creating and executing any Parallel LINQ query when the ordering of the result sequence is not important.</span></span> <span data-ttu-id="c6d4b-108">Por lo general, las consultas desordenadas son más rápidas que las ordenadas.</span><span class="sxs-lookup"><span data-stu-id="c6d4b-108">Unordered queries are generally faster than ordered queries.</span></span> <span data-ttu-id="c6d4b-109">La consulta crea particiones del origen, dividiéndolo en tareas que se ejecutan de forma asincrónica en varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="c6d4b-109">The query partitions the source into tasks that are executed asynchronously on multiple threads.</span></span> <span data-ttu-id="c6d4b-110">El orden en el que se completa cada tarea no depende solo de la cantidad de trabajo necesario para procesar los elementos de la partición, sino también de factores externos como, por ejemplo, el modo en que el sistema operativo programa cada uno de los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="c6d4b-110">The order in which each task completes depends not only on the amount of work involved to process the elements in the partition, but also on external factors such as how the operating system schedules each thread.</span></span> <span data-ttu-id="c6d4b-111">La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente.</span><span class="sxs-lookup"><span data-stu-id="c6d4b-111">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="c6d4b-112">Para más información sobre la velocidad, vea [Introducción a la velocidad en PLINQ](understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="c6d4b-112">For more information about speedup, see [Understanding Speedup in PLINQ](understanding-speedup-in-plinq.md).</span></span> <span data-ttu-id="c6d4b-113">Para obtener más información sobre cómo mantener el orden de los elementos de una consulta, vea [Procedimiento para controlar la ordenación en una consulta PLINQ](how-to-control-ordering-in-a-plinq-query.md).</span><span class="sxs-lookup"><span data-stu-id="c6d4b-113">For more information about how to preserve the ordering of elements in a query, see [How to: Control Ordering in a PLINQ Query](how-to-control-ordering-in-a-plinq-query.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6d4b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6d4b-114">See also</span></span>

- [<span data-ttu-id="c6d4b-115">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="c6d4b-115">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
