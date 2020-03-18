---
title: do - Referencia de C#
ms.date: 05/28/2018
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: 38224ce70c19ff67ad80b99d3da52155849f1341
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713600"
---
# <a name="do-c-reference"></a><span data-ttu-id="956fc-102">do (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="956fc-102">do (C# Reference)</span></span>

<span data-ttu-id="956fc-103">La instrucción `do` ejecuta una instrucción o un bloque de instrucciones mientras que una expresión booleana especificada se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="956fc-103">The `do` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span> <span data-ttu-id="956fc-104">Como esa expresión se evalúa después de cada ejecución del bucle, un bucle `do-while` se ejecuta una o varias veces.</span><span class="sxs-lookup"><span data-stu-id="956fc-104">Because that expression is evaluated after each execution of the loop, a `do-while` loop executes one or more times.</span></span> <span data-ttu-id="956fc-105">Esto es diferente del bucle [while](while.md), que se ejecuta cero o varias veces.</span><span class="sxs-lookup"><span data-stu-id="956fc-105">This differs from the [while](while.md) loop, which executes zero or more times.</span></span>

<span data-ttu-id="956fc-106">En cualquier punto del bloque de instrucciones `do`, se puede salir del bucle mediante la instrucción [break](break.md).</span><span class="sxs-lookup"><span data-stu-id="956fc-106">At any point within the `do` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="956fc-107">Puede ir directamente a la evaluación de la expresión `while` mediante la instrucción [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="956fc-107">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="956fc-108">Si la expresión se evalúa como `true`, la ejecución continúa en la primera instrucción del bucle.</span><span class="sxs-lookup"><span data-stu-id="956fc-108">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="956fc-109">En caso contrario, la ejecución continúa en la primera instrucción después del bucle.</span><span class="sxs-lookup"><span data-stu-id="956fc-109">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="956fc-110">También se puede salir de un bucle `do-while` mediante las instrucciones [goto](goto.md), [return](return.md) o [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="956fc-110">You also can exit a `do-while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="956fc-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="956fc-111">Example</span></span>

<span data-ttu-id="956fc-112">En el ejemplo siguiente se muestra el uso de la instrucción `do`.</span><span class="sxs-lookup"><span data-stu-id="956fc-112">The following example shows the usage of the `do` statement.</span></span> <span data-ttu-id="956fc-113">Haga clic en **Ejecutar** para ejecutar el código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="956fc-113">Select **Run** to run the example code.</span></span> <span data-ttu-id="956fc-114">Después, puede modificar el código y volver a ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="956fc-114">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[do loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="956fc-115">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="956fc-115">C# language specification</span></span>

<span data-ttu-id="956fc-116">Para más información, vea la sección sobre la [instrucción do](~/_csharplang/spec/statements.md#the-do-statement) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="956fc-116">For more information, see [The do statement](~/_csharplang/spec/statements.md#the-do-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="956fc-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="956fc-117">See also</span></span>

- [<span data-ttu-id="956fc-118">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="956fc-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="956fc-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="956fc-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="956fc-120">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="956fc-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="956fc-121">while (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="956fc-121">while statement</span></span>](while.md)
