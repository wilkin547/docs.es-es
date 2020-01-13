---
title: 'Instrucción continue: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 83b43b31eacf0ed835ee3d7a919538eb9f1dd1e8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713661"
---
# <a name="continue-c-reference"></a><span data-ttu-id="1fd24-102">continue (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="1fd24-102">continue (C# Reference)</span></span>

<span data-ttu-id="1fd24-103">La instrucción `continue` transfiere el control a la siguiente iteración de la instrucción envolvente [while](./while.md), [do](./do.md), [for](./for.md) o [foreach](./foreach-in.md) en la que aparece.</span><span class="sxs-lookup"><span data-stu-id="1fd24-103">The `continue` statement passes control to the next iteration of the enclosing [while](./while.md), [do](./do.md), [for](./for.md), or [foreach](./foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="1fd24-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1fd24-104">Example</span></span>

<span data-ttu-id="1fd24-105">En este ejemplo se inicializa un contador para contar del 1 al 10.</span><span class="sxs-lookup"><span data-stu-id="1fd24-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="1fd24-106">Si se usa la instrucción `continue` junto con la expresión `(i < 9)`, se omiten las instrucciones comprendidas entre `continue` y el final del cuerpo de `for`.</span><span class="sxs-lookup"><span data-stu-id="1fd24-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="1fd24-107">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="1fd24-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="1fd24-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="1fd24-108">See also</span></span>

- [<span data-ttu-id="1fd24-109">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="1fd24-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1fd24-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="1fd24-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1fd24-111">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="1fd24-111">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="1fd24-112">break (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="1fd24-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
