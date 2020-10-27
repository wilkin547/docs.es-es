---
description: Obtenga información sobre el tipo booleano integrado en C#.
title: 'bool (tipo): Referencia de C#'
ms.date: 11/26/2019
f1_keywords:
- bool
- bool_CSharpKeyword
- "true"
- "false"
- true_CSharpKeyword
- false_CSharpKeyword
helpviewer_keywords:
- bool data type [C#]
- Boolean [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: e74fd76fcb19faa5860e48140da0fbd3db4afa47
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471894"
---
# <a name="bool-c-reference"></a><span data-ttu-id="c31d6-103">bool (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c31d6-103">bool (C# reference)</span></span>

<span data-ttu-id="c31d6-104">La palabra clave de tipo `bool` es un alias para el tipo de estructura de .NET <xref:System.Boolean?displayProperty=nameWithType> que representa un valor booleano que puede ser `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="c31d6-104">The `bool` type keyword is an alias for the .NET <xref:System.Boolean?displayProperty=nameWithType> structure type that represents a Boolean value, which can be either `true` or `false`.</span></span>

<span data-ttu-id="c31d6-105">Para realizar operaciones lógicas con valores del tipo `bool`, use operadores [lógicos booleanos](../operators/boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="c31d6-105">To perform logical operations with values of the `bool` type, use [Boolean logical](../operators/boolean-logical-operators.md) operators.</span></span> <span data-ttu-id="c31d6-106">El tipo `bool` es el tipo de resultado de los operadores de [comparación](../operators/comparison-operators.md) e [igualdad](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="c31d6-106">The `bool` type is the result type of [comparison](../operators/comparison-operators.md) and [equality](../operators/equality-operators.md) operators.</span></span> <span data-ttu-id="c31d6-107">Una expresión `bool` puede ser una expresión condicional de control en las instrucciones [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md) y [for](../keywords/for.md), así como en el [operador condicional `?:`](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c31d6-107">A `bool` expression can be a controlling conditional expression in the [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md), and [for](../keywords/for.md) statements and in the [conditional operator `?:`](../operators/conditional-operator.md).</span></span>

<span data-ttu-id="c31d6-108">El valor predeterminado del tipo `bool` es `false`.</span><span class="sxs-lookup"><span data-stu-id="c31d6-108">The default value of the `bool` type is `false`.</span></span>

## <a name="literals"></a><span data-ttu-id="c31d6-109">Literales</span><span class="sxs-lookup"><span data-stu-id="c31d6-109">Literals</span></span>

<span data-ttu-id="c31d6-110">Puede usar los literales `true` y `false` para inicializar una variable `bool` o para pasar un valor `bool`:</span><span class="sxs-lookup"><span data-stu-id="c31d6-110">You can use the `true` and `false` literals to initialize a `bool` variable or to pass a `bool` value:</span></span>

[!code-csharp-interactive[bool literals](snippets/shared/BoolType.cs#Literals)]

## <a name="three-valued-boolean-logic"></a><span data-ttu-id="c31d6-111">Lógica booleana de tres valores</span><span class="sxs-lookup"><span data-stu-id="c31d6-111">Three-valued Boolean logic</span></span>

<span data-ttu-id="c31d6-112">Use el tipo `bool?` que acepta valores NULL si tiene que admitir la lógica de tres valores (por ejemplo, si trabaja con bases de datos que admiten un tipo booleano de tres valores).</span><span class="sxs-lookup"><span data-stu-id="c31d6-112">Use the nullable `bool?` type, if you need to support the three-valued logic, for example, when you work with databases that support a three-valued Boolean type.</span></span> <span data-ttu-id="c31d6-113">En el caso de los operandos `bool?`, los operadores predefinidos `&` y `|` admiten la lógica de tres valores.</span><span class="sxs-lookup"><span data-stu-id="c31d6-113">For the `bool?` operands, the predefined `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="c31d6-114">Para más información, consulte la sección [Operadores lógicos booleanos que aceptan valores NULL](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) del artículo [Operadores lógicos booleanos](../operators/boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="c31d6-114">For more information, see the [Nullable Boolean logical operators](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../operators/boolean-logical-operators.md) article.</span></span>

<span data-ttu-id="c31d6-115">Para más información sobre los tipos de valor que admiten un valor NULL, consulte [Tipos de valor que admiten un valor NULL](nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="c31d6-115">For more information about nullable value types, see [Nullable value types](nullable-value-types.md).</span></span>

## <a name="conversions"></a><span data-ttu-id="c31d6-116">Conversiones</span><span class="sxs-lookup"><span data-stu-id="c31d6-116">Conversions</span></span>

<span data-ttu-id="c31d6-117">C# solo proporciona dos conversiones que implican al tipo `bool`.</span><span class="sxs-lookup"><span data-stu-id="c31d6-117">C# provides only two conversions that involve the `bool` type.</span></span> <span data-ttu-id="c31d6-118">Son una conversión implícita al tipo `bool?` que acepta valores NULL correspondiente y una conversión explícita del tipo `bool?`.</span><span class="sxs-lookup"><span data-stu-id="c31d6-118">Those are an implicit conversion to the corresponding nullable `bool?` type and an explicit conversion from the `bool?` type.</span></span> <span data-ttu-id="c31d6-119">Sin embargo, .NET proporciona métodos adicionales que se pueden usar para realizar una conversión al tipo `bool`, o bien revertirla.</span><span class="sxs-lookup"><span data-stu-id="c31d6-119">However, .NET provides additional methods that you can use to convert to or from the `bool` type.</span></span> <span data-ttu-id="c31d6-120">Para obtener más información, vea la sección [Convertir a y desde valores booleanos](/dotnet/api/system.boolean#converting-to-and-from-boolean-values) de la página de referencia de la API <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c31d6-120">For more information, see the [Converting to and from Boolean values](/dotnet/api/system.boolean#converting-to-and-from-boolean-values) section of the <xref:System.Boolean?displayProperty=nameWithType> API reference page.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c31d6-121">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c31d6-121">C# language specification</span></span>

<span data-ttu-id="c31d6-122">Para obtener más información, vea la sección [Tipo bool](~/_csharplang/spec/types.md#the-bool-type) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="c31d6-122">For more information, see [The bool type](~/_csharplang/spec/types.md#the-bool-type) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c31d6-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="c31d6-123">See also</span></span>

- [<span data-ttu-id="c31d6-124">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="c31d6-124">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c31d6-125">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="c31d6-125">Value types</span></span>](value-types.md)
- [<span data-ttu-id="c31d6-126">operadores true y false</span><span class="sxs-lookup"><span data-stu-id="c31d6-126">true and false operators</span></span>](../operators/true-false-operators.md)
