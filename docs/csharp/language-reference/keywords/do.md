---
title: do (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- do_CSharpKeyword
- do
dev_langs:
- CSharp
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 58a9361c440bc1b17c5ab929ff7b45ba71ce50a4
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="do-c-reference"></a><span data-ttu-id="14157-102">do (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="14157-102">do (C# Reference)</span></span>
<span data-ttu-id="14157-103">La instrucción `do` ejecuta una instrucción o un bloque de instrucciones repetidamente hasta que una expresión especificada se evalúa como `false`.</span><span class="sxs-lookup"><span data-stu-id="14157-103">The `do` statement executes a statement or a block of statements repeatedly until a specified expression evaluates to `false`.</span></span> <span data-ttu-id="14157-104">El cuerpo del bucle debe incluirse entre llaves, `{}`, a menos que conste de una sola instrucción.</span><span class="sxs-lookup"><span data-stu-id="14157-104">The body of the loop must be enclosed in braces, `{}`, unless it consists of a single statement.</span></span> <span data-ttu-id="14157-105">En ese caso, las llaves son opcionales.</span><span class="sxs-lookup"><span data-stu-id="14157-105">In that case, the braces are optional.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14157-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="14157-106">Example</span></span>  
 <span data-ttu-id="14157-107">En el ejemplo siguiente, las instrucciones de bucle `do-while` se ejecutan siempre que la variable `x` sea menor que 5.</span><span class="sxs-lookup"><span data-stu-id="14157-107">In the following example, the `do-while` loop statements execute as long as the variable `x` is less than 5.</span></span>  
  
 <span data-ttu-id="14157-108">[!code-cs[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="14157-108">[!code-cs[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]</span></span>  
  
 <span data-ttu-id="14157-109">A diferencia de la instrucción [while](../../../csharp/language-reference/keywords/while.md), un bucle `do-while` se ejecuta una vez antes de que se evalúe la expresión condicional.</span><span class="sxs-lookup"><span data-stu-id="14157-109">Unlike the [while](../../../csharp/language-reference/keywords/while.md) statement, a `do-while` loop is executed one time before the conditional expression is evaluated.</span></span>  
  
 <span data-ttu-id="14157-110">En cualquier punto del bloque `do-while`, puede salir del bucle mediante la instrucción [break](../../../csharp/language-reference/keywords/break.md).</span><span class="sxs-lookup"><span data-stu-id="14157-110">At any point in the `do-while` block, you can break out of the loop using the [break](../../../csharp/language-reference/keywords/break.md) statement.</span></span> <span data-ttu-id="14157-111">Puede ir directamente a la instrucción de evaluación de expresiones `while` mediante la instrucción [continue](../../../csharp/language-reference/keywords/continue.md).</span><span class="sxs-lookup"><span data-stu-id="14157-111">You can step directly to the `while` expression evaluation statement by using the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="14157-112">Si la expresión `while` se evalúa como true, la ejecución continúa en la primera instrucción del bucle.</span><span class="sxs-lookup"><span data-stu-id="14157-112">If the `while` expression evaluates to true, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="14157-113">Si la expresión se evalúa como false, la ejecución continúa en la primera instrucción después del bucle `do-while`.</span><span class="sxs-lookup"><span data-stu-id="14157-113">If the expression evaluates to false, execution continues at the first statement after the `do-while` loop.</span></span>  
  
 <span data-ttu-id="14157-114">También se puede salir de un bucle `do-while` mediante las instrucciones [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md).</span><span class="sxs-lookup"><span data-stu-id="14157-114">A `do-while` loop can also be exited by the [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statements.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="14157-115">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="14157-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="14157-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="14157-116">See Also</span></span>  
 <span data-ttu-id="14157-117">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="14157-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="14157-118">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="14157-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="14157-119">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="14157-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="14157-120">[Instrucción do-while (C++)](/cpp/cpp/do-while-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="14157-120">[do-while Statement (C++)](/cpp/cpp/do-while-statement-cpp) </span></span>  
 [<span data-ttu-id="14157-121">Instrucciones de iteración</span><span class="sxs-lookup"><span data-stu-id="14157-121">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)

