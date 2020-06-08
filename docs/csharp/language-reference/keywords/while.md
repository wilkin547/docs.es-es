---
title: while - Referencia de C#
ms.date: 05/28/2018
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: af616c2381b993f86296cbfa43a01ba2f9e000c2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401867"
---
# <a name="while-c-reference"></a><span data-ttu-id="0f021-102">while (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="0f021-102">while (C# Reference)</span></span>

<span data-ttu-id="0f021-103">La instrucción `while` ejecuta una instrucción o un bloque de instrucciones mientras que una expresión booleana especificada se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="0f021-103">The `while` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span> <span data-ttu-id="0f021-104">Como esa expresión se evalúa antes de cada ejecución del bucle, un bucle `while` se ejecuta cero o varias veces.</span><span class="sxs-lookup"><span data-stu-id="0f021-104">Because that expression is evaluated before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="0f021-105">Esto es diferente del bucle [do](do.md) que se ejecuta una o varias veces.</span><span class="sxs-lookup"><span data-stu-id="0f021-105">This differs from the [do](do.md) loop, which executes one or more times.</span></span>

<span data-ttu-id="0f021-106">En cualquier punto del bloque de instrucciones `while`, se puede salir del bucle mediante la instrucción [break](break.md).</span><span class="sxs-lookup"><span data-stu-id="0f021-106">At any point within the `while` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="0f021-107">Puede ir directamente a la evaluación de la expresión `while` mediante la instrucción [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="0f021-107">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="0f021-108">Si la expresión se evalúa como `true`, la ejecución continúa en la primera instrucción del bucle.</span><span class="sxs-lookup"><span data-stu-id="0f021-108">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="0f021-109">En caso contrario, la ejecución continúa en la primera instrucción después del bucle.</span><span class="sxs-lookup"><span data-stu-id="0f021-109">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="0f021-110">También se puede salir de un bucle `while` mediante las instrucciones [goto](goto.md), [return](return.md) o [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="0f021-110">You can also exit a `while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="0f021-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0f021-111">Example</span></span>

<span data-ttu-id="0f021-112">En el ejemplo siguiente se muestra el uso de la instrucción `while`.</span><span class="sxs-lookup"><span data-stu-id="0f021-112">The following example shows the usage of the `while` statement.</span></span> <span data-ttu-id="0f021-113">Haga clic en **Ejecutar** para ejecutar el código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0f021-113">Select **Run** to run the example code.</span></span> <span data-ttu-id="0f021-114">Después, puede modificar el código y volver a ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="0f021-114">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[while loop example](snippets/IterationKeywordsExamples.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="0f021-115">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="0f021-115">C# language specification</span></span>

<span data-ttu-id="0f021-116">Para más información, vea la sección [La instrucción while](~/_csharplang/spec/statements.md#the-while-statement) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="0f021-116">For more information, see [The while statement](~/_csharplang/spec/statements.md#the-while-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="0f021-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f021-117">See also</span></span>

- [<span data-ttu-id="0f021-118">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="0f021-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0f021-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0f021-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0f021-120">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="0f021-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="0f021-121">do (instrucción)</span><span class="sxs-lookup"><span data-stu-id="0f021-121">do statement</span></span>](do.md)
