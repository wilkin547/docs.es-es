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
ms.openlocfilehash: 6c70934c3b861e1a1433e5c0b95bb32e9d717c53
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877657"
---
# <a name="continue-c-reference"></a><span data-ttu-id="3acb2-103">continue (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="3acb2-103">continue (C# Reference)</span></span>

<span data-ttu-id="3acb2-104">La instrucción `continue` transfiere el control a la siguiente iteración de la instrucción envolvente [while](./while.md), [do](./do.md), [for](./for.md) o [foreach](./foreach-in.md) en la que aparece.</span><span class="sxs-lookup"><span data-stu-id="3acb2-104">The `continue` statement passes control to the next iteration of the enclosing [while](./while.md), [do](./do.md), [for](./for.md), or [foreach](./foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="3acb2-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3acb2-105">Example</span></span>

<span data-ttu-id="3acb2-106">En este ejemplo se inicializa un contador para contar del 1 al 10.</span><span class="sxs-lookup"><span data-stu-id="3acb2-106">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="3acb2-107">Si se usa la instrucción `continue` junto con la expresión `(i < 9)`, se omiten las instrucciones comprendidas entre `continue` y el final del cuerpo de `for` en las iteraciones donde `i` es menor que 9.</span><span class="sxs-lookup"><span data-stu-id="3acb2-107">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped in the iterations where `i` is less than 9.</span></span> <span data-ttu-id="3acb2-108">En las dos últimas iteraciones del bucle `for` (donde i == 9 e i == 10), la instrucción `continue` no se ejecuta y el valor de `i` se imprime en la consola.</span><span class="sxs-lookup"><span data-stu-id="3acb2-108">In the last two iterations of the `for` loop (where i == 9 and i == 10), the `continue` statement is not executed and the value of `i` is printed to the console.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="3acb2-109">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="3acb2-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="3acb2-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3acb2-110">See also</span></span>

- [<span data-ttu-id="3acb2-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="3acb2-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3acb2-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3acb2-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3acb2-113">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="3acb2-113">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="3acb2-114">break (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="3acb2-114">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
