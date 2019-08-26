---
title: 'Instrucción continue: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 74d166dbcf03b868baf464864e4c246f789df9cc
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605874"
---
# <a name="continue-c-reference"></a><span data-ttu-id="50d0c-102">continue (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="50d0c-102">continue (C# Reference)</span></span>

<span data-ttu-id="50d0c-103">La instrucción `continue` transfiere el control a la siguiente iteración de la instrucción envolvente [while](./while.md), [do](./do.md), [for](./for.md) o [foreach](./foreach-in.md) en la que aparece.</span><span class="sxs-lookup"><span data-stu-id="50d0c-103">The `continue` statement passes control to the next iteration of the enclosing [while](./while.md), [do](./do.md), [for](./for.md), or [foreach](./foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="50d0c-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="50d0c-104">Example</span></span>

<span data-ttu-id="50d0c-105">En este ejemplo se inicializa un contador para contar del 1 al 10.</span><span class="sxs-lookup"><span data-stu-id="50d0c-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="50d0c-106">Si se usa la instrucción `continue` junto con la expresión `(i < 9)`, se omiten las instrucciones comprendidas entre `continue` y el final del cuerpo de `for`.</span><span class="sxs-lookup"><span data-stu-id="50d0c-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="50d0c-107">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="50d0c-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="50d0c-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="50d0c-108">See also</span></span>

- [<span data-ttu-id="50d0c-109">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="50d0c-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="50d0c-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="50d0c-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="50d0c-111">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="50d0c-111">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="50d0c-112">break (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="50d0c-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
