---
title: 'Palabra clave params: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 90d224080f607cbac96514aaf5ac6d67affef9e0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713240"
---
# <a name="params-c-reference"></a><span data-ttu-id="247da-102">params (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="247da-102">params (C# Reference)</span></span>

<span data-ttu-id="247da-103">Mediante el uso de la palabra clave `params`, puede especificar un [parámetro de método](method-parameters.md) que toma un número variable de argumentos.</span><span class="sxs-lookup"><span data-stu-id="247da-103">By using the `params` keyword, you can specify a [method parameter](method-parameters.md) that takes a variable number of arguments.</span></span>

<span data-ttu-id="247da-104">Puede enviar una lista separada por comas de argumentos del tipo especificado en la declaración de parámetro o una matriz de argumentos del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="247da-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="247da-105">También puede no enviar ningún argumento.</span><span class="sxs-lookup"><span data-stu-id="247da-105">You also can send no arguments.</span></span> <span data-ttu-id="247da-106">Si no envía ningún argumento, la longitud de la lista `params` es cero.</span><span class="sxs-lookup"><span data-stu-id="247da-106">If you send no arguments, the length of the `params` list is zero.</span></span>

<span data-ttu-id="247da-107">No se permiten parámetros adicionales después de la palabra clave `params` en una declaración de método, y solo se permite una palabra clave `params` en una declaración de método.</span><span class="sxs-lookup"><span data-stu-id="247da-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>

<span data-ttu-id="247da-108">El tipo declarado del parámetro `params` debe ser una matriz unidimensional, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="247da-108">The declared type of the `params` parameter must be a single-dimensional array, as the following example shows.</span></span> <span data-ttu-id="247da-109">En caso contrario, se produce un error del compilador [CS0225](../../misc/cs0225.md).</span><span class="sxs-lookup"><span data-stu-id="247da-109">Otherwise, a compiler error [CS0225](../../misc/cs0225.md) occurs.</span></span>

## <a name="example"></a><span data-ttu-id="247da-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="247da-110">Example</span></span>

<span data-ttu-id="247da-111">En el ejemplo siguiente se muestran varias maneras de enviar argumentos a un parámetro `params`.</span><span class="sxs-lookup"><span data-stu-id="247da-111">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)] 

## <a name="c-language-specification"></a><span data-ttu-id="247da-112">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="247da-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="247da-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="247da-113">See also</span></span>

- [<span data-ttu-id="247da-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="247da-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="247da-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="247da-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="247da-116">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="247da-116">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="247da-117">Parámetros de métodos</span><span class="sxs-lookup"><span data-stu-id="247da-117">Method Parameters</span></span>](method-parameters.md)
