---
title: Procedimiento para cancelar una consulta PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to cancel
- cancellation, PLINQ
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
ms.openlocfilehash: 312c71b787ac7b4aa092f1517d2ed5af314a22e4
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635876"
---
# <a name="how-to-cancel-a-plinq-query"></a><span data-ttu-id="2ec46-102">Procedimiento para cancelar una consulta PLINQ</span><span class="sxs-lookup"><span data-stu-id="2ec46-102">How to: Cancel a PLINQ Query</span></span>
<span data-ttu-id="2ec46-103">En los siguientes ejemplos se muestran dos formas de cancelar una consulta PLINQ.</span><span class="sxs-lookup"><span data-stu-id="2ec46-103">The following examples show two ways to cancel a PLINQ query.</span></span> <span data-ttu-id="2ec46-104">El primer ejemplo muestra cómo cancelar una consulta que se compone principalmente de un cruce seguro de datos.</span><span class="sxs-lookup"><span data-stu-id="2ec46-104">The first example shows how to cancel a query that consists mostly of data traversal.</span></span> <span data-ttu-id="2ec46-105">El segundo ejemplo muestra cómo cancelar una consulta que contiene una función de usuario que es cara desde el punto de vista computacional.</span><span class="sxs-lookup"><span data-stu-id="2ec46-105">The second example shows how to cancel a query that contains a user function that is computationally expensive.</span></span>

