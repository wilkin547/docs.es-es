---
title: 'Palabra clave char: referencia de C#'
ms.custom: seodec18
ms.date: 10/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 1b9f8d1bb205a6cbfe521830a11bd8878ccde991
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771803"
---
# <a name="char-c-reference"></a><span data-ttu-id="1db50-102">char (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="1db50-102">char (C# reference)</span></span>

<span data-ttu-id="1db50-103">La palabra clave de tipo `char` es un alias para el tipo de estructura de .NET <xref:System.Char?displayProperty=nameWithType> que representa un carácter Unicode UTF-16:</span><span class="sxs-lookup"><span data-stu-id="1db50-103">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character:</span></span>

|<span data-ttu-id="1db50-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="1db50-104">Type</span></span>|<span data-ttu-id="1db50-105">Intervalo</span><span class="sxs-lookup"><span data-stu-id="1db50-105">Range</span></span>|<span data-ttu-id="1db50-106">Tamaño</span><span class="sxs-lookup"><span data-stu-id="1db50-106">Size</span></span>|<span data-ttu-id="1db50-107">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="1db50-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="1db50-108">U+0000 a U+FFFF</span><span class="sxs-lookup"><span data-stu-id="1db50-108">U+0000 to U+FFFF</span></span>|<span data-ttu-id="1db50-109">16 bits</span><span class="sxs-lookup"><span data-stu-id="1db50-109">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="1db50-110">Literales</span><span class="sxs-lookup"><span data-stu-id="1db50-110">Literals</span></span>

<span data-ttu-id="1db50-111">Las constantes de tipo `char` pueden escribirse como literales de caracteres, secuencias de escape hexadecimal o representaciones Unicode.</span><span class="sxs-lookup"><span data-stu-id="1db50-111">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="1db50-112">También puede convertir un código de carácter entero en el valor `char` correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1db50-112">You can also cast an integral character code into the corresponding `char` value.</span></span> <span data-ttu-id="1db50-113">En el siguiente ejemplo, los cuatro elementos de una matriz de `char` se inicializan con el mismo carácter `X`:</span><span class="sxs-lookup"><span data-stu-id="1db50-113">In the following example, the four elements of an array of `char` are initialized with the same character `X`:</span></span>

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a><span data-ttu-id="1db50-114">Conversiones</span><span class="sxs-lookup"><span data-stu-id="1db50-114">Conversions</span></span>

<span data-ttu-id="1db50-115">El tipo `char` se puede convertir implícitamente en los tipos [enteros](../builtin-types/integral-numeric-types.md) siguientes: `ushort`, `int`, `uint`, `long` y `ulong`.</span><span class="sxs-lookup"><span data-stu-id="1db50-115">The `char` type is implicitly convertible to the following [integral](../builtin-types/integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="1db50-116">También se puede convertir implícitamente en los tipos numéricos de [punto flotante](../builtin-types/floating-point-numeric-types.md) integrados: `float`, `double` y `decimal`.</span><span class="sxs-lookup"><span data-stu-id="1db50-116">It's also implicitly convertible to the built-in [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="1db50-117">Se puede convertir explícitamente en los tipos enteros `sbyte`, `byte` y `short`.</span><span class="sxs-lookup"><span data-stu-id="1db50-117">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="1db50-118">No hay ninguna conversión implícita de otros tipos al tipo `char`.</span><span class="sxs-lookup"><span data-stu-id="1db50-118">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="1db50-119">Sin embargo, cualquier tipo numérico [entero](../builtin-types/integral-numeric-types.md) o de [punto flotante](../builtin-types/floating-point-numeric-types.md) es implícitamente convertible a `char`.</span><span class="sxs-lookup"><span data-stu-id="1db50-119">However, any [integral](../builtin-types/integral-numeric-types.md) or [floating-point](../builtin-types/floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1db50-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="1db50-120">C# language specification</span></span>

<span data-ttu-id="1db50-121">Para obtener más información, consulte la sección [Tipos enteros](~/_csharplang/spec/types.md#integral-types) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="1db50-121">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1db50-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="1db50-122">See also</span></span>

- [<span data-ttu-id="1db50-123">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="1db50-123">C# reference</span></span>](../index.md)
- [<span data-ttu-id="1db50-124">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="1db50-124">C# keywords</span></span>](./index.md)
- [<span data-ttu-id="1db50-125">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="1db50-125">Built-in types table</span></span>](./built-in-types-table.md)
- [<span data-ttu-id="1db50-126">Cadenas</span><span class="sxs-lookup"><span data-stu-id="1db50-126">Strings</span></span>](../../programming-guide/strings/index.md)
- <xref:System.Char?displayProperty=nameWithType>
