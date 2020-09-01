---
description: 'Palabra clave params para matrices de parámetros: referencia de C#'
title: 'Palabra clave params para matrices de parámetros: referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
- parameter array
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: a2726c725508cd297001aaabddeff414704d1115
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134476"
---
# <a name="params-c-reference"></a><span data-ttu-id="06f82-103">params (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="06f82-103">params (C# Reference)</span></span>

<span data-ttu-id="06f82-104">Mediante el uso de la palabra clave `params`, puede especificar un [parámetro de método](method-parameters.md) que toma un número variable de argumentos.</span><span class="sxs-lookup"><span data-stu-id="06f82-104">By using the `params` keyword, you can specify a [method parameter](method-parameters.md) that takes a variable number of arguments.</span></span> <span data-ttu-id="06f82-105">El tipo de parámetro debe ser una matriz unidimensional.</span><span class="sxs-lookup"><span data-stu-id="06f82-105">The parameter type must be a single-dimensional array.</span></span>

<span data-ttu-id="06f82-106">No se permiten parámetros adicionales después de la palabra clave `params` en una declaración de método, y solo se permite una palabra clave `params` en una declaración de método.</span><span class="sxs-lookup"><span data-stu-id="06f82-106">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>

<span data-ttu-id="06f82-107">Si el tipo declarado del parámetro `params` no es una matriz unidimensional, se produce el error [CS0225](../../misc/cs0225.md) del compilador.</span><span class="sxs-lookup"><span data-stu-id="06f82-107">If the declared type of the `params` parameter is not a single-dimensional array, compiler error [CS0225](../../misc/cs0225.md) occurs.</span></span>

<span data-ttu-id="06f82-108">Cuando se llama a un método con un parámetro `params`, se puede pasar:</span><span class="sxs-lookup"><span data-stu-id="06f82-108">When you call a method with a `params` parameter, you can pass in:</span></span>

- <span data-ttu-id="06f82-109">Una lista separada por comas de argumentos del tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="06f82-109">A comma-separated list of arguments of the type of the array elements.</span></span>
- <span data-ttu-id="06f82-110">Una matriz de argumentos del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="06f82-110">An array of arguments of the specified type.</span></span>
- <span data-ttu-id="06f82-111">Sin argumentos.</span><span class="sxs-lookup"><span data-stu-id="06f82-111">No arguments.</span></span> <span data-ttu-id="06f82-112">Si no envía ningún argumento, la longitud de la lista `params` es cero.</span><span class="sxs-lookup"><span data-stu-id="06f82-112">If you send no arguments, the length of the `params` list is zero.</span></span>

## <a name="example"></a><span data-ttu-id="06f82-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="06f82-113">Example</span></span>

<span data-ttu-id="06f82-114">En el ejemplo siguiente se muestran varias maneras de enviar argumentos a un parámetro `params`.</span><span class="sxs-lookup"><span data-stu-id="06f82-114">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="06f82-115">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="06f82-115">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="06f82-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="06f82-116">See also</span></span>

- [<span data-ttu-id="06f82-117">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="06f82-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="06f82-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="06f82-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="06f82-119">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="06f82-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="06f82-120">Parámetros de métodos</span><span class="sxs-lookup"><span data-stu-id="06f82-120">Method Parameters</span></span>](method-parameters.md)
