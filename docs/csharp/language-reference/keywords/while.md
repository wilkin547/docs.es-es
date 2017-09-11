---
title: while (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- while_CSharpKeyword
- while
dev_langs:
- CSharp
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
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
ms.openlocfilehash: ed531c83dba02b38576bf8354b1ff92f075048bc
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="while-c-reference"></a><span data-ttu-id="0bbbc-102">while (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="0bbbc-102">while (C# Reference)</span></span>
<span data-ttu-id="0bbbc-103">La instrucción `while` ejecuta una instrucción o un bloque de instrucciones hasta que una expresión especificada se evalúa como `false`.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-103">The `while` statement executes a statement or a block of statements until a specified expression evaluates to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bbbc-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0bbbc-104">Example</span></span>  
 <span data-ttu-id="0bbbc-105">[!code-cs[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0bbbc-105">[!code-cs[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bbbc-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0bbbc-106">Example</span></span>  
 <span data-ttu-id="0bbbc-107">[!code-cs[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="0bbbc-107">[!code-cs[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bbbc-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0bbbc-108">Example</span></span>  
 <span data-ttu-id="0bbbc-109">Como la comprobación de la expresión `while` tiene lugar antes de la ejecución del bucle, un bucle `while` se ejecuta cero o varias veces.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-109">Because the test of the `while` expression takes place before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="0bbbc-110">Esto es diferente del bucle [do](../../../csharp/language-reference/keywords/do.md) que se ejecuta una o varias veces.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-110">This differs from the [do](../../../csharp/language-reference/keywords/do.md) loop, which executes one or more times.</span></span>  
  
 <span data-ttu-id="0bbbc-111">Un bucle `while` se puede terminar cuando una instrucción [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md) transfiere el control fuera del bucle.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-111">A `while` loop can be terminated when a [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statement transfers control outside the loop.</span></span> <span data-ttu-id="0bbbc-112">Para pasar el control a la siguiente iteración sin salir del bucle, use la instrucción [continue](../../../csharp/language-reference/keywords/continue.md).</span><span class="sxs-lookup"><span data-stu-id="0bbbc-112">To pass control to the next iteration without exiting the loop, use the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="0bbbc-113">Observe la diferencia en los resultados de los tres ejemplos anteriores, con relación a dónde se incrementa `int n`.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-113">Notice the difference in output in the three previous examples, depending on where `int n` is incremented.</span></span> <span data-ttu-id="0bbbc-114">En el ejemplo siguiente no se genera ningún resultado.</span><span class="sxs-lookup"><span data-stu-id="0bbbc-114">In the example below no output is generated.</span></span>  
  
 <span data-ttu-id="0bbbc-115">[!code-cs[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="0bbbc-115">[!code-cs[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0bbbc-116">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="0bbbc-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0bbbc-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0bbbc-117">See Also</span></span>  
 <span data-ttu-id="0bbbc-118">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0bbbc-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0bbbc-119">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0bbbc-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0bbbc-120">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="0bbbc-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="0bbbc-121">[while (Instrucción) (C++)](/cpp/cpp/while-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="0bbbc-121">[while Statement (C++)](/cpp/cpp/while-statement-cpp) </span></span>  
 [<span data-ttu-id="0bbbc-122">Instrucciones de iteración</span><span class="sxs-lookup"><span data-stu-id="0bbbc-122">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)

