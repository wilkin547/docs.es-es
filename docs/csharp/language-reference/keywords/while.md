---
title: while (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 420b409689d877c3e1ac744e8d7a65500cf8f964
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="while-c-reference"></a><span data-ttu-id="53651-102">while (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="53651-102">while (C# Reference)</span></span>
<span data-ttu-id="53651-103">La instrucción `while` ejecuta una instrucción o un bloque de instrucciones hasta que una expresión especificada se evalúa como `false`.</span><span class="sxs-lookup"><span data-stu-id="53651-103">The `while` statement executes a statement or a block of statements until a specified expression evaluates to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53651-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53651-104">Example</span></span>  
 [!code-csharp[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="53651-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53651-105">Example</span></span>  
 [!code-csharp[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="53651-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53651-106">Example</span></span>  
 <span data-ttu-id="53651-107">Como la comprobación de la expresión `while` tiene lugar antes de la ejecución del bucle, un bucle `while` se ejecuta cero o varias veces.</span><span class="sxs-lookup"><span data-stu-id="53651-107">Because the test of the `while` expression takes place before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="53651-108">Esto es diferente del bucle [do](../../../csharp/language-reference/keywords/do.md) que se ejecuta una o varias veces.</span><span class="sxs-lookup"><span data-stu-id="53651-108">This differs from the [do](../../../csharp/language-reference/keywords/do.md) loop, which executes one or more times.</span></span>  
  
 <span data-ttu-id="53651-109">Un bucle `while` se puede terminar cuando una instrucción [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md) transfiere el control fuera del bucle.</span><span class="sxs-lookup"><span data-stu-id="53651-109">A `while` loop can be terminated when a [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statement transfers control outside the loop.</span></span> <span data-ttu-id="53651-110">Para pasar el control a la siguiente iteración sin salir del bucle, use la instrucción [continue](../../../csharp/language-reference/keywords/continue.md).</span><span class="sxs-lookup"><span data-stu-id="53651-110">To pass control to the next iteration without exiting the loop, use the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="53651-111">Observe la diferencia en los resultados de los tres ejemplos anteriores, con relación a dónde se incrementa `int n`.</span><span class="sxs-lookup"><span data-stu-id="53651-111">Notice the difference in output in the three previous examples, depending on where `int n` is incremented.</span></span> <span data-ttu-id="53651-112">En el ejemplo siguiente no se genera ningún resultado.</span><span class="sxs-lookup"><span data-stu-id="53651-112">In the example below no output is generated.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="53651-113">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="53651-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="53651-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="53651-114">See Also</span></span>  
 [<span data-ttu-id="53651-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="53651-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="53651-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="53651-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="53651-117">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="53651-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="53651-118">while (Instrucción) (C++)</span><span class="sxs-lookup"><span data-stu-id="53651-118">while Statement (C++)</span></span>](/cpp/cpp/while-statement-cpp)  
 [<span data-ttu-id="53651-119">Instrucciones de iteración</span><span class="sxs-lookup"><span data-stu-id="53651-119">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
