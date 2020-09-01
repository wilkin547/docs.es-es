---
description: 'Instrucción return: Referencia de C#'
title: 'Instrucción return: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: 486db846304c0972942ff58f3d5b276083681abe
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137010"
---
# <a name="return-c-reference"></a><span data-ttu-id="97b3f-103">return (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="97b3f-103">return (C# Reference)</span></span>

<span data-ttu-id="97b3f-104">La instrucción `return` termina la ejecución del método en el que aparece y devuelve el control al método de llamada.</span><span class="sxs-lookup"><span data-stu-id="97b3f-104">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="97b3f-105">También puede devolver un valor opcional.</span><span class="sxs-lookup"><span data-stu-id="97b3f-105">It can also return an optional value.</span></span> <span data-ttu-id="97b3f-106">Si el método es del tipo `void`, la instrucción `return` se puede omitir.</span><span class="sxs-lookup"><span data-stu-id="97b3f-106">If the method is a `void` type, the `return` statement can be omitted.</span></span>

 <span data-ttu-id="97b3f-107">Si la instrucción return está incluida en un bloque `try`, el bloque `finally`, si existe, se ejecutará antes de que el control se devuelva al método de llamada.</span><span class="sxs-lookup"><span data-stu-id="97b3f-107">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>

## <a name="example"></a><span data-ttu-id="97b3f-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="97b3f-108">Example</span></span>

 <span data-ttu-id="97b3f-109">En el siguiente ejemplo, el método `CalculateArea()` devuelve la variable local `area` como un valor de tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="97b3f-109">In the following example, the method `CalculateArea()` returns the local variable `area` as a `double` value.</span></span>

[!code-csharp[csrefKeywordsJump#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#6)]  

## <a name="c-language-specification"></a><span data-ttu-id="97b3f-110">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="97b3f-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="97b3f-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="97b3f-111">See also</span></span>

- [<span data-ttu-id="97b3f-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="97b3f-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="97b3f-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="97b3f-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="97b3f-114">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="97b3f-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="97b3f-115">return (instrucción)</span><span class="sxs-lookup"><span data-stu-id="97b3f-115">return Statement</span></span>](/cpp/cpp/return-statement-cpp)
