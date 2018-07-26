---
title: do (Referencia de C#)
ms.date: 05/28/2018
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: b918b378623a239803fb4e0a65fcf82fd677b21f
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2018
ms.locfileid: "37961331"
---
# <a name="do-c-reference"></a><span data-ttu-id="266fa-102">do (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="266fa-102">do (C# Reference)</span></span>

<span data-ttu-id="266fa-103">La instrucción `do` ejecuta una instrucción o un bloque de instrucciones mientras una expresión booleana especificada se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="266fa-103">The `do` statement executes a statement or a block of statements while a specified boolean expression evaluates to `true`.</span></span> <span data-ttu-id="266fa-104">Como esa expresión se evalúa después de cada ejecución del bucle, un bucle `do-while` se ejecuta una o varias veces.</span><span class="sxs-lookup"><span data-stu-id="266fa-104">Because that expression is evaluated after each execution of the loop, a `do-while` loop executes one or more times.</span></span> <span data-ttu-id="266fa-105">Esto es diferente del bucle [while](while.md), que se ejecuta cero o varias veces.</span><span class="sxs-lookup"><span data-stu-id="266fa-105">This differs from the [while](while.md) loop, which executes zero or more times.</span></span>

<span data-ttu-id="266fa-106">En cualquier punto del bloque de instrucciones `do`, se puede salir del bucle mediante la instrucción [break](break.md).</span><span class="sxs-lookup"><span data-stu-id="266fa-106">At any point within the `do` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="266fa-107">Puede ir directamente a la evaluación de la expresión `while` mediante la instrucción [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="266fa-107">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="266fa-108">Si la expresión se evalúa como `true`, la ejecución continúa en la primera instrucción del bucle.</span><span class="sxs-lookup"><span data-stu-id="266fa-108">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="266fa-109">En caso contrario, la ejecución continúa en la primera instrucción después del bucle.</span><span class="sxs-lookup"><span data-stu-id="266fa-109">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="266fa-110">También se puede salir de un bucle `do-while` mediante las instrucciones [goto](goto.md), [return](return.md) o [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="266fa-110">You also can exit a `do-while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="266fa-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="266fa-111">Example</span></span>

<span data-ttu-id="266fa-112">En el ejemplo siguiente se muestra el uso de la instrucción `do`.</span><span class="sxs-lookup"><span data-stu-id="266fa-112">The following example shows the usage of the `do` statement.</span></span> <span data-ttu-id="266fa-113">Haga clic en **Ejecutar** para ejecutar el código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="266fa-113">Select **Run** to run the example code.</span></span> <span data-ttu-id="266fa-114">Después, puede modificar el código y volver a ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="266fa-114">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[do loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="266fa-115">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="266fa-115">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="266fa-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="266fa-116">See also</span></span>

 [<span data-ttu-id="266fa-117">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="266fa-117">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="266fa-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="266fa-118">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="266fa-119">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="266fa-119">C# Keywords</span></span>](index.md)  
 [<span data-ttu-id="266fa-120">do-while (Instrucción) (C++)</span><span class="sxs-lookup"><span data-stu-id="266fa-120">do-while Statement (C++)</span></span>](/cpp/cpp/do-while-statement-cpp)  
 [<span data-ttu-id="266fa-121">Instrucciones de iteración</span><span class="sxs-lookup"><span data-stu-id="266fa-121">Iteration Statements</span></span>](iteration-statements.md)  
 [<span data-ttu-id="266fa-122">while (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="266fa-122">while statement</span></span>](while.md)  
