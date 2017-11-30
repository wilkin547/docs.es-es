---
title: do (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords: do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
caps.latest.revision: "22"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d24078d3fb985f643fb66aa456900d03d2ff3fce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="do-c-reference"></a><span data-ttu-id="67c3f-102">do (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="67c3f-102">do (C# Reference)</span></span>
<span data-ttu-id="67c3f-103">La instrucción `do` ejecuta una instrucción o un bloque de instrucciones repetidamente hasta que una expresión especificada se evalúa como `false`.</span><span class="sxs-lookup"><span data-stu-id="67c3f-103">The `do` statement executes a statement or a block of statements repeatedly until a specified expression evaluates to `false`.</span></span> <span data-ttu-id="67c3f-104">El cuerpo del bucle debe incluirse entre llaves, `{}`, a menos que conste de una sola instrucción.</span><span class="sxs-lookup"><span data-stu-id="67c3f-104">The body of the loop must be enclosed in braces, `{}`, unless it consists of a single statement.</span></span> <span data-ttu-id="67c3f-105">En ese caso, las llaves son opcionales.</span><span class="sxs-lookup"><span data-stu-id="67c3f-105">In that case, the braces are optional.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67c3f-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67c3f-106">Example</span></span>  
 <span data-ttu-id="67c3f-107">En el ejemplo siguiente, las instrucciones de bucle `do-while` se ejecutan siempre que la variable `x` sea menor que 5.</span><span class="sxs-lookup"><span data-stu-id="67c3f-107">In the following example, the `do-while` loop statements execute as long as the variable `x` is less than 5.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]  
  
 <span data-ttu-id="67c3f-108">A diferencia de la instrucción [while](../../../csharp/language-reference/keywords/while.md), un bucle `do-while` se ejecuta una vez antes de que se evalúe la expresión condicional.</span><span class="sxs-lookup"><span data-stu-id="67c3f-108">Unlike the [while](../../../csharp/language-reference/keywords/while.md) statement, a `do-while` loop is executed one time before the conditional expression is evaluated.</span></span>  
  
 <span data-ttu-id="67c3f-109">En cualquier punto del bloque `do-while`, puede salir del bucle mediante la instrucción [break](../../../csharp/language-reference/keywords/break.md).</span><span class="sxs-lookup"><span data-stu-id="67c3f-109">At any point in the `do-while` block, you can break out of the loop using the [break](../../../csharp/language-reference/keywords/break.md) statement.</span></span> <span data-ttu-id="67c3f-110">Puede ir directamente a la instrucción de evaluación de expresiones `while` mediante la instrucción [continue](../../../csharp/language-reference/keywords/continue.md).</span><span class="sxs-lookup"><span data-stu-id="67c3f-110">You can step directly to the `while` expression evaluation statement by using the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="67c3f-111">Si la expresión `while` se evalúa como true, la ejecución continúa en la primera instrucción del bucle.</span><span class="sxs-lookup"><span data-stu-id="67c3f-111">If the `while` expression evaluates to true, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="67c3f-112">Si la expresión se evalúa como false, la ejecución continúa en la primera instrucción después del bucle `do-while`.</span><span class="sxs-lookup"><span data-stu-id="67c3f-112">If the expression evaluates to false, execution continues at the first statement after the `do-while` loop.</span></span>  
  
 <span data-ttu-id="67c3f-113">También se puede salir de un bucle `do-while` mediante las instrucciones [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md).</span><span class="sxs-lookup"><span data-stu-id="67c3f-113">A `do-while` loop can also be exited by the [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statements.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="67c3f-114">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="67c3f-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="67c3f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="67c3f-115">See Also</span></span>  
 [<span data-ttu-id="67c3f-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="67c3f-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="67c3f-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="67c3f-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="67c3f-118">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="67c3f-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="67c3f-119">do-while (Instrucción) (C++)</span><span class="sxs-lookup"><span data-stu-id="67c3f-119">do-while Statement (C++)</span></span>](/cpp/cpp/do-while-statement-cpp)  
 [<span data-ttu-id="67c3f-120">Instrucciones de iteración</span><span class="sxs-lookup"><span data-stu-id="67c3f-120">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
