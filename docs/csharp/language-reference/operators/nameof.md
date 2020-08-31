---
description: 'Expresión nameof: referencia de C#'
title: 'Expresión nameof: referencia de C#'
ms.date: 04/23/2020
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 04109cde2a1f9146bf9bb44f301272808797ded0
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118317"
---
# <a name="nameof-expression-c-reference"></a><span data-ttu-id="be7be-103">Expresión nameof (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="be7be-103">nameof expression (C# reference)</span></span>

<span data-ttu-id="be7be-104">Una expresión `nameof` genera el nombre de una variable, un tipo o un miembro como constante de cadena:</span><span class="sxs-lookup"><span data-stu-id="be7be-104">A `nameof` expression produces the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof expression](snippets/shared/NameOfOperator.cs#Examples)]

<span data-ttu-id="be7be-105">Como se muestra en el ejemplo anterior, en el caso de un tipo y un espacio de nombres, el nombre generado por lo general no está [completo](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span><span class="sxs-lookup"><span data-stu-id="be7be-105">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="be7be-106">En el caso de [identificadores textuales](../tokens/verbatim.md), el carácter `@` no es parte de un nombre, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="be7be-106">In the case of [verbatim identifiers](../tokens/verbatim.md), the `@` character is not the part of a name, as the following example shows:</span></span>

[!code-csharp-interactive[nameof verbatim](snippets/shared/NameOfOperator.cs#Verbatim)]

<span data-ttu-id="be7be-107">La expresión `nameof` se evalúa en tiempo de compilación y no tiene efecto en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="be7be-107">A `nameof` expression is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="be7be-108">Puede usar una expresión `nameof` para facilitar el mantenimiento del código de comprobación de argumentos:</span><span class="sxs-lookup"><span data-stu-id="be7be-108">You can use a `nameof` expression to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](snippets/shared/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="be7be-109">Una expresión `nameof` está disponible en C# 6 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="be7be-109">A `nameof` expression is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="be7be-110">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="be7be-110">C# language specification</span></span>

<span data-ttu-id="be7be-111">Para más información, consulte la sección [Expresiones Nameof](~/_csharplang/spec/expressions.md#nameof-expressions) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="be7be-111">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="be7be-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="be7be-112">See also</span></span>

- [<span data-ttu-id="be7be-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="be7be-113">C# reference</span></span>](../index.md)
- [<span data-ttu-id="be7be-114">Operadores y expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="be7be-114">C# operators and expressions</span></span>](index.md)
