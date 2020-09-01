---
description: 'Instrucción goto: Referencia de C#'
title: 'Instrucción goto: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: de95e477bd7e76f549130643c8d4b70a0e2f015c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128431"
---
# <a name="goto-c-reference"></a><span data-ttu-id="13558-103">goto (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="13558-103">goto (C# Reference)</span></span>

<span data-ttu-id="13558-104">La instrucción `goto` transfiere el control del programa directamente a una instrucción con etiqueta.</span><span class="sxs-lookup"><span data-stu-id="13558-104">The `goto` statement transfers the program control directly to a labeled statement.</span></span>

<span data-ttu-id="13558-105">Un uso común de `goto` consiste en transferir el control a una etiqueta de switch case específica o a la etiqueta predeterminada en una instrucción `switch`.</span><span class="sxs-lookup"><span data-stu-id="13558-105">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>

<span data-ttu-id="13558-106">La instrucción `goto` también es útil para salir de bucles demasiado anidados.</span><span class="sxs-lookup"><span data-stu-id="13558-106">The `goto` statement is also useful to get out of deeply nested loops.</span></span>

## <a name="example"></a><span data-ttu-id="13558-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="13558-107">Example</span></span>

<span data-ttu-id="13558-108">En el ejemplo siguiente se muestra cómo usar `goto` en una instrucción [switch](switch.md).</span><span class="sxs-lookup"><span data-stu-id="13558-108">The following example demonstrates using `goto` in a [switch](switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a><span data-ttu-id="13558-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="13558-109">Example</span></span>

<span data-ttu-id="13558-110">En el ejemplo siguiente se muestra cómo usar `goto` para salir de bucles anidados.</span><span class="sxs-lookup"><span data-stu-id="13558-110">The following example demonstrates using `goto` to break out from nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="13558-111">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="13558-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="13558-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="13558-112">See also</span></span>

- [<span data-ttu-id="13558-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="13558-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="13558-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="13558-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="13558-115">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="13558-115">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="13558-116">goto (Instrucción) (C++)</span><span class="sxs-lookup"><span data-stu-id="13558-116">goto Statement (C++)</span></span>](/cpp/cpp/goto-statement-cpp)
