---
title: do (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: 5599f079e29fd094c4d6a6a75afba89fb562a166
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="do-c-reference"></a><span data-ttu-id="db404-102">do (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="db404-102">do (C# Reference)</span></span>
<span data-ttu-id="db404-103">La instrucción `do` ejecuta una instrucción o un bloque de instrucciones repetidamente hasta que una expresión especificada se evalúa como `false`.</span><span class="sxs-lookup"><span data-stu-id="db404-103">The `do` statement executes a statement or a block of statements repeatedly until a specified expression evaluates to `false`.</span></span> <span data-ttu-id="db404-104">El cuerpo del bucle debe incluirse entre llaves, `{}`, a menos que conste de una sola instrucción.</span><span class="sxs-lookup"><span data-stu-id="db404-104">The body of the loop must be enclosed in braces, `{}`, unless it consists of a single statement.</span></span> <span data-ttu-id="db404-105">En ese caso, las llaves son opcionales.</span><span class="sxs-lookup"><span data-stu-id="db404-105">In that case, the braces are optional.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db404-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="db404-106">Example</span></span>  
 <span data-ttu-id="db404-107">En el ejemplo siguiente, las instrucciones de bucle `do-while` se ejecutan siempre que la variable `x` sea menor que 5.</span><span class="sxs-lookup"><span data-stu-id="db404-107">In the following example, the `do-while` loop statements execute as long as the variable `x` is less than 5.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]  
  
 <span data-ttu-id="db404-108">A diferencia de la instrucción [while](../../../csharp/language-reference/keywords/while.md), un bucle `do-while` se ejecuta una vez antes de que se evalúe la expresión condicional.</span><span class="sxs-lookup"><span data-stu-id="db404-108">Unlike the [while](../../../csharp/language-reference/keywords/while.md) statement, a `do-while` loop is executed one time before the conditional expression is evaluated.</span></span>  
  
 <span data-ttu-id="db404-109">En cualquier punto del bloque `do-while`, puede salir del bucle mediante la instrucción [break](../../../csharp/language-reference/keywords/break.md).</span><span class="sxs-lookup"><span data-stu-id="db404-109">At any point in the `do-while` block, you can break out of the loop using the [break](../../../csharp/language-reference/keywords/break.md) statement.</span></span> <span data-ttu-id="db404-110">Puede ir directamente a la instrucción de evaluación de expresiones `while` mediante la instrucción [continue](../../../csharp/language-reference/keywords/continue.md).</span><span class="sxs-lookup"><span data-stu-id="db404-110">You can step directly to the `while` expression evaluation statement by using the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="db404-111">Si la expresión `while` se evalúa como true, la ejecución continúa en la primera instrucción del bucle.</span><span class="sxs-lookup"><span data-stu-id="db404-111">If the `while` expression evaluates to true, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="db404-112">Si la expresión se evalúa como false, la ejecución continúa en la primera instrucción después del bucle `do-while`.</span><span class="sxs-lookup"><span data-stu-id="db404-112">If the expression evaluates to false, execution continues at the first statement after the `do-while` loop.</span></span>  
  
 <span data-ttu-id="db404-113">También se puede salir de un bucle `do-while` mediante las instrucciones [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md).</span><span class="sxs-lookup"><span data-stu-id="db404-113">A `do-while` loop can also be exited by the [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statements.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="db404-114">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="db404-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="db404-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="db404-115">See Also</span></span>  
 [<span data-ttu-id="db404-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="db404-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="db404-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="db404-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="db404-118">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="db404-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="db404-119">do-while (Instrucción) (C++)</span><span class="sxs-lookup"><span data-stu-id="db404-119">do-while Statement (C++)</span></span>](/cpp/cpp/do-while-statement-cpp)  
 [<span data-ttu-id="db404-120">Instrucciones de iteración</span><span class="sxs-lookup"><span data-stu-id="db404-120">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
