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
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 79ab0f4427e0f37259f88cd3ec0762d1582481f1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="lambda-expressions-in-plinq-and-tpl"></a><span data-ttu-id="fc09b-102">Expresiones lambda en PLINQ y TPL</span><span class="sxs-lookup"><span data-stu-id="fc09b-102">Lambda Expressions in PLINQ and TPL</span></span>
<span data-ttu-id="fc09b-103">La biblioteca (TPL) contiene muchos métodos que toman una de las <xref:System.Func%601?displayProperty=nameWithType> o <xref:System.Action?displayProperty=nameWithType> familia de delegados como parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="fc09b-103">The Task Parallel Library (TPL) contains many methods that take one of the <xref:System.Func%601?displayProperty=nameWithType> or <xref:System.Action?displayProperty=nameWithType> family of delegates as input parameters.</span></span> <span data-ttu-id="fc09b-104">Puede usar estos delegados para pasar de la lógica personalizada del programa al bucle, tarea o consulta en paralelo.</span><span class="sxs-lookup"><span data-stu-id="fc09b-104">You use these delegates to pass in your custom program logic to the parallel loop, task or query.</span></span> <span data-ttu-id="fc09b-105">Los ejemplos de código de TPL, igual que igual que de PLINQ, usan expresiones lambda para crear instancias de esos delegados como bloques de código insertados.</span><span class="sxs-lookup"><span data-stu-id="fc09b-105">The code examples for TPL as well as PLINQ use lambda expressions to create instances of those delegates as inline code blocks.</span></span> <span data-ttu-id="fc09b-106">En este tema se proporciona una breve introducción a Func y Action, y muestra cómo usar las expresiones lambda en la biblioteca TPL y PLINQ.</span><span class="sxs-lookup"><span data-stu-id="fc09b-106">This topic provides a brief introduction to Func and Action and shows you how to use lambda expressions in the Task Parallel Library and PLINQ.</span></span>  
  
 <span data-ttu-id="fc09b-107">**Nota** Para más información sobre los delegados en general, consulte [Delegados](../../csharp/programming-guide/delegates/index.md) y [Delegados](../../visual-basic/programming-guide/language-features/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="fc09b-107">**Note** For more information about delegates in general, see [Delegates](../../csharp/programming-guide/delegates/index.md) and [Delegates](../../visual-basic/programming-guide/language-features/delegates/index.md).</span></span> <span data-ttu-id="fc09b-108">Para más información sobre las expresiones lambda en C# y [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], consulte [Expresiones lambda](~/docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) y [Expresiones lambda](~/docs/visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="fc09b-108">For more information about lambda expressions in C# and [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], see [Lambda Expressions](~/docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) and [Lambda Expressions](~/docs/visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="func-delegate"></a><span data-ttu-id="fc09b-109">Func (delegado)</span><span class="sxs-lookup"><span data-stu-id="fc09b-109">Func Delegate</span></span>  
 <span data-ttu-id="fc09b-110">Un delegado `Func` encapsula un método que devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="fc09b-110">A `Func` delegate encapsulates a method that returns a value.</span></span> <span data-ttu-id="fc09b-111">En una signatura Func, el último parámetro de tipo o el ubicado más a la derecha siempre especifica el tipo de devolución.</span><span class="sxs-lookup"><span data-stu-id="fc09b-111">In a Func signature, the last or rightmost type parameter always specifies the return type.</span></span> <span data-ttu-id="fc09b-112">Una causa común de errores del compilador está intentando pasar dos parámetros de entrada para un <xref:System.Func%602?displayProperty=nameWithType>; en el hecho de este tipo es solo un parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="fc09b-112">One common cause of compiler errors is to attempt to pass in two input parameters to a <xref:System.Func%602?displayProperty=nameWithType>; in fact this type takes only one input parameter.</span></span> <span data-ttu-id="fc09b-113">La biblioteca de clases de Framework define 17 versiones de `Func`: <xref:System.Func%601?displayProperty=nameWithType>, <xref:System.Func%602?displayProperty=nameWithType>, <xref:System.Func%603?displayProperty=nameWithType>, y así sucesivamente hasta a través de <xref:System.Func%6017?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fc09b-113">The Framework Class Library defines 17 versions of `Func`: <xref:System.Func%601?displayProperty=nameWithType>, <xref:System.Func%602?displayProperty=nameWithType>, <xref:System.Func%603?displayProperty=nameWithType>, and so on up through <xref:System.Func%6017?displayProperty=nameWithType>.</span></span>  
  
## <a name="action-delegate"></a><span data-ttu-id="fc09b-114">Action (delegado)</span><span class="sxs-lookup"><span data-stu-id="fc09b-114">Action Delegate</span></span>  
 <span data-ttu-id="fc09b-115">A <xref:System.Action?displayProperty=nameWithType> delegado encapsula un método (Sub en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) que no devuelve un valor o devuelve [void](~/docs/csharp/language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="fc09b-115">A <xref:System.Action?displayProperty=nameWithType> delegate encapsulates a method (Sub in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) that does not return a value, or returns [void](~/docs/csharp/language-reference/keywords/void.md).</span></span> <span data-ttu-id="fc09b-116">En una signatura de tipo Action, los parámetros de tipo representan solo parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="fc09b-116">In an Action type signature, the type parameters represent only input parameters.</span></span> <span data-ttu-id="fc09b-117">Al igual que Func, la biblioteca de clases de .NET Framework define 17 versiones de Action, desde una versión que no tiene parámetros de tipo hasta una versión que tiene 16.</span><span class="sxs-lookup"><span data-stu-id="fc09b-117">Like Func, the Framework Class Library defines 17 versions of Action, from a version that has no type parameters up through a version that has 16 type parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc09b-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc09b-118">Example</span></span>  
 <span data-ttu-id="fc09b-119">El siguiente ejemplo para el <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> método muestra cómo expresar delegados Func y Action mediante expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="fc09b-119">The following example for the <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> method shows how to express both Func and Action delegates by using lambda expressions.</span></span>  
  
 [!code-csharp[System.Threading.Tasks.Parallel#02](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.parallel/cs/parallelforeach.cs#02)]
 [!code-vb[System.Threading.Tasks.Parallel#02](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.parallel/vb/parallelforeach.vb#02)]  
  
## <a name="see-also"></a><span data-ttu-id="fc09b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc09b-120">See Also</span></span>  
 [<span data-ttu-id="fc09b-121">Programación en paralelo</span><span class="sxs-lookup"><span data-stu-id="fc09b-121">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)
