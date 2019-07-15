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
ms.openlocfilehash: b58730d945582ded7b76fcd5c4c65bc1dd9324da
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661452"
---
# <a name="char-c-reference"></a><span data-ttu-id="57a14-102">char (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="57a14-102">char (C# Reference)</span></span>

<span data-ttu-id="57a14-103">La palabra clave `char` se usa para declarar una instancia de la estructura <xref:System.Char?displayProperty=nameWithType> que .NET Framework usa para representar un carácter Unicode.</span><span class="sxs-lookup"><span data-stu-id="57a14-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=nameWithType> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="57a14-104">El valor de un objeto `Char` es un valor numérico de 16 bits (ordinal).</span><span class="sxs-lookup"><span data-stu-id="57a14-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>

 <span data-ttu-id="57a14-105">Los caracteres Unicode se usan para representar la mayoría de los idiomas escritos del mundo.</span><span class="sxs-lookup"><span data-stu-id="57a14-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>

|<span data-ttu-id="57a14-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="57a14-106">Type</span></span>|<span data-ttu-id="57a14-107">Intervalo</span><span class="sxs-lookup"><span data-stu-id="57a14-107">Range</span></span>|<span data-ttu-id="57a14-108">Tamaño</span><span class="sxs-lookup"><span data-stu-id="57a14-108">Size</span></span>|<span data-ttu-id="57a14-109">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="57a14-109">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="57a14-110">U+0000 a U+FFFF</span><span class="sxs-lookup"><span data-stu-id="57a14-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="57a14-111">Carácter Unicode de 16 bits</span><span class="sxs-lookup"><span data-stu-id="57a14-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="57a14-112">Literales</span><span class="sxs-lookup"><span data-stu-id="57a14-112">Literals</span></span>

<span data-ttu-id="57a14-113">Las constantes de tipo `char` pueden escribirse como literales de caracteres, secuencias de escape hexadecimal o representaciones Unicode.</span><span class="sxs-lookup"><span data-stu-id="57a14-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="57a14-114">También se pueden convertir los códigos de caracteres enteros.</span><span class="sxs-lookup"><span data-stu-id="57a14-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="57a14-115">En el siguiente ejemplo se inicializan cuatro variables `char` con el mismo carácter `X`:</span><span class="sxs-lookup"><span data-stu-id="57a14-115">In the following example four `char` variables are initialized with the same character `X`:</span></span>

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a><span data-ttu-id="57a14-116">Conversiones</span><span class="sxs-lookup"><span data-stu-id="57a14-116">Conversions</span></span>

<span data-ttu-id="57a14-117">Un `char` se puede convertir implícitamente a [ushort](../builtin-types/integral-numeric-types.md), [int](../builtin-types/integral-numeric-types.md), [uint](../builtin-types/integral-numeric-types.md), [double](../builtin-types/floating-point-numeric-types.md) o [decimal](../builtin-types/floating-point-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="57a14-117">A `char` can be implicitly converted to [ushort](../builtin-types/integral-numeric-types.md), [int](../builtin-types/integral-numeric-types.md), [uint](../builtin-types/integral-numeric-types.md), [double](../builtin-types/floating-point-numeric-types.md), or [decimal](../builtin-types/floating-point-numeric-types.md).</span></span> <span data-ttu-id="57a14-118">En cambio, no hay ninguna conversión implícita de otros tipos al tipo `char`.</span><span class="sxs-lookup"><span data-stu-id="57a14-118">However, there are no implicit conversions from other types to the `char` type.</span></span>

<span data-ttu-id="57a14-119">El tipo <xref:System.Char?displayProperty=nameWithType> proporciona varios métodos estáticos para trabajar con valores `char`.</span><span class="sxs-lookup"><span data-stu-id="57a14-119">The <xref:System.Char?displayProperty=nameWithType> type provides several static methods for working with `char` values.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="57a14-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="57a14-120">C# language specification</span></span>  

<span data-ttu-id="57a14-121">Para obtener más información, vea la sección [Tipos enteros](~/_csharplang/spec/types.md#integral-types) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="57a14-121">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="57a14-122">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="57a14-122">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="57a14-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="57a14-123">See also</span></span>

- <xref:System.Char>
- [<span data-ttu-id="57a14-124">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="57a14-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="57a14-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="57a14-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="57a14-126">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="57a14-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="57a14-127">Tipos enteros</span><span class="sxs-lookup"><span data-stu-id="57a14-127">Integral types</span></span>](../../../csharp/language-reference/builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="57a14-128">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="57a14-128">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="57a14-129">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="57a14-129">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="57a14-130">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="57a14-130">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
- [<span data-ttu-id="57a14-131">Tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="57a14-131">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)
- [<span data-ttu-id="57a14-132">Cadenas</span><span class="sxs-lookup"><span data-stu-id="57a14-132">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)
