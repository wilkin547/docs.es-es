---
title: 'Palabra clave char: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 754c04bfc3b4090906420d55d55e51606b72f187
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605953"
---
# <a name="char-c-reference"></a><span data-ttu-id="1d230-102">char (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="1d230-102">char (C# Reference)</span></span>

<span data-ttu-id="1d230-103">La palabra clave `char` se usa para declarar una instancia de la estructura <xref:System.Char?displayProperty=nameWithType> que .NET Framework usa para representar un carácter Unicode.</span><span class="sxs-lookup"><span data-stu-id="1d230-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=nameWithType> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="1d230-104">El valor de un objeto `Char` es un valor numérico de 16 bits (ordinal).</span><span class="sxs-lookup"><span data-stu-id="1d230-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>

 <span data-ttu-id="1d230-105">Los caracteres Unicode se usan para representar la mayoría de los idiomas escritos del mundo.</span><span class="sxs-lookup"><span data-stu-id="1d230-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>

|<span data-ttu-id="1d230-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="1d230-106">Type</span></span>|<span data-ttu-id="1d230-107">Intervalo</span><span class="sxs-lookup"><span data-stu-id="1d230-107">Range</span></span>|<span data-ttu-id="1d230-108">Tamaño</span><span class="sxs-lookup"><span data-stu-id="1d230-108">Size</span></span>|<span data-ttu-id="1d230-109">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="1d230-109">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="1d230-110">U+0000 a U+FFFF</span><span class="sxs-lookup"><span data-stu-id="1d230-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="1d230-111">Carácter Unicode de 16 bits</span><span class="sxs-lookup"><span data-stu-id="1d230-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="1d230-112">Literales</span><span class="sxs-lookup"><span data-stu-id="1d230-112">Literals</span></span>

<span data-ttu-id="1d230-113">Las constantes de tipo `char` pueden escribirse como literales de caracteres, secuencias de escape hexadecimal o representaciones Unicode.</span><span class="sxs-lookup"><span data-stu-id="1d230-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="1d230-114">También se pueden convertir los códigos de caracteres enteros.</span><span class="sxs-lookup"><span data-stu-id="1d230-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="1d230-115">En el siguiente ejemplo se inicializan cuatro variables `char` con el mismo carácter `X`:</span><span class="sxs-lookup"><span data-stu-id="1d230-115">In the following example four `char` variables are initialized with the same character `X`:</span></span>

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a><span data-ttu-id="1d230-116">Conversiones</span><span class="sxs-lookup"><span data-stu-id="1d230-116">Conversions</span></span>

<span data-ttu-id="1d230-117">Un `char` se puede convertir implícitamente a [ushort](../builtin-types/integral-numeric-types.md), [int](../builtin-types/integral-numeric-types.md), [uint](../builtin-types/integral-numeric-types.md), [double](../builtin-types/floating-point-numeric-types.md) o [decimal](../builtin-types/floating-point-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="1d230-117">A `char` can be implicitly converted to [ushort](../builtin-types/integral-numeric-types.md), [int](../builtin-types/integral-numeric-types.md), [uint](../builtin-types/integral-numeric-types.md), [double](../builtin-types/floating-point-numeric-types.md), or [decimal](../builtin-types/floating-point-numeric-types.md).</span></span> <span data-ttu-id="1d230-118">En cambio, no hay ninguna conversión implícita de otros tipos al tipo `char`.</span><span class="sxs-lookup"><span data-stu-id="1d230-118">However, there are no implicit conversions from other types to the `char` type.</span></span>

<span data-ttu-id="1d230-119">El tipo <xref:System.Char?displayProperty=nameWithType> proporciona varios métodos estáticos para trabajar con valores `char`.</span><span class="sxs-lookup"><span data-stu-id="1d230-119">The <xref:System.Char?displayProperty=nameWithType> type provides several static methods for working with `char` values.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1d230-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="1d230-120">C# language specification</span></span>  

<span data-ttu-id="1d230-121">Para obtener más información, vea la sección [Tipos enteros](~/_csharplang/spec/types.md#integral-types) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="1d230-121">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="1d230-122">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="1d230-122">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d230-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d230-123">See also</span></span>

- <xref:System.Char>
- [<span data-ttu-id="1d230-124">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="1d230-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1d230-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="1d230-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1d230-126">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="1d230-126">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="1d230-127">Tipos enteros</span><span class="sxs-lookup"><span data-stu-id="1d230-127">Integral types</span></span>](../builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="1d230-128">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="1d230-128">Built-In Types Table</span></span>](./built-in-types-table.md)
- [<span data-ttu-id="1d230-129">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="1d230-129">Implicit Numeric Conversions Table</span></span>](./implicit-numeric-conversions-table.md)
- [<span data-ttu-id="1d230-130">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="1d230-130">Explicit Numeric Conversions Table</span></span>](./explicit-numeric-conversions-table.md)
- [<span data-ttu-id="1d230-131">Tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="1d230-131">Nullable Types</span></span>](../../programming-guide/nullable-types/index.md)
- [<span data-ttu-id="1d230-132">Cadenas</span><span class="sxs-lookup"><span data-stu-id="1d230-132">Strings</span></span>](../../programming-guide/strings/index.md)
