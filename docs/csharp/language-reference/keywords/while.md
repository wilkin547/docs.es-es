---
title: while (Referencia de C#)
ms.date: 05/28/2018
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: e3e9493b5371fbd6f53a779ba73743efc6d6e05b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43390029"
---
# <a name="while-c-reference"></a><span data-ttu-id="57295-102">while (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="57295-102">while (C# Reference)</span></span>

<span data-ttu-id="57295-103">La instrucción `while` ejecuta una instrucción o un bloque de instrucciones mientras una expresión booleana especificada se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="57295-103">The `while` statement executes a statement or a block of statements while a specified boolean expression evaluates to `true`.</span></span> <span data-ttu-id="57295-104">Como esa expresión se evalúa antes de cada ejecución del bucle, un bucle `while` se ejecuta cero o varias veces.</span><span class="sxs-lookup"><span data-stu-id="57295-104">Because that expression is evaluated before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="57295-105">Esto es diferente del bucle [do](do.md) que se ejecuta una o varias veces.</span><span class="sxs-lookup"><span data-stu-id="57295-105">This differs from the [do](do.md) loop, which executes one or more times.</span></span>

<span data-ttu-id="57295-106">En cualquier punto del bloque de instrucciones `while`, se puede salir del bucle mediante la instrucción [break](break.md).</span><span class="sxs-lookup"><span data-stu-id="57295-106">At any point within the `while` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="57295-107">Puede ir directamente a la evaluación de la expresión `while` mediante la instrucción [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="57295-107">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="57295-108">Si la expresión se evalúa como `true`, la ejecución continúa en la primera instrucción del bucle.</span><span class="sxs-lookup"><span data-stu-id="57295-108">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="57295-109">En caso contrario, la ejecución continúa en la primera instrucción después del bucle.</span><span class="sxs-lookup"><span data-stu-id="57295-109">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="57295-110">También se puede salir de un bucle `while` mediante las instrucciones [goto](goto.md), [return](return.md) o [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="57295-110">You also can exit a `while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="57295-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57295-111">Example</span></span>

<span data-ttu-id="57295-112">En el ejemplo siguiente se muestra el uso de la instrucción `while`.</span><span class="sxs-lookup"><span data-stu-id="57295-112">The following example shows the usage of the `while` statement.</span></span> <span data-ttu-id="57295-113">Haga clic en **Ejecutar** para ejecutar el código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="57295-113">Select **Run** to run the example code.</span></span> <span data-ttu-id="57295-114">Después, puede modificar el código y volver a ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="57295-114">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[while loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="57295-115">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="57295-115">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="57295-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="57295-116">See also</span></span>

- [<span data-ttu-id="57295-117">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="57295-117">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="57295-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="57295-118">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="57295-119">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="57295-119">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="57295-120">while (Instrucción) (C++)</span><span class="sxs-lookup"><span data-stu-id="57295-120">while Statement (C++)</span></span>](/cpp/cpp/while-statement-cpp)  
- [<span data-ttu-id="57295-121">Instrucciones de iteración</span><span class="sxs-lookup"><span data-stu-id="57295-121">Iteration Statements</span></span>](iteration-statements.md)  
- [<span data-ttu-id="57295-122">do (instrucción)</span><span class="sxs-lookup"><span data-stu-id="57295-122">do statement</span></span>](do.md)  
