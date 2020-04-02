---
title: 'Expresión nameof: referencia de C#'
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 5a68161be7bb03122d2a63ccef4365c5853862b2
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507144"
---
# <a name="nameof-expression-c-reference"></a><span data-ttu-id="a280c-102">Expresión nameof (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a280c-102">nameof expression (C# reference)</span></span>

<span data-ttu-id="a280c-103">Una expresión `nameof` genera el nombre de una variable, un tipo o un miembro como constante de cadena:</span><span class="sxs-lookup"><span data-stu-id="a280c-103">A `nameof` expression produces the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof expression](snippets/NameOfOperator.cs#Examples)]

<span data-ttu-id="a280c-104">Como se muestra en el ejemplo anterior, en el caso de un tipo y un espacio de nombres, el nombre generado por lo general no está [completo](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span><span class="sxs-lookup"><span data-stu-id="a280c-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="a280c-105">La expresión `nameof` se evalúa en tiempo de compilación y no tiene efecto en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a280c-105">A `nameof` expression is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="a280c-106">Puede usar una expresión `nameof` para facilitar el mantenimiento del código de comprobación de argumentos:</span><span class="sxs-lookup"><span data-stu-id="a280c-106">You can use a `nameof` expression to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="a280c-107">Una expresión `nameof` está disponible en C# 6 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a280c-107">A `nameof` expression is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a280c-108">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="a280c-108">C# language specification</span></span>

<span data-ttu-id="a280c-109">Para más información, consulte la sección [Expresiones Nameof](~/_csharplang/spec/expressions.md#nameof-expressions) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="a280c-109">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a280c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="a280c-110">See also</span></span>

- [<span data-ttu-id="a280c-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="a280c-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a280c-112">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="a280c-112">C# operators</span></span>](index.md)
