---
title: 'Instrucción goto: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: e4642d0e43a538217493298b58d572e435db5dae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645332"
---
# <a name="goto-c-reference"></a><span data-ttu-id="f8ae8-102">goto (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f8ae8-102">goto (C# Reference)</span></span>

<span data-ttu-id="f8ae8-103">La instrucción `goto` transfiere el control del programa directamente a una instrucción con etiqueta.</span><span class="sxs-lookup"><span data-stu-id="f8ae8-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>

<span data-ttu-id="f8ae8-104">Un uso común de `goto` consiste en transferir el control a una etiqueta de switch case específica o a la etiqueta predeterminada en una instrucción `switch`.</span><span class="sxs-lookup"><span data-stu-id="f8ae8-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>

<span data-ttu-id="f8ae8-105">La instrucción `goto` también es útil para salir de bucles demasiado anidados.</span><span class="sxs-lookup"><span data-stu-id="f8ae8-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>

## <a name="example"></a><span data-ttu-id="f8ae8-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8ae8-106">Example</span></span>

<span data-ttu-id="f8ae8-107">En el ejemplo siguiente se muestra cómo usar `goto` en una instrucción [switch](switch.md).</span><span class="sxs-lookup"><span data-stu-id="f8ae8-107">The following example demonstrates using `goto` in a [switch](switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a><span data-ttu-id="f8ae8-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8ae8-108">Example</span></span>

<span data-ttu-id="f8ae8-109">En el ejemplo siguiente se muestra cómo usar `goto` para salir de bucles anidados.</span><span class="sxs-lookup"><span data-stu-id="f8ae8-109">The following example demonstrates using `goto` to break out from nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="f8ae8-110">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f8ae8-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f8ae8-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8ae8-111">See also</span></span>

- [<span data-ttu-id="f8ae8-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f8ae8-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f8ae8-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f8ae8-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f8ae8-114">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="f8ae8-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f8ae8-115">goto (Instrucción) (C++)</span><span class="sxs-lookup"><span data-stu-id="f8ae8-115">goto Statement (C++)</span></span>](/cpp/cpp/goto-statement-cpp)
- [<span data-ttu-id="f8ae8-116">Instrucciones de salto</span><span class="sxs-lookup"><span data-stu-id="f8ae8-116">Jump Statements</span></span>](jump-statements.md)
