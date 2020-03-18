---
title: 'Instrucción goto: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: 076f793e880a7b4d1e8872d80e88c44cdf077541
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715270"
---
# <a name="goto-c-reference"></a><span data-ttu-id="41c3b-102">goto (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="41c3b-102">goto (C# Reference)</span></span>

<span data-ttu-id="41c3b-103">La instrucción `goto` transfiere el control del programa directamente a una instrucción con etiqueta.</span><span class="sxs-lookup"><span data-stu-id="41c3b-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>

<span data-ttu-id="41c3b-104">Un uso común de `goto` consiste en transferir el control a una etiqueta de switch case específica o a la etiqueta predeterminada en una instrucción `switch`.</span><span class="sxs-lookup"><span data-stu-id="41c3b-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>

<span data-ttu-id="41c3b-105">La instrucción `goto` también es útil para salir de bucles demasiado anidados.</span><span class="sxs-lookup"><span data-stu-id="41c3b-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>

## <a name="example"></a><span data-ttu-id="41c3b-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="41c3b-106">Example</span></span>

<span data-ttu-id="41c3b-107">En el ejemplo siguiente se muestra cómo usar `goto` en una instrucción [switch](switch.md).</span><span class="sxs-lookup"><span data-stu-id="41c3b-107">The following example demonstrates using `goto` in a [switch](switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a><span data-ttu-id="41c3b-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="41c3b-108">Example</span></span>

<span data-ttu-id="41c3b-109">En el ejemplo siguiente se muestra cómo usar `goto` para salir de bucles anidados.</span><span class="sxs-lookup"><span data-stu-id="41c3b-109">The following example demonstrates using `goto` to break out from nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="41c3b-110">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="41c3b-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="41c3b-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="41c3b-111">See also</span></span>

- [<span data-ttu-id="41c3b-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="41c3b-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="41c3b-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="41c3b-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="41c3b-114">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="41c3b-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="41c3b-115">goto (Instrucción) (C++)</span><span class="sxs-lookup"><span data-stu-id="41c3b-115">goto Statement (C++)</span></span>](/cpp/cpp/goto-statement-cpp)
