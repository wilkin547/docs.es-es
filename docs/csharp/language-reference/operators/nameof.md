---
title: 'Expresión nameof: referencia de C#'
ms.date: 04/23/2020
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: b00c5f6f97d27290fb3773dcbb422bf9fb4c425b
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916778"
---
# <a name="nameof-expression-c-reference"></a><span data-ttu-id="7c981-102">Expresión nameof (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="7c981-102">nameof expression (C# reference)</span></span>

<span data-ttu-id="7c981-103">Una expresión `nameof` genera el nombre de una variable, un tipo o un miembro como constante de cadena:</span><span class="sxs-lookup"><span data-stu-id="7c981-103">A `nameof` expression produces the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof expression](snippets/shared/NameOfOperator.cs#Examples)]

<span data-ttu-id="7c981-104">Como se muestra en el ejemplo anterior, en el caso de un tipo y un espacio de nombres, el nombre generado por lo general no está [completo](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span><span class="sxs-lookup"><span data-stu-id="7c981-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="7c981-105">En el caso de [identificadores textuales](../tokens/verbatim.md), el carácter `@` no es parte de un nombre, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7c981-105">In the case of [verbatim identifiers](../tokens/verbatim.md), the `@` character is not the part of a name, as the following example shows:</span></span>

[!code-csharp-interactive[nameof verbatim](snippets/shared/NameOfOperator.cs#Verbatim)]

<span data-ttu-id="7c981-106">La expresión `nameof` se evalúa en tiempo de compilación y no tiene efecto en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7c981-106">A `nameof` expression is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="7c981-107">Puede usar una expresión `nameof` para facilitar el mantenimiento del código de comprobación de argumentos:</span><span class="sxs-lookup"><span data-stu-id="7c981-107">You can use a `nameof` expression to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](snippets/shared/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="7c981-108">Una expresión `nameof` está disponible en C# 6 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="7c981-108">A `nameof` expression is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7c981-109">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="7c981-109">C# language specification</span></span>

<span data-ttu-id="7c981-110">Para más información, consulte la sección [Expresiones Nameof](~/_csharplang/spec/expressions.md#nameof-expressions) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="7c981-110">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7c981-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c981-111">See also</span></span>

- [<span data-ttu-id="7c981-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="7c981-112">C# reference</span></span>](../index.md)
- [<span data-ttu-id="7c981-113">Operadores y expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="7c981-113">C# operators and expressions</span></span>](index.md)
