---
title: Expresiones lambda en PLINQ y TPL
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
- Func delegate, creating with lambda expression
- Action delegate, creating with lambda expression
- lambda expressions, with Action and Func
ms.assetid: 645b2c17-29d0-4ffa-8684-430743cc2f2d
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 364d23db41aac4733226189f7c8ae85d281b9887
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="lambda-expressions-in-plinq-and-tpl"></a><span data-ttu-id="ea040-102">Expresiones lambda en PLINQ y TPL</span><span class="sxs-lookup"><span data-stu-id="ea040-102">Lambda Expressions in PLINQ and TPL</span></span>
<span data-ttu-id="ea040-103">La biblioteca TPL contiene muchos métodos que adoptan una de las familias <xref:System.Func%601?displayProperty=nameWithType> o <xref:System.Action?displayProperty=nameWithType> de delegados como parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="ea040-103">The Task Parallel Library (TPL) contains many methods that take one of the <xref:System.Func%601?displayProperty=nameWithType> or <xref:System.Action?displayProperty=nameWithType> family of delegates as input parameters.</span></span> <span data-ttu-id="ea040-104">Puede usar estos delegados para pasar de la lógica personalizada del programa al bucle, tarea o consulta en paralelo.</span><span class="sxs-lookup"><span data-stu-id="ea040-104">You use these delegates to pass in your custom program logic to the parallel loop, task or query.</span></span> <span data-ttu-id="ea040-105">Los ejemplos de código de TPL, igual que igual que de PLINQ, usan expresiones lambda para crear instancias de esos delegados como bloques de código insertados.</span><span class="sxs-lookup"><span data-stu-id="ea040-105">The code examples for TPL as well as PLINQ use lambda expressions to create instances of those delegates as inline code blocks.</span></span> <span data-ttu-id="ea040-106">En este tema se proporciona una breve introducción a Func y Action, y muestra cómo usar las expresiones lambda en la biblioteca TPL y PLINQ.</span><span class="sxs-lookup"><span data-stu-id="ea040-106">This topic provides a brief introduction to Func and Action and shows you how to use lambda expressions in the Task Parallel Library and PLINQ.</span></span>  
  
 <span data-ttu-id="ea040-107">**Nota** Para más información sobre los delegados en general, consulte [Delegados](../../csharp/programming-guide/delegates/index.md) y [Delegados](../../visual-basic/programming-guide/language-features/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="ea040-107">**Note** For more information about delegates in general, see [Delegates](../../csharp/programming-guide/delegates/index.md) and [Delegates](../../visual-basic/programming-guide/language-features/delegates/index.md).</span></span> <span data-ttu-id="ea040-108">Para más información sobre las expresiones lambda en C# y [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], consulte [Expresiones lambda](~/docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) y [Expresiones lambda](~/docs/visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="ea040-108">For more information about lambda expressions in C# and [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], see [Lambda Expressions](~/docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) and [Lambda Expressions](~/docs/visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="func-delegate"></a><span data-ttu-id="ea040-109">Func (delegado)</span><span class="sxs-lookup"><span data-stu-id="ea040-109">Func Delegate</span></span>  
 <span data-ttu-id="ea040-110">Un delegado `Func` encapsula un método que devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="ea040-110">A `Func` delegate encapsulates a method that returns a value.</span></span> <span data-ttu-id="ea040-111">En una signatura Func, el último parámetro de tipo o el ubicado más a la derecha siempre especifica el tipo de devolución.</span><span class="sxs-lookup"><span data-stu-id="ea040-111">In a Func signature, the last or rightmost type parameter always specifies the return type.</span></span> <span data-ttu-id="ea040-112">Una causa común de los errores de compilador es intentar pasar dos parámetros de entrada a un <xref:System.Func%602?displayProperty=nameWithType>; de hecho, este tipo solo acepta un parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="ea040-112">One common cause of compiler errors is to attempt to pass in two input parameters to a <xref:System.Func%602?displayProperty=nameWithType>; in fact this type takes only one input parameter.</span></span> <span data-ttu-id="ea040-113">La biblioteca de clases de Framework define diecisiete versiones de `Func`: <xref:System.Func%601?displayProperty=nameWithType>, <xref:System.Func%602?displayProperty=nameWithType>, <xref:System.Func%603?displayProperty=nameWithType>, y así sucesivamente, hasta <xref:System.Func%6017?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ea040-113">The Framework Class Library defines 17 versions of `Func`: <xref:System.Func%601?displayProperty=nameWithType>, <xref:System.Func%602?displayProperty=nameWithType>, <xref:System.Func%603?displayProperty=nameWithType>, and so on up through <xref:System.Func%6017?displayProperty=nameWithType>.</span></span>  
  
## <a name="action-delegate"></a><span data-ttu-id="ea040-114">Action (delegado)</span><span class="sxs-lookup"><span data-stu-id="ea040-114">Action Delegate</span></span>  
 <span data-ttu-id="ea040-115">Un delegado <xref:System.Action?displayProperty=nameWithType> encapsula un método (Sub en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) que no devuelve un valor o que devuelve [void](~/docs/csharp/language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="ea040-115">A <xref:System.Action?displayProperty=nameWithType> delegate encapsulates a method (Sub in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) that does not return a value, or returns [void](~/docs/csharp/language-reference/keywords/void.md).</span></span> <span data-ttu-id="ea040-116">En una signatura de tipo Action, los parámetros de tipo representan solo parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="ea040-116">In an Action type signature, the type parameters represent only input parameters.</span></span> <span data-ttu-id="ea040-117">Al igual que Func, la biblioteca de clases de .NET Framework define 17 versiones de Action, desde una versión que no tiene parámetros de tipo hasta una versión que tiene 16.</span><span class="sxs-lookup"><span data-stu-id="ea040-117">Like Func, the Framework Class Library defines 17 versions of Action, from a version that has no type parameters up through a version that has 16 type parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea040-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea040-118">Example</span></span>  
 <span data-ttu-id="ea040-119">El siguiente ejemplo del método <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> muestra cómo expresar delegados Func y Action mediante expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="ea040-119">The following example for the <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> method shows how to express both Func and Action delegates by using lambda expressions.</span></span>  
  
 [!code-csharp[System.Threading.Tasks.Parallel#02](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.parallel/cs/parallelforeach.cs#02)]
 [!code-vb[System.Threading.Tasks.Parallel#02](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.parallel/vb/parallelforeach.vb#02)]  
  
## <a name="see-also"></a><span data-ttu-id="ea040-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea040-120">See Also</span></span>  
 [<span data-ttu-id="ea040-121">Programación en paralelo</span><span class="sxs-lookup"><span data-stu-id="ea040-121">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)
