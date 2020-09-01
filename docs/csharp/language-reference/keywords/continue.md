---
description: 'Instrucción continue: Referencia de C#'
title: 'Instrucción continue: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 76578b0ad7e2b969609fbf50df1f9ab7de6e5097
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128444"
---
# <a name="continue-c-reference"></a><span data-ttu-id="03cc4-103">continue (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="03cc4-103">continue (C# Reference)</span></span>

<span data-ttu-id="03cc4-104">La instrucción `continue` transfiere el control a la siguiente iteración de la instrucción envolvente [while](./while.md), [do](./do.md), [for](./for.md) o [foreach](./foreach-in.md) en la que aparece.</span><span class="sxs-lookup"><span data-stu-id="03cc4-104">The `continue` statement passes control to the next iteration of the enclosing [while](./while.md), [do](./do.md), [for](./for.md), or [foreach](./foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="03cc4-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03cc4-105">Example</span></span>

<span data-ttu-id="03cc4-106">En este ejemplo se inicializa un contador para contar del 1 al 10.</span><span class="sxs-lookup"><span data-stu-id="03cc4-106">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="03cc4-107">Si se usa la instrucción `continue` junto con la expresión `(i < 9)`, se omiten las instrucciones comprendidas entre `continue` y el final del cuerpo de `for`.</span><span class="sxs-lookup"><span data-stu-id="03cc4-107">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="03cc4-108">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="03cc4-108">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="03cc4-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="03cc4-109">See also</span></span>

- [<span data-ttu-id="03cc4-110">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="03cc4-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="03cc4-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="03cc4-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="03cc4-112">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="03cc4-112">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="03cc4-113">break (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="03cc4-113">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
