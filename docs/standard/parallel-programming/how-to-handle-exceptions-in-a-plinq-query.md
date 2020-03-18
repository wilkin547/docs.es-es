---
title: 'Cómo: Controlar excepciones en una consulta PLINQ'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to handle exceptions
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
ms.openlocfilehash: 3645f5dc470ef53710aa7f4c78c60431fb27ecfa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73123091"
---
# <a name="how-to-handle-exceptions-in-a-plinq-query"></a><span data-ttu-id="76cc6-102">Cómo: Controlar excepciones en una consulta PLINQ</span><span class="sxs-lookup"><span data-stu-id="76cc6-102">How to: Handle Exceptions in a PLINQ Query</span></span>

<span data-ttu-id="76cc6-103">El primer ejemplo de este tema muestra cómo controlar la clase <xref:System.AggregateException?displayProperty=nameWithType> que se puede iniciar desde una consulta PLINQ cuando se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="76cc6-103">The first example in this topic shows how to handle the <xref:System.AggregateException?displayProperty=nameWithType> that can be thrown from a PLINQ query when it executes.</span></span> <span data-ttu-id="76cc6-104">El segundo ejemplo muestra cómo colocar bloques try-catch dentro de los delegados, lo más cerca posible de donde se producirá la excepción.</span><span class="sxs-lookup"><span data-stu-id="76cc6-104">The second example shows how to put try-catch blocks within delegates, as close as possible to where the exception will be thrown.</span></span> <span data-ttu-id="76cc6-105">De este modo, se pueden detectar en cuanto se producen y posiblemente continuar con la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="76cc6-105">In this way, you can catch them as soon as they occur and possibly continue query execution.</span></span> <span data-ttu-id="76cc6-106">Cuando las excepciones pueden propagarse de nuevo al subproceso de unión, es posible que una consulta continúe procesando algunos elementos después de que se haya producido la excepción.</span><span class="sxs-lookup"><span data-stu-id="76cc6-106">When exceptions are allowed to bubble up back to the joining thread, then it is possible that a query may continue to process some items after the exception is raised.</span></span>

<span data-ttu-id="76cc6-107">En algunos casos, cuando PLINQ vuelve a realizar la ejecución por secuencias y cuando se produce una excepción, esta puede propagarse directamente y no ajustarse en una excepción <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="76cc6-107">In some cases when PLINQ falls back to sequential execution, and an exception occurs, the exception may be propagated directly, and not wrapped in an <xref:System.AggregateException>.</span></span> <span data-ttu-id="76cc6-108">Además, las excepciones <xref:System.Threading.ThreadAbortException> siempre se propagan directamente.</span><span class="sxs-lookup"><span data-stu-id="76cc6-108">Also, <xref:System.Threading.ThreadAbortException>s are always propagated directly.</span></span>

> [!NOTE]
> <span data-ttu-id="76cc6-109">Cuando está habilitada la opción "Solo mi código", Visual Studio se interrumpe en la línea que produce la excepción y muestra el mensaje de error "Excepción no controlada por el código de usuario".</span><span class="sxs-lookup"><span data-stu-id="76cc6-109">When "Just My Code" is enabled, Visual Studio will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="76cc6-110">Este error es benigno.</span><span class="sxs-lookup"><span data-stu-id="76cc6-110">This error is benign.</span></span> <span data-ttu-id="76cc6-111">Puede presionar F5 para continuar y ver el comportamiento de control de excepciones que se muestra en estos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="76cc6-111">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="76cc6-112">Para evitar que Visual Studio se interrumpa con el primer error, desactive la casilla "Solo mi código" en **Herramientas, Opciones, Depurar, General**.</span><span class="sxs-lookup"><span data-stu-id="76cc6-112">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>
>
> <span data-ttu-id="76cc6-113">La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente.</span><span class="sxs-lookup"><span data-stu-id="76cc6-113">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="76cc6-114">Para más información sobre la velocidad, vea [Introducción a la velocidad en PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="76cc6-114">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>

## <a name="example"></a><span data-ttu-id="76cc6-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="76cc6-115">Example</span></span>

<span data-ttu-id="76cc6-116">Este ejemplo muestra cómo colocar los bloques try-catch alrededor del código que ejecuta la consulta para detectar cualquier excepción <xref:System.AggregateException?displayProperty=nameWithType> que se produzca.</span><span class="sxs-lookup"><span data-stu-id="76cc6-116">This example shows how to put the try-catch blocks around the code that executes the query to catch any <xref:System.AggregateException?displayProperty=nameWithType>s that are thrown.</span></span>

[!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
[!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]

<span data-ttu-id="76cc6-117">En este ejemplo, la consulta no puede continuar después de que se produce la excepción.</span><span class="sxs-lookup"><span data-stu-id="76cc6-117">In this example, the query cannot continue after the exception is thrown.</span></span> <span data-ttu-id="76cc6-118">En el momento en que el código de la aplicación detecta la excepción, PLINQ ya ha detenido la consulta en todos los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="76cc6-118">By the time your application code catches the exception, PLINQ has already stopped the query on all threads.</span></span>

## <a name="example"></a><span data-ttu-id="76cc6-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="76cc6-119">Example</span></span>

<span data-ttu-id="76cc6-120">En el ejemplo siguiente se muestra cómo colocar un bloque try-catch en un delegado para que sea posible detectar una excepción y continuar con la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="76cc6-120">The following example shows how to put a try-catch block in a delegate to make it possible to catch an exception and continue with the query execution.</span></span>

[!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
[!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]

## <a name="compiling-the-code"></a><span data-ttu-id="76cc6-121">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="76cc6-121">Compiling the Code</span></span>

- <span data-ttu-id="76cc6-122">Para compilar y ejecutar estos ejemplos, cópielos en el ejemplo de datos de PLINQ y llame al método desde Main.</span><span class="sxs-lookup"><span data-stu-id="76cc6-122">To compile and run these examples, copy them into the PLINQ Data Sample example and call the method from Main.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="76cc6-123">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="76cc6-123">Robust Programming</span></span>

<span data-ttu-id="76cc6-124">No se detecta ninguna excepción a menos que sepa cómo controlarla para que no se dañe el estado del programa.</span><span class="sxs-lookup"><span data-stu-id="76cc6-124">Do not catch an exception unless you know how to handle it so that you do not corrupt the state of your program.</span></span>

## <a name="see-also"></a><span data-ttu-id="76cc6-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="76cc6-125">See also</span></span>

- <xref:System.Linq.ParallelEnumerable>
- [<span data-ttu-id="76cc6-126">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="76cc6-126">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
