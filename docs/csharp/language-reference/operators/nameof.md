---
title: 'Operador nameof: referencia de C#'
ms.custom: seodec18
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof operator [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: fa858db918cdaf04c757f2741265e359acb74f7b
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036349"
---
# <a name="nameof-operator-c-reference"></a><span data-ttu-id="687f2-102">Operador nameof (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="687f2-102">nameof operator (C# reference)</span></span>

<span data-ttu-id="687f2-103">El operador `nameof` obtiene el nombre de una variable, un tipo o un miembro como la constante de cadena:</span><span class="sxs-lookup"><span data-stu-id="687f2-103">The `nameof` operator obtains the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof operator](~/samples/csharp/language-reference/operators/NameOfOperator.cs#Examples)]

<span data-ttu-id="687f2-104">Como se muestra en el ejemplo anterior, en el caso de un tipo y un espacio de nombres, el nombre generado por lo general no está [completo](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span><span class="sxs-lookup"><span data-stu-id="687f2-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="687f2-105">El operador `nameof` se evalúa en tiempo de compilación y no tiene efecto en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="687f2-105">The `nameof` operator is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="687f2-106">Puede usar el operador `nameof` para hacer que el código de comprobación de argumentos sea más fácil de mantener:</span><span class="sxs-lookup"><span data-stu-id="687f2-106">You can use the `nameof` operator to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](~/samples/csharp/language-reference/operators/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="687f2-107">El operador `nameof` está disponible en C# 6 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="687f2-107">The `nameof` operator is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="687f2-108">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="687f2-108">C# language specification</span></span>

<span data-ttu-id="687f2-109">Para más información, consulte la sección [Expresiones Nameof](~/_csharplang/spec/expressions.md#nameof-expressions) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="687f2-109">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="687f2-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="687f2-110">See also</span></span>

- [<span data-ttu-id="687f2-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="687f2-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="687f2-112">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="687f2-112">C# operators</span></span>](index.md)
