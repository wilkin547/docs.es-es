---
title: Palabra clave operator (Referencia de C#)
description: Cómo sobrecargar un operador de C# integrado
ms.date: 08/27/2018
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: 1e11d7767b61becc39b1158fae9cb2abe997e4bd
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44207634"
---
# <a name="operator-c-reference"></a><span data-ttu-id="06aeb-103">operator (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="06aeb-103">operator (C# Reference)</span></span>

<span data-ttu-id="06aeb-104">Use la palabra clave `operator` para sobrecargar un operador integrado o proporcionar una conversión definida por el usuario en una declaración de clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="06aeb-104">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>

<span data-ttu-id="06aeb-105">Para sobrecargar un operador en una clase o estructura personalizadas, puede crear una declaración de operador en el tipo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="06aeb-105">To overload an operator on a custom class or struct, you create an operator declaration in the corresponding type.</span></span> <span data-ttu-id="06aeb-106">La declaración del operador que sobrecarga un operador de C# integrado debe cumplir las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="06aeb-106">The operator declaration that overloads a built-in C# operator must satisfy the following rules:</span></span>

- <span data-ttu-id="06aeb-107">Incluye los modificadores `public` y `static`.</span><span class="sxs-lookup"><span data-stu-id="06aeb-107">It includes both a `public` and a `static` modifier.</span></span>
- <span data-ttu-id="06aeb-108">Incluye `operator X`, donde `X` es el nombre o símbolo del operador que está sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="06aeb-108">It includes `operator X` where `X` is the name or symbol of the operator being overloaded.</span></span>
- <span data-ttu-id="06aeb-109">Los operadores unarios tienen un parámetro y los operadores binarios tienen dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="06aeb-109">Unary operators have one parameter, and binary operators have two parameters.</span></span> <span data-ttu-id="06aeb-110">En cada caso, por lo menos un parámetro debe ser del mismo tipo que la clase o estructura que declara el operador.</span><span class="sxs-lookup"><span data-stu-id="06aeb-110">In each case, at least one parameter must be the same type as the class or struct that declares the operator.</span></span>

<span data-ttu-id="06aeb-111">Para obtener información sobre cómo definir operadores de conversión, vea los artículos sobre las palabras clave [explicit](explicit.md) e [implicit](implicit.md).</span><span class="sxs-lookup"><span data-stu-id="06aeb-111">For information about how to define conversion operators, see the [explicit](explicit.md) and [implicit](implicit.md) keyword articles.</span></span>

<span data-ttu-id="06aeb-112">Para obtener información general sobre los operadores C# que se pueden sobrecargar, vea el artículo [Operadores sobrecargables](../../programming-guide/statements-expressions-operators/overloadable-operators.md).</span><span class="sxs-lookup"><span data-stu-id="06aeb-112">For an overview of the C# operators that can be overloaded, see the [Overloadable operators](../../programming-guide/statements-expressions-operators/overloadable-operators.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="06aeb-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="06aeb-113">Example</span></span>

<span data-ttu-id="06aeb-114">En el ejemplo siguiente se define un tipo `Fraction` que representa números fraccionarios.</span><span class="sxs-lookup"><span data-stu-id="06aeb-114">The following example defines a `Fraction` type that represents fractional numbers.</span></span> <span data-ttu-id="06aeb-115">Sobrecarga los operadores `+` y `*` para realizar multiplicaciones y sumas fraccionarias, y también proporciona un operador de conversión que convierte un tipo `Fraction` en un tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="06aeb-115">It overloads the `+` and `*` operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a `Fraction` type to a `double` type.</span></span>

[!code-csharp[csrefKeywordsConversion#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="06aeb-116">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="06aeb-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="06aeb-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="06aeb-117">See also</span></span>

- [<span data-ttu-id="06aeb-118">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="06aeb-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="06aeb-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="06aeb-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="06aeb-120">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="06aeb-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="06aeb-121">implicit</span><span class="sxs-lookup"><span data-stu-id="06aeb-121">implicit</span></span>](implicit.md)
- [<span data-ttu-id="06aeb-122">explicit</span><span class="sxs-lookup"><span data-stu-id="06aeb-122">explicit</span></span>](explicit.md)
- [<span data-ttu-id="06aeb-123">Operadores sobrecargables</span><span class="sxs-lookup"><span data-stu-id="06aeb-123">Overloadable operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="06aeb-124">Cómo: Implementar conversiones definidas por el usuario entre structs</span><span class="sxs-lookup"><span data-stu-id="06aeb-124">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
