---
title: 'Cómo: Escribir un bucle Parallel.ForEach simple'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
caps.latest.revision: 19
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 90b900bf98ab664e0fce5c70573f01e044d70803
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a><span data-ttu-id="72917-102">Cómo: Escribir un bucle Parallel.ForEach simple</span><span class="sxs-lookup"><span data-stu-id="72917-102">How to: Write a Simple Parallel.ForEach Loop</span></span>
<span data-ttu-id="72917-103">Este ejemplo muestra cómo utilizar un bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> para habilitar el paralelismo de datos sobre cualquier origen de datos <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="72917-103">This example shows how to use a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop to enable data parallelism over any <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> data source.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72917-104">En esta documentación, se utilizan expresiones lambda para definir delegados en PLINQ.</span><span class="sxs-lookup"><span data-stu-id="72917-104">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="72917-105">Si no está familiarizado con las expresiones lambda de C# o Visual Basic, consulte [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md) (Expresiones lambda en PLINQ y TPL).</span><span class="sxs-lookup"><span data-stu-id="72917-105">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="72917-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="72917-106">Example</span></span>  
 [!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
 [!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]  
  
 <span data-ttu-id="72917-107">Un bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A> funciona como un bucle <xref:System.Threading.Tasks.Parallel.For%2A>.</span><span class="sxs-lookup"><span data-stu-id="72917-107">A <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop works like a <xref:System.Threading.Tasks.Parallel.For%2A> loop.</span></span> <span data-ttu-id="72917-108">Se divide la colección de origen y se programa el trabajo en varios subprocesos según el entorno del sistema.</span><span class="sxs-lookup"><span data-stu-id="72917-108">The source collection is partitioned and the work is scheduled on multiple threads based on the system environment.</span></span> <span data-ttu-id="72917-109">Mientras más procesadores haya en el sistema, más rápido se ejecutará el método paralelo.</span><span class="sxs-lookup"><span data-stu-id="72917-109">The more processors on the system, the faster the parallel method runs.</span></span> <span data-ttu-id="72917-110">Para algunas colecciones de origen, un bucle secuencial puede ser más rápido, dependiendo del tamaño del origen y del tipo de trabajo que se realiza.</span><span class="sxs-lookup"><span data-stu-id="72917-110">For some source collections, a sequential loop may be faster, depending on the size of the source, and the kind of work being performed.</span></span> <span data-ttu-id="72917-111">Para más información sobre el rendimiento, vea [Problemas potenciales en el paralelismo de datos y tareas](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md).</span><span class="sxs-lookup"><span data-stu-id="72917-111">For more information about performance, see [Potential Pitfalls in Data and Task Parallelism](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)</span></span>  
  
 <span data-ttu-id="72917-112">Para más información sobre los bucles paralelos, vea [Cómo: Escribir un bucle Parallel.For simple](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).</span><span class="sxs-lookup"><span data-stu-id="72917-112">For more information about parallel loops, see [How to: Write a Simple Parallel.For Loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).</span></span>  
  
 <span data-ttu-id="72917-113">Para usar <xref:System.Threading.Tasks.Parallel.ForEach%2A> con una colección no genérica, puede usar el método de extensión <xref:System.Linq.Enumerable.Cast%2A> para convertir la colección en una colección genérica, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="72917-113">To use <xref:System.Threading.Tasks.Parallel.ForEach%2A> with a non-generic collection, you can use the <xref:System.Linq.Enumerable.Cast%2A> extension method to convert the collection to a generic collection, as shown in the following example:</span></span>  
  
 [!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
 [!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]  
  
 <span data-ttu-id="72917-114">También puede utilizar Parallel LINQ (PLINQ) para paralelizar el procesamiento de orígenes de datos <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="72917-114">You can also use Parallel LINQ (PLINQ) to parallelize processing of <xref:System.Collections.Generic.IEnumerable%601> data sources.</span></span> <span data-ttu-id="72917-115">PLINQ permite usar la sintaxis de consulta declarativa para expresar el comportamiento del bucle.</span><span class="sxs-lookup"><span data-stu-id="72917-115">PLINQ enables you to use declarative query syntax to express the loop behavior.</span></span> <span data-ttu-id="72917-116">Para más información, consulte [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="72917-116">For more information, see [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="72917-117">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="72917-117">Compiling the Code</span></span>  
  
-   <span data-ttu-id="72917-118">Copie y pegue este código en un proyecto de aplicación de consola de Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="72917-118">Copy and paste this code into a Visual Studio 2010 Console Application project.</span></span>  
  
-   <span data-ttu-id="72917-119">Adición de una referencia a System.Drawing.dll</span><span class="sxs-lookup"><span data-stu-id="72917-119">Add a reference to System.Drawing.dll</span></span>  
  
-   <span data-ttu-id="72917-120">Presione F5.</span><span class="sxs-lookup"><span data-stu-id="72917-120">Press F5</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72917-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="72917-121">See Also</span></span>  
 <span data-ttu-id="72917-122">[Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md) (Paralelismo de datos)</span><span class="sxs-lookup"><span data-stu-id="72917-122">[Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)</span></span>  
 [<span data-ttu-id="72917-123">Programación en paralelo</span><span class="sxs-lookup"><span data-stu-id="72917-123">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 [<span data-ttu-id="72917-124">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="72917-124">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
