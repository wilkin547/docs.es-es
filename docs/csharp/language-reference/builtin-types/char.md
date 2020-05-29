---
title: 'Tipo char: Referencia de C#'
ms.date: 05/11/2020
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: f771626e9777deab30e798559d847615d6124e6d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205781"
---
# <a name="char-c-reference"></a><span data-ttu-id="b9eea-102">char (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="b9eea-102">char (C# reference)</span></span>

<span data-ttu-id="b9eea-103">La palabra clave de tipo `char` es un alias para el tipo de estructura de .NET <xref:System.Char?displayProperty=nameWithType> que representa un carácter Unicode UTF-16.</span><span class="sxs-lookup"><span data-stu-id="b9eea-103">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character.</span></span>

|<span data-ttu-id="b9eea-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="b9eea-104">Type</span></span>|<span data-ttu-id="b9eea-105">Intervalo</span><span class="sxs-lookup"><span data-stu-id="b9eea-105">Range</span></span>|<span data-ttu-id="b9eea-106">Tamaño</span><span class="sxs-lookup"><span data-stu-id="b9eea-106">Size</span></span>|<span data-ttu-id="b9eea-107">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="b9eea-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="b9eea-108">U+0000 a U+FFFF</span><span class="sxs-lookup"><span data-stu-id="b9eea-108">U+0000 to U+FFFF</span></span>|<span data-ttu-id="b9eea-109">16 bits</span><span class="sxs-lookup"><span data-stu-id="b9eea-109">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

<span data-ttu-id="b9eea-110">El valor predeterminado del tipo `char` es `\0`, es decir, U+0000.</span><span class="sxs-lookup"><span data-stu-id="b9eea-110">The default value of the `char` type is `\0`, that is, U+0000.</span></span>