> [!NOTE]
> <span data-ttu-id="2ec46-106">Cuando está habilitada la opción "Solo mi código", Visual Studio se interrumpe en la línea que produce la excepción y muestra el mensaje de error "Excepción no controlada por el código de usuario".</span><span class="sxs-lookup"><span data-stu-id="2ec46-106">When "Just My Code" is enabled, Visual Studio will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="2ec46-107">Este error es benigno.</span><span class="sxs-lookup"><span data-stu-id="2ec46-107">This error is benign.</span></span> <span data-ttu-id="2ec46-108">Puede presionar F5 para continuar y ver el comportamiento de control de excepciones que se muestra en estos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="2ec46-108">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="2ec46-109">Para evitar que Visual Studio se interrumpa con el primer error, desactive la casilla "Solo mi código" en **Herramientas, Opciones, Depurar, General**.</span><span class="sxs-lookup"><span data-stu-id="2ec46-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>
>
> <span data-ttu-id="2ec46-110">La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente.</span><span class="sxs-lookup"><span data-stu-id="2ec46-110">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="2ec46-111">Para más información sobre la velocidad, vea [Introducción a la velocidad en PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="2ec46-111">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>

## <a name="example"></a><span data-ttu-id="2ec46-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2ec46-112">Example</span></span>

[!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
[!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]

<span data-ttu-id="2ec46-113">El marco PLINQ no revierte una clase <xref:System.OperationCanceledException> única en <xref:System.AggregateException?displayProperty=nameWithType>; <xref:System.OperationCanceledException> debe controlarse en un bloque de filtrado independiente.</span><span class="sxs-lookup"><span data-stu-id="2ec46-113">The PLINQ framework does not roll a single <xref:System.OperationCanceledException> into an <xref:System.AggregateException?displayProperty=nameWithType>; the <xref:System.OperationCanceledException> must be handled in a separate catch block.</span></span> <span data-ttu-id="2ec46-114">Si uno o varios de los delegados de usuario produce una clase OperationCanceledException(externalCT) (mediante el uso de una referencia externa <xref:System.Threading.CancellationToken?displayProperty=nameWithType>), pero ninguna otra excepción, y la consulta se ha definido como `AsParallel().WithCancellation(externalCT)`, a continuación, PLINQ emitirá una única clase <xref:System.OperationCanceledException> (externalCT) en lugar de una clase <xref:System.AggregateException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2ec46-114">If one or more user delegates throws an OperationCanceledException(externalCT) (by using an external <xref:System.Threading.CancellationToken?displayProperty=nameWithType>) but no other exception, and the query was defined as `AsParallel().WithCancellation(externalCT)`, then PLINQ will issue a single <xref:System.OperationCanceledException> (externalCT) rather than an <xref:System.AggregateException?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2ec46-115">Sin embargo, si un usuario delegado inicia una clase <xref:System.OperationCanceledException> y otro delegado inicia otro tipo de excepción, ambas excepciones se propagarán a <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="2ec46-115">However, if one user delegate throws an <xref:System.OperationCanceledException>, and another delegate throws another exception type, then both exceptions will be rolled into an <xref:System.AggregateException>.</span></span>

<span data-ttu-id="2ec46-116">Las instrucciones generales sobre la cancelación son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="2ec46-116">The general guidance on cancellation is as follows:</span></span>

1. <span data-ttu-id="2ec46-117">Si realiza la cancelación de un delegado de usuario, debe informar a PLINQ sobre la clase externa <xref:System.Threading.CancellationToken> e iniciar <xref:System.OperationCanceledException> (externalCT).</span><span class="sxs-lookup"><span data-stu-id="2ec46-117">If you perform user-delegate cancellation, you should inform PLINQ about the external <xref:System.Threading.CancellationToken> and throw an <xref:System.OperationCanceledException>(externalCT).</span></span>

2. <span data-ttu-id="2ec46-118">Si se produce la cancelación y no se inicia ninguna otra excepción, controle un elemento <xref:System.OperationCanceledException> en lugar de uno <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="2ec46-118">If cancellation occurs and no other exceptions are thrown, then handle an <xref:System.OperationCanceledException> rather than an <xref:System.AggregateException>.</span></span>

## <a name="example"></a><span data-ttu-id="2ec46-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2ec46-119">Example</span></span>

<span data-ttu-id="2ec46-120">En el ejemplo siguiente se muestra cómo controlar la cancelación cuando se tiene una función cara desde el punto de vista computacional en el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="2ec46-120">The following example shows how to handle cancellation when you have a computationally expensive function in user code.</span></span>

[!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
[!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]

<span data-ttu-id="2ec46-121">Al controlar la cancelación en el código de usuario, no tiene que usar <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> en la definición de consulta.</span><span class="sxs-lookup"><span data-stu-id="2ec46-121">When you handle the cancellation in user code, you do not have to use <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> in the query definition.</span></span> <span data-ttu-id="2ec46-122">Sin embargo, se recomienda el uso de <xref:System.Linq.ParallelEnumerable.WithCancellation%2A>, porque <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> no tiene ningún efecto en el rendimiento de las consultas y permite que los operadores de consulta y el código de usuario controlen la cancelación.</span><span class="sxs-lookup"><span data-stu-id="2ec46-122">However, we recommended that you do use <xref:System.Linq.ParallelEnumerable.WithCancellation%2A>, because <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> has no effect on query performance and it enables the cancellation to be handled by query operators and your user code.</span></span>

<span data-ttu-id="2ec46-123">Con el fin de garantizar la capacidad de respuesta del sistema, se recomienda que compruebe la cancelación una vez por cada milisegundo; sin embargo, cualquier período que transcurre hasta diez milisegundos se considera aceptable.</span><span class="sxs-lookup"><span data-stu-id="2ec46-123">In order to ensure system responsiveness, we recommend that you check for cancellation around once per millisecond; however, any period up to 10 milliseconds is considered acceptable.</span></span> <span data-ttu-id="2ec46-124">Esta frecuencia no debe tener un impacto negativo en el rendimiento del código.</span><span class="sxs-lookup"><span data-stu-id="2ec46-124">This frequency should not have a negative impact on your code's performance.</span></span>

<span data-ttu-id="2ec46-125">Cuando se elimina un enumerador, por ejemplo cuando el código desencadena un bucle foreach (For Each en Visual Basic) que está iterando en los resultados de la consulta, se cancela la consulta, pero no se inicia ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="2ec46-125">When an enumerator is disposed, for example when code breaks out of a foreach (For Each in Visual Basic) loop that is iterating over query results, then the query is canceled, but no exception is thrown.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ec46-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ec46-126">See also</span></span>

- <xref:System.Linq.ParallelEnumerable>
- [<span data-ttu-id="2ec46-127">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="2ec46-127">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
- [<span data-ttu-id="2ec46-128">Cancelación en subprocesos administrados</span><span class="sxs-lookup"><span data-stu-id="2ec46-128">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
