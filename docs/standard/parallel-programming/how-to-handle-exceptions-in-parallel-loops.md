---
title: Procedimiento para controlar excepciones en bucles paralelos
description: Aprenda a controlar excepciones en bucles paralelos en .NET. Vea un ejemplo de cómo ajustar todas las excepciones del bucle en System.AggregateException.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to handle exceptions
ms.assetid: 512f0d5a-4636-4875-b766-88f20044f143
ms.openlocfilehash: e8478f27b21b9b9dbf85d68f766c24aa5b9cf600
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825759"
---
# <a name="how-to-handle-exceptions-in-parallel-loops"></a><span data-ttu-id="04b09-104">Procedimiento para controlar excepciones en bucles paralelos</span><span class="sxs-lookup"><span data-stu-id="04b09-104">How to: Handle Exceptions in Parallel Loops</span></span>
<span data-ttu-id="04b09-105">Las sobrecargas <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType><xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> no tienen ningún mecanismo especial para controlar las excepciones que puedan iniciarse.</span><span class="sxs-lookup"><span data-stu-id="04b09-105">The <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> overloads do not have any special mechanism to handle exceptions that might be thrown.</span></span> <span data-ttu-id="04b09-106">En este sentido, se asemejan a bucles `for` y `foreach` normales (`For` y `For Each` en Visual Basic). Una excepción no controlada hace que el bucle termine en cuanto finalicen todas las iteraciones que se estén ejecutando.</span><span class="sxs-lookup"><span data-stu-id="04b09-106">In this respect, they resemble regular `for` and `foreach` loops (`For` and `For Each` in Visual Basic); an unhandled exception causes the loop to terminate as soon as all currently running iterations finish.</span></span>
  
 <span data-ttu-id="04b09-107">Cuando agregue su propia lógica de control de excepciones a los bucles paralelos, tenga en cuenta la posibilidad de que se inicien excepciones similares en varios subprocesos al mismo tiempo y la opción de que una excepción iniciada en un subproceso puede hacer que se inicie otra excepción en otro subproceso.</span><span class="sxs-lookup"><span data-stu-id="04b09-107">When you add your own exception-handling logic to parallel loops, handle the case in which similar exceptions might be thrown on multiple threads concurrently, and the case in which an exception thrown on one thread causes another exception to be thrown on another thread.</span></span> <span data-ttu-id="04b09-108">Puede controlar ambos casos ajustando todas las excepciones del bucle en <xref:System.AggregateException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="04b09-108">You can handle both cases by wrapping all exceptions from the loop in a <xref:System.AggregateException?displayProperty=nameWithType>.</span></span> <span data-ttu-id="04b09-109">En el ejemplo siguiente, se muestra un posible enfoque.</span><span class="sxs-lookup"><span data-stu-id="04b09-109">The following example shows one possible approach.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="04b09-110">Cuando está habilitada la opción "Solo mi código", en algunos casos, Visual Studio se interrumpe en la línea que produce la excepción y muestra el mensaje de error "Excepción no controlada por el código de usuario".</span><span class="sxs-lookup"><span data-stu-id="04b09-110">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="04b09-111">Este error es benigno.</span><span class="sxs-lookup"><span data-stu-id="04b09-111">This error is benign.</span></span> <span data-ttu-id="04b09-112">Puede presionar F5 para continuar y ver el comportamiento de control de excepciones que se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="04b09-112">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the example below.</span></span> <span data-ttu-id="04b09-113">Para evitar que Visual Studio se interrumpa con el primer error, desactive la casilla "Solo mi código" en **Herramientas, Opciones, Depurar, General**.</span><span class="sxs-lookup"><span data-stu-id="04b09-113">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04b09-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04b09-114">Example</span></span>  
 <span data-ttu-id="04b09-115">En este ejemplo, se detectan todas las excepciones y, a continuación, se ajusta en un <xref:System.AggregateException?displayProperty=nameWithType> que se produce.</span><span class="sxs-lookup"><span data-stu-id="04b09-115">In this example, all exceptions are caught and then wrapped in an <xref:System.AggregateException?displayProperty=nameWithType> which is thrown.</span></span> <span data-ttu-id="04b09-116">El llamador puede decidir qué excepciones se deben administrar.</span><span class="sxs-lookup"><span data-stu-id="04b09-116">The caller can decide which exceptions to handle.</span></span>  
  
 [!code-csharp[TPL_Exceptions#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#08)]
 [!code-vb[TPL_Exceptions#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionsinloops.vb#08)]  
  
## <a name="see-also"></a><span data-ttu-id="04b09-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="04b09-117">See also</span></span>

- [<span data-ttu-id="04b09-118">Paralelismo de datos</span><span class="sxs-lookup"><span data-stu-id="04b09-118">Data Parallelism</span></span>](data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="04b09-119">Expresiones lambda en PLINQ y TPL</span><span class="sxs-lookup"><span data-stu-id="04b09-119">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
