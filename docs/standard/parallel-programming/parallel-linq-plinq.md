---
title: Parallel LINQ (PLINQ)
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- PLINQ, overview
ms.assetid: 3d4d0cd3-bde4-490b-99e7-f4e41be96455
ms.openlocfilehash: 1ea880c6403a5fc8b26ba67fe21dfce79c4683db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73140039"
---
# <a name="parallel-linq-plinq"></a><span data-ttu-id="1a4dc-102">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="1a4dc-102">Parallel LINQ (PLINQ)</span></span>
<span data-ttu-id="1a4dc-103">Parallel LINQ (PLINQ) es una implementación en paralelo de LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="1a4dc-103">Parallel LINQ (PLINQ) is a parallel implementation of LINQ to Objects.</span></span> <span data-ttu-id="1a4dc-104">PLINQ implementa el conjunto completo de operadores de consulta estándar de LINQ como métodos de extensión para el espacio de nombres <xref:System.Linq> y tiene operadores adicionales para las operaciones en paralelo.</span><span class="sxs-lookup"><span data-stu-id="1a4dc-104">PLINQ implements the full set of LINQ standard query operators as extension methods for the <xref:System.Linq> namespace and has additional operators for parallel operations.</span></span> <span data-ttu-id="1a4dc-105">PLINQ combina la simplicidad y legibilidad de la sintaxis de LINQ con la eficacia de la programación en paralelo.</span><span class="sxs-lookup"><span data-stu-id="1a4dc-105">PLINQ combines the simplicity and readability of LINQ syntax with the power of parallel programming.</span></span> <span data-ttu-id="1a4dc-106">Al igual que el código que tiene como destino la biblioteca TPL, PLINQ consulta la escala en el grado de simultaneidad según las funcionalidades del equipo host.</span><span class="sxs-lookup"><span data-stu-id="1a4dc-106">Just like code that targets the Task Parallel Library, PLINQ queries scale in the degree of concurrency based on the capabilities of the host computer.</span></span>  
  
 <span data-ttu-id="1a4dc-107">En muchos escenarios, PLINQ puede aumentar considerablemente la velocidad de las consultas de LINQ to Objects usando de manera más eficiente todos los núcleos disponibles en el equipo host.</span><span class="sxs-lookup"><span data-stu-id="1a4dc-107">In many scenarios, PLINQ can significantly increase the speed of LINQ to Objects queries by using all available cores on the host computer more efficiently.</span></span> <span data-ttu-id="1a4dc-108">Este mayor rendimiento aporta capacidad de procesamiento de alto rendimiento al escritorio.</span><span class="sxs-lookup"><span data-stu-id="1a4dc-108">This increased performance brings high-performance computing power onto the desktop.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1a4dc-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1a4dc-109">In This Section</span></span>  
 [<span data-ttu-id="1a4dc-110">Introducción a PLINQ</span><span class="sxs-lookup"><span data-stu-id="1a4dc-110">Introduction to PLINQ</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)  
  
 [<span data-ttu-id="1a4dc-111">Introducción a la velocidad en PLINQ</span><span class="sxs-lookup"><span data-stu-id="1a4dc-111">Understanding Speedup in PLINQ</span></span>](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)  
  
 [<span data-ttu-id="1a4dc-112">Conversación del orden en PLINQ</span><span class="sxs-lookup"><span data-stu-id="1a4dc-112">Order Preservation in PLINQ</span></span>](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md)  
  
 [<span data-ttu-id="1a4dc-113">Opciones de combinación en PLINQ</span><span class="sxs-lookup"><span data-stu-id="1a4dc-113">Merge Options in PLINQ</span></span>](../../../docs/standard/parallel-programming/merge-options-in-plinq.md)  
  
 [<span data-ttu-id="1a4dc-114">Creación y ejecución de una consulta PLINQ simple</span><span class="sxs-lookup"><span data-stu-id="1a4dc-114">How to: Create and Execute a Simple PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-create-and-execute-a-simple-plinq-query.md)  
  
 [<span data-ttu-id="1a4dc-115">Control de la ordenación en una consulta PLINQ</span><span class="sxs-lookup"><span data-stu-id="1a4dc-115">How to: Control Ordering in a PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md)  
  
 [<span data-ttu-id="1a4dc-116">Combinación de consultas LINQ en paralelo y secuenciales</span><span class="sxs-lookup"><span data-stu-id="1a4dc-116">How to: Combine Parallel and Sequential LINQ Queries</span></span>](../../../docs/standard/parallel-programming/how-to-combine-parallel-and-sequential-linq-queries.md)  
  
 [<span data-ttu-id="1a4dc-117">Control de excepciones en una consulta PLINQ</span><span class="sxs-lookup"><span data-stu-id="1a4dc-117">How to: Handle Exceptions in a PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md)  
  
 [<span data-ttu-id="1a4dc-118">Cancelación de una consulta PLINQ</span><span class="sxs-lookup"><span data-stu-id="1a4dc-118">How to: Cancel a PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-cancel-a-plinq-query.md)  
  
 [<span data-ttu-id="1a4dc-119">Escritura de una función de agregado personalizada de PLINQ</span><span class="sxs-lookup"><span data-stu-id="1a4dc-119">How to: Write a Custom PLINQ Aggregate Function</span></span>](../../../docs/standard/parallel-programming/how-to-write-a-custom-plinq-aggregate-function.md)  
  
 [<span data-ttu-id="1a4dc-120">Especificación del modo de ejecución en PLINQ</span><span class="sxs-lookup"><span data-stu-id="1a4dc-120">How to: Specify the Execution Mode in PLINQ</span></span>](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md)  
  
 [<span data-ttu-id="1a4dc-121">Especificación de opciones de combinación en PLINQ</span><span class="sxs-lookup"><span data-stu-id="1a4dc-121">How to: Specify Merge Options in PLINQ</span></span>](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)  
  
 [<span data-ttu-id="1a4dc-122">Iteración de directorios de archivos con PLINQ</span><span class="sxs-lookup"><span data-stu-id="1a4dc-122">How to: Iterate File Directories with PLINQ</span></span>](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md)  
  
 [<span data-ttu-id="1a4dc-123">Medición del rendimiento de consultas PLINQ</span><span class="sxs-lookup"><span data-stu-id="1a4dc-123">How to: Measure PLINQ Query Performance</span></span>](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md)  
  
 [<span data-ttu-id="1a4dc-124">Ejemplo de datos de PLINQ</span><span class="sxs-lookup"><span data-stu-id="1a4dc-124">PLINQ Data Sample</span></span>](../../../docs/standard/parallel-programming/plinq-data-sample.md)  
  
## <a name="see-also"></a><span data-ttu-id="1a4dc-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a4dc-125">See also</span></span>

- <xref:System.Linq.ParallelEnumerable>
- [<span data-ttu-id="1a4dc-126">Programación en paralelo</span><span class="sxs-lookup"><span data-stu-id="1a4dc-126">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)
- [<span data-ttu-id="1a4dc-127">Language Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="1a4dc-127">Language-Integrated Query (LINQ) - C#</span></span>](../../csharp/programming-guide/concepts/linq/index.md)  
- [<span data-ttu-id="1a4dc-128">Language Integrated Query (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a4dc-128">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../visual-basic/programming-guide/concepts/linq/index.md)  
