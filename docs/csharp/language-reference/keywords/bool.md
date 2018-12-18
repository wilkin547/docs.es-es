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
ms.openlocfilehash: a274083ad2e518f8f29384e51d692bcf9a9cb61e
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237251"
---
# <a name="bool-c-reference"></a><span data-ttu-id="e1aec-102">bool (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="e1aec-102">bool (C# Reference)</span></span>

<span data-ttu-id="e1aec-103">La palabra clave `bool` es un alias de <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e1aec-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e1aec-104">Se usa para declarar variables que almacenan los valores booleanos [true](true-literal.md) y [false](false-literal.md).</span><span class="sxs-lookup"><span data-stu-id="e1aec-104">It is used to declare variables to store the Boolean values: [true](true-literal.md) and [false](false-literal.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e1aec-105">Si necesita una variable booleana que también pueda tener un valor de `null`, use `bool?`.</span><span class="sxs-lookup"><span data-stu-id="e1aec-105">If you require a Boolean variable that can also have a value of `null`, use `bool?`.</span></span> <span data-ttu-id="e1aec-106">Para más información, vea la sección [Tipo bool?](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) del artículo [Uso de tipos que aceptan valores NULL](../../programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="e1aec-106">For more information, see [The bool? type](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

## <a name="literals"></a><span data-ttu-id="e1aec-107">Literales</span><span class="sxs-lookup"><span data-stu-id="e1aec-107">Literals</span></span>

<span data-ttu-id="e1aec-108">Se puede asignar un valor booleano a una variable `bool`.</span><span class="sxs-lookup"><span data-stu-id="e1aec-108">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="e1aec-109">También se puede asignar una expresión que se evalúe como `bool` a una variable `bool`.</span><span class="sxs-lookup"><span data-stu-id="e1aec-109">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

<span data-ttu-id="e1aec-110">El valor predeterminado de una variable `bool` es `false`.</span><span class="sxs-lookup"><span data-stu-id="e1aec-110">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="e1aec-111">El valor predeterminado de una variable `bool?` es `null`.</span><span class="sxs-lookup"><span data-stu-id="e1aec-111">The default value of a `bool?` variable is `null`.</span></span>

## <a name="conversions"></a><span data-ttu-id="e1aec-112">Conversiones</span><span class="sxs-lookup"><span data-stu-id="e1aec-112">Conversions</span></span>

<span data-ttu-id="e1aec-113">En C++, un valor de tipo `bool` se puede convertir en un valor de tipo `int`, es decir, `false` equivale a cero y `true` equivale a valores distintos de cero.</span><span class="sxs-lookup"><span data-stu-id="e1aec-113">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="e1aec-114">En C#, no hay ninguna conversión entre el tipo `bool` y otros tipos.</span><span class="sxs-lookup"><span data-stu-id="e1aec-114">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="e1aec-115">Por ejemplo, la siguiente instrucción `if` no es válida en C#:</span><span class="sxs-lookup"><span data-stu-id="e1aec-115">For example, the following `if` statement is invalid in C#:</span></span>

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

<span data-ttu-id="e1aec-116">Para probar una variable del tipo `int`, tendrá que compararla explícitamente con un valor, como cero, del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e1aec-116">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a><span data-ttu-id="e1aec-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e1aec-117">Example</span></span>

<span data-ttu-id="e1aec-118">En este ejemplo, se escribe un carácter desde el teclado y el programa comprueba si el carácter de entrada es una letra.</span><span class="sxs-lookup"><span data-stu-id="e1aec-118">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="e1aec-119">Si es una letra, comprueba si está en mayúsculas o minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e1aec-119">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="e1aec-120">Estas comprobaciones se realizan con <xref:System.Char.IsLetter%2A> y <xref:System.Char.IsLower%2A>; ambos devuelven el tipo `bool`:</span><span class="sxs-lookup"><span data-stu-id="e1aec-120">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="e1aec-121">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="e1aec-121">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="e1aec-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1aec-122">See also</span></span>

- [<span data-ttu-id="e1aec-123">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="e1aec-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="e1aec-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="e1aec-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="e1aec-125">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="e1aec-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="e1aec-126">Tabla de tipos enteros</span><span class="sxs-lookup"><span data-stu-id="e1aec-126">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="e1aec-127">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="e1aec-127">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="e1aec-128">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="e1aec-128">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="e1aec-129">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="e1aec-129">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  