---
title: 'Cómo: Usar Parallel.Invoke para ejecutar operaciones paralelas'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- task parallelism in .NET
- parallel programming, task parallelism
ms.assetid: 6b3ecd79-dec9-4ce1-abf4-62e5392a59c6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0192e12c86b21eb126293bbd220e093b334768b
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2018
ms.locfileid: "48837068"
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a><span data-ttu-id="4b56a-102">Cómo: Usar Parallel.Invoke para ejecutar operaciones paralelas</span><span class="sxs-lookup"><span data-stu-id="4b56a-102">How to: Use Parallel.Invoke to Execute Parallel Operations</span></span>

<span data-ttu-id="4b56a-103">En este ejemplo se muestra cómo paralelizar operaciones usando <xref:System.Threading.Tasks.Parallel.Invoke%2A> en la biblioteca TPL.</span><span class="sxs-lookup"><span data-stu-id="4b56a-103">This example shows how to parallelize operations by using <xref:System.Threading.Tasks.Parallel.Invoke%2A> in the Task Parallel Library.</span></span> <span data-ttu-id="4b56a-104">Se realizan tres operaciones en un origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="4b56a-104">Three operations are performed on a shared data source.</span></span> <span data-ttu-id="4b56a-105">Como ninguna de ellas modifica el origen, se pueden ejecutar en paralelo de manera sencilla.</span><span class="sxs-lookup"><span data-stu-id="4b56a-105">Because none of the operations modifies the source, they can be executed in parallel in a straightforward manner.</span></span>

> [!NOTE]
> <span data-ttu-id="4b56a-106">En esta documentación, se utilizan expresiones lambda para definir delegados en la TPL.</span><span class="sxs-lookup"><span data-stu-id="4b56a-106">This documentation uses lambda expressions to define delegates in TPL.</span></span> <span data-ttu-id="4b56a-107">Si no está familiarizado con las expresiones lambda de C# o Visual Basic, consulte [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md) (Expresiones lambda en PLINQ y TPL).</span><span class="sxs-lookup"><span data-stu-id="4b56a-107">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>

## <a name="example"></a><span data-ttu-id="4b56a-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4b56a-108">Example</span></span>

[!code-csharp[TPL_Parallel#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallelinvoke.cs#06)]
[!code-vb[TPL_Parallel#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/parallelinvoke.vb#06)]

<span data-ttu-id="4b56a-109">Tenga en cuenta que con <xref:System.Threading.Tasks.Parallel.Invoke%2A>, solo tiene que expresar qué acciones quiere ejecutar simultáneamente y el tiempo de ejecución controla todos los detalles de programación de los subprocesos, incluido el ajuste automático del número de núcleos en el equipo host.</span><span class="sxs-lookup"><span data-stu-id="4b56a-109">Note that with <xref:System.Threading.Tasks.Parallel.Invoke%2A>, you simply express which actions you want to run concurrently, and the runtime handles all thread scheduling details, including scaling automatically to the number of cores on the host computer.</span></span>

<span data-ttu-id="4b56a-110">En este ejemplo se paralelizan las operaciones, no los datos.</span><span class="sxs-lookup"><span data-stu-id="4b56a-110">This example parallelizes the operations, not the data.</span></span> <span data-ttu-id="4b56a-111">Como método alternativo, puede paralelizar los consultas de LINQ mediante PLINQ y ejecutar las consultas de forma secuencial.</span><span class="sxs-lookup"><span data-stu-id="4b56a-111">As an alternate approach, you can parallelize the LINQ queries by using PLINQ and run the queries sequentially.</span></span> <span data-ttu-id="4b56a-112">También puede paralelizar los datos con PLINQ.</span><span class="sxs-lookup"><span data-stu-id="4b56a-112">Alternatively, you could parallelize the data by using PLINQ.</span></span> <span data-ttu-id="4b56a-113">Otra opción consiste en paralelizar las consultas y las tareas.</span><span class="sxs-lookup"><span data-stu-id="4b56a-113">Another option is to parallelize both the queries and the tasks.</span></span> <span data-ttu-id="4b56a-114">Aunque la sobrecarga resultante podría reducir el rendimiento en equipos host con relativamente pocos procesadores, se ajustaría mucho mejor en equipos con varios procesadores.</span><span class="sxs-lookup"><span data-stu-id="4b56a-114">Although the resulting overhead might degrade performance on host computers with relatively few processors, it would scale much better on computers with many processors.</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="4b56a-115">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="4b56a-115">Compile the Code</span></span>

<span data-ttu-id="4b56a-116">Copie y pegue el ejemplo completo en un proyecto de Microsoft Visual Studio y presione **F5**.</span><span class="sxs-lookup"><span data-stu-id="4b56a-116">Copy and paste the entire example into a Microsoft Visual Studio project and press **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b56a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b56a-117">See also</span></span>

- [<span data-ttu-id="4b56a-118">Programación en paralelo</span><span class="sxs-lookup"><span data-stu-id="4b56a-118">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)
- [<span data-ttu-id="4b56a-119">Cancelar una tarea y los elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4b56a-119">How to: Cancel a Task and Its Children</span></span>](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md)
- [<span data-ttu-id="4b56a-120">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="4b56a-120">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
