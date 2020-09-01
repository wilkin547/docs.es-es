---
description: do - Referencia de C#
title: do - Referencia de C#
ms.date: 05/28/2018
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: 601231f23a58e8af8339a733677f0bbd92bb4ffc
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89126962"
---
# <a name="do-c-reference"></a><span data-ttu-id="efab8-103">do (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="efab8-103">do (C# Reference)</span></span>

<span data-ttu-id="efab8-104">La instrucción `do` ejecuta una instrucción o un bloque de instrucciones mientras que una expresión booleana especificada se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="efab8-104">The `do` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span> <span data-ttu-id="efab8-105">Como esa expresión se evalúa después de cada ejecución del bucle, un bucle `do-while` se ejecuta una o varias veces.</span><span class="sxs-lookup"><span data-stu-id="efab8-105">Because that expression is evaluated after each execution of the loop, a `do-while` loop executes one or more times.</span></span> <span data-ttu-id="efab8-106">Esto es diferente del bucle [while](while.md), que se ejecuta cero o varias veces.</span><span class="sxs-lookup"><span data-stu-id="efab8-106">This differs from the [while](while.md) loop, which executes zero or more times.</span></span>

<span data-ttu-id="efab8-107">En cualquier punto del bloque de instrucciones `do`, se puede salir del bucle mediante la instrucción [break](break.md).</span><span class="sxs-lookup"><span data-stu-id="efab8-107">At any point within the `do` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="efab8-108">Puede ir directamente a la evaluación de la expresión `while` mediante la instrucción [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="efab8-108">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="efab8-109">Si la expresión se evalúa como `true`, la ejecución continúa en la primera instrucción del bucle.</span><span class="sxs-lookup"><span data-stu-id="efab8-109">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="efab8-110">En caso contrario, la ejecución continúa en la primera instrucción después del bucle.</span><span class="sxs-lookup"><span data-stu-id="efab8-110">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="efab8-111">También se puede salir de un bucle `do-while` mediante las instrucciones [goto](goto.md), [return](return.md) o [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="efab8-111">You can also exit a `do-while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="efab8-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="efab8-112">Example</span></span>

<span data-ttu-id="efab8-113">En el ejemplo siguiente se muestra el uso de la instrucción `do`.</span><span class="sxs-lookup"><span data-stu-id="efab8-113">The following example shows the usage of the `do` statement.</span></span> <span data-ttu-id="efab8-114">Haga clic en **Ejecutar** para ejecutar el código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="efab8-114">Select **Run** to run the example code.</span></span> <span data-ttu-id="efab8-115">Después, puede modificar el código y volver a ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="efab8-115">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[do loop example](snippets/IterationKeywordsExamples.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="efab8-116">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="efab8-116">C# language specification</span></span>

<span data-ttu-id="efab8-117">Para más información, vea la sección sobre la [instrucción do](~/_csharplang/spec/statements.md#the-do-statement) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="efab8-117">For more information, see [The do statement](~/_csharplang/spec/statements.md#the-do-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="efab8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="efab8-118">See also</span></span>

- [<span data-ttu-id="efab8-119">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="efab8-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="efab8-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="efab8-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="efab8-121">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="efab8-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="efab8-122">while (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="efab8-122">while statement</span></span>](while.md)