<span data-ttu-id="b9eea-111">El tipo `char` admite operadores de [comparación](../operators/comparison-operators.md), [igualdad](../operators/equality-operators.md), [incremento](../operators/arithmetic-operators.md#increment-operator-) y [decremento](../operators/arithmetic-operators.md#decrement-operator---).</span><span class="sxs-lookup"><span data-stu-id="b9eea-111">The `char` type supports [comparison](../operators/comparison-operators.md), [equality](../operators/equality-operators.md), [increment](../operators/arithmetic-operators.md#increment-operator-), and [decrement](../operators/arithmetic-operators.md#decrement-operator---) operators.</span></span> <span data-ttu-id="b9eea-112">Además, en el caso de los operandos `char`, los operadores [aritméticos](../operators/arithmetic-operators.md) y [lógicos bit a bit](../operators/bitwise-and-shift-operators.md) realizan una operación en los códigos de caracteres correspondientes y producen el resultado del tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="b9eea-112">Moreover, for `char` operands, [arithmetic](../operators/arithmetic-operators.md) and [bitwise logical](../operators/bitwise-and-shift-operators.md) operators perform an operation on the corresponding character codes and produce the result of the `int` type.</span></span>

<span data-ttu-id="b9eea-113">El tipo [string](reference-types.md#the-string-type) representa el texto como una secuencia de valores `char`.</span><span class="sxs-lookup"><span data-stu-id="b9eea-113">The [string](reference-types.md#the-string-type) type represents text as a sequence of `char` values.</span></span>

## <a name="literals"></a><span data-ttu-id="b9eea-114">Literales</span><span class="sxs-lookup"><span data-stu-id="b9eea-114">Literals</span></span>

<span data-ttu-id="b9eea-115">Puede especificar un valor de `char` con:</span><span class="sxs-lookup"><span data-stu-id="b9eea-115">You can specify a `char` value with:</span></span>

- <span data-ttu-id="b9eea-116">un literal de carácter.</span><span class="sxs-lookup"><span data-stu-id="b9eea-116">a character literal.</span></span>
- <span data-ttu-id="b9eea-117">una secuencia de escape Unicode, que es `\u` seguido de la representación hexadecimal de cuatro símbolos de un código de carácter.</span><span class="sxs-lookup"><span data-stu-id="b9eea-117">a Unicode escape sequence, which is `\u` followed by the four-symbol hexadecimal representation of a character code.</span></span>
- <span data-ttu-id="b9eea-118">una secuencia de escape hexadecimal, que es `\x` seguido de la representación hexadecimal de un código de carácter.</span><span class="sxs-lookup"><span data-stu-id="b9eea-118">a hexadecimal escape sequence, which is `\x` followed by the hexadecimal representation of a character code.</span></span>

[!code-csharp-interactive[char literals](snippets/CharType.cs#Literals)]

<span data-ttu-id="b9eea-119">Como se muestra en el ejemplo anterior, también puede convertir el valor de un código de carácter en el valor de `char` correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b9eea-119">As the preceding example shows, you can also cast the value of a character code into the corresponding `char` value.</span></span>

> [!NOTE]
> <span data-ttu-id="b9eea-120">En el caso de una secuencia de escape Unicode, debe especificar los cuatro dígitos hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="b9eea-120">In the case of a Unicode escape sequence, you must specify all four hexadecimal digits.</span></span> <span data-ttu-id="b9eea-121">Es decir, `\u006A` es una secuencia de escape válida, mientras que `\u06A` y `\u6A` no son válidas.</span><span class="sxs-lookup"><span data-stu-id="b9eea-121">That is, `\u006A` is a valid escape sequence, while `\u06A` and `\u6A` are not valid.</span></span>
>
> <span data-ttu-id="b9eea-122">En el caso de una secuencia de escape hexadecimal, puede omitir los ceros a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="b9eea-122">In the case of a hexadecimal escape sequence, you can omit the leading zeros.</span></span> <span data-ttu-id="b9eea-123">Es decir, las secuencias de escape `\x006A`, `\x06A`y `\x6A` son válidas y se corresponden con el mismo carácter.</span><span class="sxs-lookup"><span data-stu-id="b9eea-123">That is, the `\x006A`, `\x06A`, and `\x6A` escape sequences are valid and correspond to the same character.</span></span>

## <a name="conversions"></a><span data-ttu-id="b9eea-124">Conversiones</span><span class="sxs-lookup"><span data-stu-id="b9eea-124">Conversions</span></span>

<span data-ttu-id="b9eea-125">El tipo `char` se puede convertir implícitamente en los tipos [enteros](integral-numeric-types.md) siguientes: `ushort`, `int`, `uint`, `long` y `ulong`.</span><span class="sxs-lookup"><span data-stu-id="b9eea-125">The `char` type is implicitly convertible to the following [integral](integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="b9eea-126">También se puede convertir implícitamente en los tipos numéricos de [punto flotante](floating-point-numeric-types.md) integrados: `float`, `double` y `decimal`.</span><span class="sxs-lookup"><span data-stu-id="b9eea-126">It's also implicitly convertible to the built-in [floating-point](floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="b9eea-127">Se puede convertir explícitamente en los tipos enteros `sbyte`, `byte` y `short`.</span><span class="sxs-lookup"><span data-stu-id="b9eea-127">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="b9eea-128">No hay ninguna conversión implícita de otros tipos al tipo `char`.</span><span class="sxs-lookup"><span data-stu-id="b9eea-128">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="b9eea-129">Sin embargo, cualquier tipo numérico [entero](integral-numeric-types.md) o de [punto flotante](floating-point-numeric-types.md) es implícitamente convertible a `char`.</span><span class="sxs-lookup"><span data-stu-id="b9eea-129">However, any [integral](integral-numeric-types.md) or [floating-point](floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b9eea-130">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="b9eea-130">C# language specification</span></span>

<span data-ttu-id="b9eea-131">Para obtener más información, consulte la sección [Tipos enteros](~/_csharplang/spec/types.md#integral-types) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="b9eea-131">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b9eea-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9eea-132">See also</span></span>

- [<span data-ttu-id="b9eea-133">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="b9eea-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="b9eea-134">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="b9eea-134">Value types</span></span>](value-types.md)
- [<span data-ttu-id="b9eea-135">Cadenas</span><span class="sxs-lookup"><span data-stu-id="b9eea-135">Strings</span></span>](../../programming-guide/strings/index.md)
- <xref:System.Text.Rune?displayProperty=nameWithType>
- [<span data-ttu-id="b9eea-136">Codificación de caracteres de .NET</span><span class="sxs-lookup"><span data-stu-id="b9eea-136">Character encoding in .NET</span></span>](../../../standard/base-types/character-encoding-introduction.md)
