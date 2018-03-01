---
title: "Cómo: Controlar excepciones en bucles paralelos"
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
- parallel loops, how to handle exceptions
ms.assetid: 512f0d5a-4636-4875-b766-88f20044f143
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f6df28a019c2a21cc6ef94367553e0e5eaa1ad30
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-handle-exceptions-in-parallel-loops"></a><span data-ttu-id="44920-102">Cómo: Controlar excepciones en bucles paralelos</span><span class="sxs-lookup"><span data-stu-id="44920-102">How to: Handle Exceptions in Parallel Loops</span></span>
<span data-ttu-id="44920-103">Las sobrecargas <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> no tienen ningún mecanismo especial para controlar las excepciones que puedan iniciarse.</span><span class="sxs-lookup"><span data-stu-id="44920-103">The <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> overloads do not have any special mechanism to handle exceptions that might be thrown.</span></span> <span data-ttu-id="44920-104">En este sentido, se asemejan a bucles `for` y `foreach` normales (`For` y `For Each` en Visual Basic). Una excepción no controlada hace que el bucle finalice inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="44920-104">In this respect, they resemble regular `for` and `foreach` loops (`For` and `For Each` in Visual Basic); an unhandled exception causes the loop to terminate immediately.</span></span>  
  
 <span data-ttu-id="44920-105">Cuando agregue su propia lógica de control de excepciones a los bucles paralelos, tenga en cuenta la posibilidad de que se inicien excepciones similares en varios subprocesos al mismo tiempo y la opción de que una excepción iniciada en un subproceso puede hacer que se inicie otra excepción en otro subproceso.</span><span class="sxs-lookup"><span data-stu-id="44920-105">When you add your own exception-handling logic to parallel loops, handle the case in which similar exceptions might be thrown on multiple threads concurrently, and the case in which an exception thrown on one thread causes another exception to be thrown on another thread.</span></span> <span data-ttu-id="44920-106">Puede controlar ambos casos ajustando todas las excepciones del bucle en <xref:System.AggregateException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="44920-106">You can handle both cases by wrapping all exceptions from the loop in a <xref:System.AggregateException?displayProperty=nameWithType>.</span></span> <span data-ttu-id="44920-107">En el ejemplo siguiente, se muestra un posible enfoque.</span><span class="sxs-lookup"><span data-stu-id="44920-107">The following example shows one possible approach.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44920-108">Cuando está habilitada la opción "Solo mi código", en algunos casos, Visual Studio se interrumpe en la línea que produce la excepción y muestra el mensaje de error "Excepción no controlada por el código de usuario".</span><span class="sxs-lookup"><span data-stu-id="44920-108">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="44920-109">Este error es benigno.</span><span class="sxs-lookup"><span data-stu-id="44920-109">This error is benign.</span></span> <span data-ttu-id="44920-110">Puede presionar F5 para continuar y ver el comportamiento de control de excepciones que se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="44920-110">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the example below.</span></span> <span data-ttu-id="44920-111">Para evitar que Visual Studio se interrumpa con el primer error, desactive la casilla "Solo mi código" en **Herramientas, Opciones, Depurar, General**.</span><span class="sxs-lookup"><span data-stu-id="44920-111">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44920-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="44920-112">Example</span></span>  
 <span data-ttu-id="44920-113">En este ejemplo, se detectan todas las excepciones y, a continuación, se ajusta en un <xref:System.AggregateException?displayProperty=nameWithType> que se produce.</span><span class="sxs-lookup"><span data-stu-id="44920-113">In this example, all exceptions are caught and then wrapped in an <xref:System.AggregateException?displayProperty=nameWithType> which is thrown.</span></span> <span data-ttu-id="44920-114">El llamador puede decidir qué excepciones se deben administrar.</span><span class="sxs-lookup"><span data-stu-id="44920-114">The caller can decide which exceptions to handle.</span></span>  
  
 [!code-csharp[TPL_Exceptions#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#08)]
 [!code-vb[TPL_Exceptions#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionsinloops.vb#08)]  
  
## <a name="see-also"></a><span data-ttu-id="44920-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="44920-115">See Also</span></span>  
 <span data-ttu-id="44920-116">[Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md) (Paralelismo de datos)</span><span class="sxs-lookup"><span data-stu-id="44920-116">[Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)</span></span>  
 [<span data-ttu-id="44920-117">Expresiones lambda en PLINQ y TPL</span><span class="sxs-lookup"><span data-stu-id="44920-117">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
