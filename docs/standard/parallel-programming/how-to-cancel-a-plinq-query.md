---
title: "Cómo: Cancelar una consulta PLINQ"
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
helpviewer_keywords:
- PLINQ queries, how to cancel
- cancellation, PLINQ
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d8031758462df45c030b8b75a3507f1bfb44bfd0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-plinq-query"></a><span data-ttu-id="8d39d-102">Cómo: Cancelar una consulta PLINQ</span><span class="sxs-lookup"><span data-stu-id="8d39d-102">How to: Cancel a PLINQ Query</span></span>
<span data-ttu-id="8d39d-103">Los ejemplos siguientes muestran dos mecanismos para cancelar una consulta PLINQ.</span><span class="sxs-lookup"><span data-stu-id="8d39d-103">The following examples show two ways to cancel a PLINQ query.</span></span> <span data-ttu-id="8d39d-104">El primer ejemplo muestra cómo cancelar una consulta que se compone principalmente de cruce seguro de datos.</span><span class="sxs-lookup"><span data-stu-id="8d39d-104">The first example shows how to cancel a query that consists mostly of data traversal.</span></span> <span data-ttu-id="8d39d-105">El segundo ejemplo muestra cómo cancelar una consulta que contenga una función de usuario que es cara.</span><span class="sxs-lookup"><span data-stu-id="8d39d-105">The second example shows how to cancel a query that contains a user function that is computationally expensive.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d39d-106">Cuando se habilita "Solo mi código", Visual Studio se interrumpe en la línea que produce la excepción y mostrar un mensaje de error "excepción no controlada por código de usuario".</span><span class="sxs-lookup"><span data-stu-id="8d39d-106">When "Just My Code" is enabled, Visual Studio will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="8d39d-107">Este error es benigno.</span><span class="sxs-lookup"><span data-stu-id="8d39d-107">This error is benign.</span></span> <span data-ttu-id="8d39d-108">Puede presionar F5 para continuar y ver el comportamiento de control de excepciones que se muestra en estos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="8d39d-108">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="8d39d-109">Para evitar que Visual Studio se interrumpa con el primer error, desactive la casilla «Solo mi código» en **herramientas, opciones, depuración, General**.</span><span class="sxs-lookup"><span data-stu-id="8d39d-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
>   
>  <span data-ttu-id="8d39d-110">La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente.</span><span class="sxs-lookup"><span data-stu-id="8d39d-110">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="8d39d-111">Para obtener más información acerca de la velocidad, consulte [Introducción a la velocidad en PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="8d39d-111">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d39d-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8d39d-112">Example</span></span>  
 [!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
 [!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]  
  
 <span data-ttu-id="8d39d-113">El marco PLINQ no revierte una sola <xref:System.OperationCanceledException> en un <xref:System.AggregateException?displayProperty=nameWithType>; el <xref:System.OperationCanceledException> debe controlarse en un bloque catch independiente.</span><span class="sxs-lookup"><span data-stu-id="8d39d-113">The PLINQ framework does not roll a single <xref:System.OperationCanceledException> into an <xref:System.AggregateException?displayProperty=nameWithType>; the <xref:System.OperationCanceledException> must be handled in a separate catch block.</span></span> <span data-ttu-id="8d39d-114">Si uno o varios de los delegados de usuario produce una OperationCanceledException(externalCT) (mediante el uso de una referencia externa <xref:System.Threading.CancellationToken?displayProperty=nameWithType>), pero ninguna otra excepción y la consulta se ha definido como `AsParallel().WithCancellation(externalCT)`, a continuación, PLINQ emitirá una única <xref:System.OperationCanceledException> (OperationCanceledException externalCT) en lugar de una <xref:System.AggregateException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8d39d-114">If one or more user delegates throws an OperationCanceledException(externalCT) (by using an external <xref:System.Threading.CancellationToken?displayProperty=nameWithType>) but no other exception, and the query was defined as `AsParallel().WithCancellation(externalCT)`, then PLINQ will issue a single <xref:System.OperationCanceledException> (externalCT) rather than an <xref:System.AggregateException?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8d39d-115">Sin embargo, si un usuario delegado inicia un <xref:System.OperationCanceledException>y otro delegado inicia otro tipo de excepción, ambas excepciones se propagará a un <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="8d39d-115">However, if one user delegate throws an <xref:System.OperationCanceledException>, and another delegate throws another exception type, then both exceptions will be rolled into an <xref:System.AggregateException>.</span></span>  
  
 <span data-ttu-id="8d39d-116">Las instrucciones generales sobre la cancelación es como sigue:</span><span class="sxs-lookup"><span data-stu-id="8d39d-116">The general guidance on cancellation is as follows:</span></span>  
  
1.  <span data-ttu-id="8d39d-117">Si lleva a cabo cancelación del delegado de usuario debe informar a PLINQ sobre la externa <xref:System.Threading.CancellationToken> y producir un <xref:System.OperationCanceledException>(OperationCanceledException externalCT).</span><span class="sxs-lookup"><span data-stu-id="8d39d-117">If you perform user-delegate cancellation you should inform PLINQ about the external <xref:System.Threading.CancellationToken> and throw an <xref:System.OperationCanceledException>(externalCT).</span></span>  
  
2.  <span data-ttu-id="8d39d-118">Si se produce la cancelación y se produce ninguna otra excepción, a continuación, debe controlar un <xref:System.OperationCanceledException> en lugar de un <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="8d39d-118">If cancellation occurs and no other exceptions are thrown, then you should handle an <xref:System.OperationCanceledException> rather than an <xref:System.AggregateException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d39d-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8d39d-119">Example</span></span>  
 <span data-ttu-id="8d39d-120">En el ejemplo siguiente se muestra cómo controlar la cancelación cuando se tiene una función cara en código de usuario.</span><span class="sxs-lookup"><span data-stu-id="8d39d-120">The following example shows how to handle cancellation when you have a computationally expensive function in user code.</span></span>  
  
 [!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
 [!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]  
  
 <span data-ttu-id="8d39d-121">Al controlar la cancelación en el código de usuario, no tiene que usar <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> en la definición de consulta.</span><span class="sxs-lookup"><span data-stu-id="8d39d-121">When you handle the cancellation in user code, you do not have to use <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> in the query definition.</span></span> <span data-ttu-id="8d39d-122">Sin embargo, se recomienda hacerlo porque <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> no tiene ningún efecto en el rendimiento de las consultas y permite la cancelación se ocuparán de operadores de consulta y el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="8d39d-122">However, we recommended that you do this because <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> has no effect on query performance and it enables the cancellation to be handled by query operators and your user code.</span></span>  
  
 <span data-ttu-id="8d39d-123">Con el fin de garantizar la capacidad de respuesta del sistema, le recomendamos que compruebe cancelación alrededor de una vez por cada milisegundo; Sin embargo, cualquier período que transcurre hasta 10 milisegundos se considera aceptable.</span><span class="sxs-lookup"><span data-stu-id="8d39d-123">In order to ensure system responsiveness, we recommend that you check for cancellation around once per millisecond; however, any period up to 10 milliseconds is considered acceptable.</span></span> <span data-ttu-id="8d39d-124">Esta frecuencia no debe tener un impacto negativo en el rendimiento del código.</span><span class="sxs-lookup"><span data-stu-id="8d39d-124">This frequency should not have a negative impact on your code's performance.</span></span>  
  
 <span data-ttu-id="8d39d-125">Cuando se elimina un enumerador, por ejemplo cuando el código sale un bucle foreach (For Each en Visual Basic) que está iterando los resultados de la consulta, a continuación, se cancela la consulta, pero se inicia ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="8d39d-125">When an enumerator is disposed, for example when code breaks out of a foreach (For Each in Visual Basic) loop that is iterating over query results, then the query is cancelled, but no exception is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d39d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d39d-126">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="8d39d-127">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="8d39d-127">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [<span data-ttu-id="8d39d-128">Cancelación en subprocesos administrados</span><span class="sxs-lookup"><span data-stu-id="8d39d-128">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
