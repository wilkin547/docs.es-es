---
title: bool (palabra clave) - Referencia de C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 880e8c0b733afbf5c09f543e06a5a4a858d2b456
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771844"
---
# <a name="bool-c-reference"></a><span data-ttu-id="1253f-102">bool (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="1253f-102">bool (C# Reference)</span></span>

<span data-ttu-id="1253f-103">La palabra clave `bool` es un alias de <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1253f-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1253f-104">Se usa para declarar variables que almacenan los valores booleanos [true](true-literal.md) y [false](false-literal.md).</span><span class="sxs-lookup"><span data-stu-id="1253f-104">It is used to declare variables to store the Boolean values: [true](true-literal.md) and [false](false-literal.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1253f-105">Use el tipo `bool?`, si tiene que admitir la lógica de tres valores, por ejemplo, cuando trabaja con bases de datos que admiten un tipo booleano de tres valores.</span><span class="sxs-lookup"><span data-stu-id="1253f-105">Use the `bool?` type, if you need to support the three-valued logic, for example, when you work with databases that support a three-valued Boolean type.</span></span> <span data-ttu-id="1253f-106">En el caso de los operandos `bool?`, los operadores predefinidos `&` y `|` admiten la lógica de tres valores.</span><span class="sxs-lookup"><span data-stu-id="1253f-106">For the `bool?` operands, the predefined `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="1253f-107">Para más información, consulte la sección [Operadores lógicos booleanos que aceptan valores NULL](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) del artículo [Operadores lógicos booleanos](../operators/boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="1253f-107">For more information, see the [Nullable Boolean logical operators](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../operators/boolean-logical-operators.md) article.</span></span>

## <a name="literals"></a><span data-ttu-id="1253f-108">Literales</span><span class="sxs-lookup"><span data-stu-id="1253f-108">Literals</span></span>

<span data-ttu-id="1253f-109">Se puede asignar un valor booleano a una variable `bool`.</span><span class="sxs-lookup"><span data-stu-id="1253f-109">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="1253f-110">También se puede asignar una expresión que se evalúe como `bool` a una variable `bool`.</span><span class="sxs-lookup"><span data-stu-id="1253f-110">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

<span data-ttu-id="1253f-111">El valor predeterminado de una variable `bool` es `false`.</span><span class="sxs-lookup"><span data-stu-id="1253f-111">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="1253f-112">El valor predeterminado de una variable `bool?` es `null`.</span><span class="sxs-lookup"><span data-stu-id="1253f-112">The default value of a `bool?` variable is `null`.</span></span>

## <a name="conversions"></a><span data-ttu-id="1253f-113">Conversiones</span><span class="sxs-lookup"><span data-stu-id="1253f-113">Conversions</span></span>

<span data-ttu-id="1253f-114">En C++, un valor de tipo `bool` se puede convertir en un valor de tipo `int`, es decir, `false` equivale a cero y `true` equivale a valores distintos de cero.</span><span class="sxs-lookup"><span data-stu-id="1253f-114">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="1253f-115">En C#, no hay ninguna conversión entre el tipo `bool` y otros tipos.</span><span class="sxs-lookup"><span data-stu-id="1253f-115">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="1253f-116">Por ejemplo, la siguiente instrucción `if` no es válida en C#:</span><span class="sxs-lookup"><span data-stu-id="1253f-116">For example, the following `if` statement is invalid in C#:</span></span>

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

<span data-ttu-id="1253f-117">Para probar una variable del tipo `int`, tendrá que compararla explícitamente con un valor, como cero, del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1253f-117">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a><span data-ttu-id="1253f-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1253f-118">Example</span></span>

<span data-ttu-id="1253f-119">En este ejemplo, se escribe un carácter desde el teclado y el programa comprueba si el carácter de entrada es una letra.</span><span class="sxs-lookup"><span data-stu-id="1253f-119">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="1253f-120">Si es una letra, comprueba si está en mayúsculas o minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1253f-120">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="1253f-121">Estas comprobaciones se realizan con <xref:System.Char.IsLetter%2A> y <xref:System.Char.IsLower%2A>; ambos devuelven el tipo `bool`:</span><span class="sxs-lookup"><span data-stu-id="1253f-121">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="1253f-122">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="1253f-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="1253f-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="1253f-123">See also</span></span>

- [<span data-ttu-id="1253f-124">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="1253f-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1253f-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="1253f-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1253f-126">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="1253f-126">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="1253f-127">Tipos enteros</span><span class="sxs-lookup"><span data-stu-id="1253f-127">Integral types</span></span>](../builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="1253f-128">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="1253f-128">Built-In Types Table</span></span>](./built-in-types-table.md)
