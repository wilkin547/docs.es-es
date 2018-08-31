---
title: Palabra clave operator (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: c3bfada235993670bf158fe9803a09707b2b3251
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2018
ms.locfileid: "42929877"
---
# <a name="operator-c-reference"></a><span data-ttu-id="ba43a-102">operator (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="ba43a-102">operator (C# Reference)</span></span>

<span data-ttu-id="ba43a-103">Use la palabra clave `operator` para sobrecargar un operador integrado o proporcionar una conversión definida por el usuario en una declaración de clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="ba43a-103">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>

## <a name="example"></a><span data-ttu-id="ba43a-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba43a-104">Example</span></span>

<span data-ttu-id="ba43a-105">La siguiente es una clase muy simplificada para números fraccionarios.</span><span class="sxs-lookup"><span data-stu-id="ba43a-105">The following is a very simplified class for fractional numbers.</span></span> <span data-ttu-id="ba43a-106">Sobrecarga los operadores `+` y `*` para realizar multiplicaciones y sumas fraccionarias, y también proporciona un operador de conversión que convierte un tipo `Fraction` en un tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="ba43a-106">It overloads the `+` and `*` operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a `Fraction` type to a `double` type.</span></span>

[!code-csharp[csrefKeywordsConversion#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="ba43a-107">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="ba43a-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ba43a-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba43a-108">See also</span></span>

- [<span data-ttu-id="ba43a-109">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="ba43a-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ba43a-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ba43a-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ba43a-111">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="ba43a-111">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="ba43a-112">implicit</span><span class="sxs-lookup"><span data-stu-id="ba43a-112">implicit</span></span>](implicit.md)
- [<span data-ttu-id="ba43a-113">explicit</span><span class="sxs-lookup"><span data-stu-id="ba43a-113">explicit</span></span>](explicit.md)
- [<span data-ttu-id="ba43a-114">Cómo: Implementar conversiones definidas por el usuario entre structs</span><span class="sxs-lookup"><span data-stu-id="ba43a-114">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
