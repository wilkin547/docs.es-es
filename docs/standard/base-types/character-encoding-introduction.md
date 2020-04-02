---
title: Introducción a la codificación de caracteres en .NET
description: Obtenga información sobre la codificación y descodificación de caracteres en .NET.
ms.date: 03/09/2020
no-loc:
- Rune
- char
- string
dev_langs:
- csharp
helpviewer_keywords:
- encoding, understanding
ms.openlocfilehash: 34b1577f8bcea80c1f41b6f9605bf47d132fdb4f
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134440"
---
# <a name="character-encoding-in-net"></a><span data-ttu-id="8273b-103">Codificación de caracteres de .NET</span><span class="sxs-lookup"><span data-stu-id="8273b-103">Character encoding in .NET</span></span>

<span data-ttu-id="8273b-104">En este artículo se proporciona una introducción a los sistemas de codificación de caracteres que se usan con .NET.</span><span class="sxs-lookup"><span data-stu-id="8273b-104">This article provides an introduction to character encoding systems that are used by .NET.</span></span> <span data-ttu-id="8273b-105">Se explica cómo funcionan los tipos <xref:System.String>, <xref:System.Char>, <xref:System.Text.Rune> y <xref:System.Globalization.StringInfo> con Unicode, UTF-16 y UTF-8.</span><span class="sxs-lookup"><span data-stu-id="8273b-105">The article explains how the <xref:System.String>, <xref:System.Char>, <xref:System.Text.Rune>, and <xref:System.Globalization.StringInfo> types work with Unicode, UTF-16, and UTF-8.</span></span>

<span data-ttu-id="8273b-106">El término *carácter* se usa aquí en el sentido general de *lo que un lector percibe como un solo elemento de presentación*.</span><span class="sxs-lookup"><span data-stu-id="8273b-106">The term *character* is used here in the general sense of *what a reader perceives as a single display element*.</span></span> <span data-ttu-id="8273b-107">Algunos ejemplos comunes son la letra "a", el símbolo "@" y el emoji "🐂".</span><span class="sxs-lookup"><span data-stu-id="8273b-107">Common examples are the letter "a", the symbol "@", and the emoji "🐂".</span></span> <span data-ttu-id="8273b-108">A veces, lo que parece un carácter consta en realidad de varios elementos de visualización independientes, como se explica en la sección sobre los [clústeres de grafemas](#grapheme-clusters).</span><span class="sxs-lookup"><span data-stu-id="8273b-108">Sometimes what looks like one character is actually composed of multiple independent display elements, as the section on [grapheme clusters](#grapheme-clusters) explains.</span></span>

## <a name="the-string-and-char-types"></a><span data-ttu-id="8273b-109">Tipos de cadena y carácter</span><span class="sxs-lookup"><span data-stu-id="8273b-109">The string and char types</span></span>

<span data-ttu-id="8273b-110">Una instancia de la clase [string](xref:System.String) representa texto.</span><span class="sxs-lookup"><span data-stu-id="8273b-110">An instance of the [string](xref:System.String) class represents some text.</span></span> <span data-ttu-id="8273b-111">Una instancia de `string` es de forma lógica una secuencia de valores de 16 bits, cada uno de los cuales es una instancia del struct [char](xref:System.Char).</span><span class="sxs-lookup"><span data-stu-id="8273b-111">A `string` is logically a sequence of 16-bit values, each of which is an instance of the [char](xref:System.Char) struct.</span></span> <span data-ttu-id="8273b-112">La propiedad [string.Length](xref:System.String.Length) devuelve el número de instancias de `char` en la instancia `string`.</span><span class="sxs-lookup"><span data-stu-id="8273b-112">The [string.Length](xref:System.String.Length) property returns the number of `char` instances in the `string` instance.</span></span>

<span data-ttu-id="8273b-113">La función de ejemplo siguiente imprime los valores en notación hexadecimal de todas las instancias de `char` en una instancia de `string`:</span><span class="sxs-lookup"><span data-stu-id="8273b-113">The following sample function prints out the values in hexadecimal notation of all the `char` instances in a `string`:</span></span>

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/PrintStringChars.cs" id="SnippetPrintChars":::

<span data-ttu-id="8273b-114">Pase la cadena "Hello" a esta función y obtendrá la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="8273b-114">Pass the string "Hello" to this function, and you get the following output:</span></span>

```csharp
PrintChars("Hello");
```

```output
"Hello".Length = 5
s[0] = 'H' ('\u0048')
s[1] = 'e' ('\u0065')
s[2] = 'l' ('\u006c')
s[3] = 'l' ('\u006c')
s[4] = 'o' ('\u006f')
```

<span data-ttu-id="8273b-115">Cada carácter se representa mediante un solo valor de `char`.</span><span class="sxs-lookup"><span data-stu-id="8273b-115">Each character is represented by a single `char` value.</span></span> <span data-ttu-id="8273b-116">Ese patrón se aplica a la mayoría de los idiomas del mundo.</span><span class="sxs-lookup"><span data-stu-id="8273b-116">That pattern holds true for most of the world's languages.</span></span> <span data-ttu-id="8273b-117">Por ejemplo, esta es la salida de dos caracteres chinos que suenan como *nǐ hǎo* y significan *Hello*:</span><span class="sxs-lookup"><span data-stu-id="8273b-117">For example, here's the output for two Chinese characters that sound like *nǐ hǎo* and mean *Hello*:</span></span>

```csharp
PrintChars("你好");
```

```output
"你好".Length = 2
s[0] = '你' ('\u4f60')
s[1] = '好' ('\u597d')
```

<span data-ttu-id="8273b-118">Sin embargo, en algunos lenguajes y en algunos símbolos y emoji, se necesitan dos instancias de `char` para representar un único carácter.</span><span class="sxs-lookup"><span data-stu-id="8273b-118">However, for some languages and for some symbols and emoji, it takes two `char` instances to represent a single character.</span></span> <span data-ttu-id="8273b-119">Por ejemplo, compare los caracteres y las instancias de `char` de la palabra que significa *Osage* en el idioma Osage:</span><span class="sxs-lookup"><span data-stu-id="8273b-119">For example, compare the characters and `char` instances in the word that means *Osage* in the Osage language:</span></span>

```csharp
PrintChars("𐓏𐓘𐓻𐓘𐓻𐓟 𐒻𐓟");
```

```output
"𐓏𐓘𐓻𐓘𐓻𐓟 𐒻𐓟".Length = 17
s[0] = '�' ('\ud801')
s[1] = '�' ('\udccf')
s[2] = '�' ('\ud801')
s[3] = '�' ('\udcd8')
s[4] = '�' ('\ud801')
s[5] = '�' ('\udcfb')
s[6] = '�' ('\ud801')
s[7] = '�' ('\udcd8')
s[8] = '�' ('\ud801')
s[9] = '�' ('\udcfb')
s[10] = '�' ('\ud801')
s[11] = '�' ('\udcdf')
s[12] = ' ' ('\u0020')
s[13] = '�' ('\ud801')
s[14] = '�' ('\udcbb')
s[15] = '�' ('\ud801')
s[16] = '�' ('\udcdf')
```

<span data-ttu-id="8273b-120">En el ejemplo anterior, cada carácter excepto el espacio se representa mediante dos instancias de `char`.</span><span class="sxs-lookup"><span data-stu-id="8273b-120">In the preceding example, each character except the space is represented by two `char` instances.</span></span>

<span data-ttu-id="8273b-121">Un solo emoji Unicode se representa mediante dos instancias de `char`, tal como se ilustra en el ejemplo siguiente, que muestra un emoji de buey:</span><span class="sxs-lookup"><span data-stu-id="8273b-121">A single Unicode emoji is also represented by two `char`s, as seen in the following example showing an ox emoji:</span></span>

```
"🐂".Length = 2
s[0] = '�' ('\ud83d')
s[1] = '�' ('\udc02')
```

<span data-ttu-id="8273b-122">En estos ejemplos se muestra que el valor de `string.Length`, que indica el número de instancias de `char`, no indica necesariamente el número de caracteres mostrados.</span><span class="sxs-lookup"><span data-stu-id="8273b-122">These examples show that the value of `string.Length`, which indicates the number of `char` instances, doesn't necessarily indicate the number of displayed characters.</span></span> <span data-ttu-id="8273b-123">Una sola instancia de `char` no representa necesariamente un carácter.</span><span class="sxs-lookup"><span data-stu-id="8273b-123">A single `char` instance by itself doesn't necessarily represent a character.</span></span>

<span data-ttu-id="8273b-124">Los pares de `char` que se asignan a un único carácter se denominan *pares suplentes*.</span><span class="sxs-lookup"><span data-stu-id="8273b-124">The `char` pairs that map to a single character are called *surrogate pairs*.</span></span> <span data-ttu-id="8273b-125">Para entender cómo funcionan, debe comprender la codificación Unicode y UTF-16.</span><span class="sxs-lookup"><span data-stu-id="8273b-125">To understand how they work, you need to understand Unicode and UTF-16 encoding.</span></span>

## <a name="unicode-code-points"></a><span data-ttu-id="8273b-126">Puntos de código Unicode</span><span class="sxs-lookup"><span data-stu-id="8273b-126">Unicode code points</span></span>

<span data-ttu-id="8273b-127">Unicode es un estándar de codificación internacional que se usa en varias plataformas y con varios idiomas y scripts.</span><span class="sxs-lookup"><span data-stu-id="8273b-127">Unicode is an international encoding standard for use on various platforms and with various languages and scripts.</span></span>

<span data-ttu-id="8273b-128">El estándar Unicode define más de 1,1 millones de [puntos de código](https://www.unicode.org/glossary/#code_point).</span><span class="sxs-lookup"><span data-stu-id="8273b-128">The Unicode Standard defines over 1.1 million [code points](https://www.unicode.org/glossary/#code_point).</span></span> <span data-ttu-id="8273b-129">Un punto de código es un valor entero comprendido entre 0 y `U+10FFFF` (decimal 1.114.111).</span><span class="sxs-lookup"><span data-stu-id="8273b-129">A code point is an integer value that can range from 0 to `U+10FFFF` (decimal 1,114,111).</span></span> <span data-ttu-id="8273b-130">Algunos puntos de código se asignan a letras, símbolos o emoji.</span><span class="sxs-lookup"><span data-stu-id="8273b-130">Some code points are assigned to letters, symbols, or emoji.</span></span> <span data-ttu-id="8273b-131">Otros se asignan a acciones que controlan el modo en que se muestra el texto o los caracteres, como el avance a una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="8273b-131">Others are assigned to actions that control how text or characters are displayed, such as advance to a new line.</span></span> <span data-ttu-id="8273b-132">Muchos puntos de código todavía no se han asignado.</span><span class="sxs-lookup"><span data-stu-id="8273b-132">Many code points are not yet assigned.</span></span>

<span data-ttu-id="8273b-133">Estos son algunos ejemplos de asignaciones de puntos de código, con vínculos a gráficos Unicode en los que aparecen:</span><span class="sxs-lookup"><span data-stu-id="8273b-133">Here are some examples of code point assignments, with links to Unicode charts in which they appear:</span></span>

|<span data-ttu-id="8273b-134">Decimal</span><span class="sxs-lookup"><span data-stu-id="8273b-134">Decimal</span></span>|<span data-ttu-id="8273b-135">Hex</span><span class="sxs-lookup"><span data-stu-id="8273b-135">Hex</span></span>       |<span data-ttu-id="8273b-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8273b-136">Example</span></span>|<span data-ttu-id="8273b-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="8273b-137">Description</span></span>|
|------:|----------|-------|-----------|
|<span data-ttu-id="8273b-138">10</span><span class="sxs-lookup"><span data-stu-id="8273b-138">10</span></span>     | `U+000A` |<span data-ttu-id="8273b-139">N/D</span><span class="sxs-lookup"><span data-stu-id="8273b-139">N/A</span></span>| [<span data-ttu-id="8273b-140">LINE FEED</span><span class="sxs-lookup"><span data-stu-id="8273b-140">LINE FEED</span></span>](https://www.unicode.org/charts/PDF/U0000.pdf) |
|<span data-ttu-id="8273b-141">65</span><span class="sxs-lookup"><span data-stu-id="8273b-141">65</span></span>     | `U+0061` | <span data-ttu-id="8273b-142">a</span><span class="sxs-lookup"><span data-stu-id="8273b-142">a</span></span> | [<span data-ttu-id="8273b-143">LATIN SMALL LETTER A</span><span class="sxs-lookup"><span data-stu-id="8273b-143">LATIN SMALL LETTER A</span></span>](https://www.unicode.org/charts/PDF/U0000.pdf) |
|<span data-ttu-id="8273b-144">562</span><span class="sxs-lookup"><span data-stu-id="8273b-144">562</span></span>    | `U+0232` | <span data-ttu-id="8273b-145">Ȳ</span><span class="sxs-lookup"><span data-stu-id="8273b-145">Ȳ</span></span> | [<span data-ttu-id="8273b-146">LATIN CAPITAL LETTER Y WITH MACRON</span><span class="sxs-lookup"><span data-stu-id="8273b-146">LATIN CAPITAL LETTER Y WITH MACRON</span></span>](https://www.unicode.org/charts/PDF/U0180.pdf) |
|<span data-ttu-id="8273b-147">68.675</span><span class="sxs-lookup"><span data-stu-id="8273b-147">68,675</span></span> | `U+10C43`| <span data-ttu-id="8273b-148">𐱃</span><span class="sxs-lookup"><span data-stu-id="8273b-148">𐱃</span></span> | [<span data-ttu-id="8273b-149">OLD TURKIC LETTER ORKHON AT</span><span class="sxs-lookup"><span data-stu-id="8273b-149">OLD TURKIC LETTER ORKHON AT</span></span>](https://www.unicode.org/charts/PDF/U10C00.pdf) |
|<span data-ttu-id="8273b-150">127.801</span><span class="sxs-lookup"><span data-stu-id="8273b-150">127,801</span></span>| `U+1F339`| <span data-ttu-id="8273b-151">🌹</span><span class="sxs-lookup"><span data-stu-id="8273b-151">🌹</span></span> | [<span data-ttu-id="8273b-152">ROSE emoji</span><span class="sxs-lookup"><span data-stu-id="8273b-152">ROSE emoji</span></span>](https://www.unicode.org/charts/PDF/U1F300.pdf) |

<span data-ttu-id="8273b-153">Normalmente se hace referencia a los puntos de código mediante la sintaxis `U+xxxx`, donde `xxxx` es el valor entero con codificación hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="8273b-153">Code points are customarily referred to by using the syntax `U+xxxx`, where `xxxx` is the hex-encoded integer value.</span></span>

<span data-ttu-id="8273b-154">Dentro del intervalo completo de puntos de código hay dos subintervalos:</span><span class="sxs-lookup"><span data-stu-id="8273b-154">Within the full range of code points there are two subranges:</span></span>

* <span data-ttu-id="8273b-155">El **plano básico multilingüe (BMP)** en el intervalo `U+0000..U+FFFF`.</span><span class="sxs-lookup"><span data-stu-id="8273b-155">The **Basic Multilingual Plane (BMP)** in the range `U+0000..U+FFFF`.</span></span> <span data-ttu-id="8273b-156">Este intervalo de 16 bits proporciona 65 536 puntos de código, suficientes para cubrir la mayoría de los sistemas de escritura del mundo.</span><span class="sxs-lookup"><span data-stu-id="8273b-156">This 16-bit range provides 65,536 code points, enough to cover the majority of the world's writing systems.</span></span>
* <span data-ttu-id="8273b-157">Los **puntos de código suplementarios** en el intervalo `U+10000..U+10FFFF`.</span><span class="sxs-lookup"><span data-stu-id="8273b-157">**Supplementary code points** in the range `U+10000..U+10FFFF`.</span></span> <span data-ttu-id="8273b-158">Este intervalo de 21 bits proporciona más de un millón de puntos de código adicionales que se pueden usar con idiomas menos conocidos y otros fines, como los emoji.</span><span class="sxs-lookup"><span data-stu-id="8273b-158">This 21-bit range provides more than a million additional code points that can be used for less well-known languages and other purposes such as emojis.</span></span>

<span data-ttu-id="8273b-159">En el diagrama siguiente se ilustra la relación entre el BMP y los puntos de código suplementarios.</span><span class="sxs-lookup"><span data-stu-id="8273b-159">The following diagram illustrates the relationship between the BMP and the supplementary code points.</span></span>

:::image type="content" source="media/character-encoding-introduction/bmp-and-supplementary.svg" alt-text="BMP y puntos de código suplementarios":::

## <a name="utf-16-code-units"></a><span data-ttu-id="8273b-161">Unidades de código UTF-16</span><span class="sxs-lookup"><span data-stu-id="8273b-161">UTF-16 code units</span></span>

<span data-ttu-id="8273b-162">El formato de transformación Unicode de 16 bits ([UTF-16](https://www.unicode.org/faq/utf_bom.html#UTF16)) es un sistema de codificación de caracteres que emplea *unidades de código* de 16 bits para representar puntos de código Unicode.</span><span class="sxs-lookup"><span data-stu-id="8273b-162">16-bit Unicode Transformation Format ([UTF-16](https://www.unicode.org/faq/utf_bom.html#UTF16)) is a character encoding system that uses 16-bit *code units* to represent Unicode code points.</span></span> <span data-ttu-id="8273b-163">.NET usa UTF-16 para codificar el texto de una instancia de `string`.</span><span class="sxs-lookup"><span data-stu-id="8273b-163">.NET uses UTF-16 to encode the text in a `string`.</span></span> <span data-ttu-id="8273b-164">Una instancia de `char` representa una unidad de código de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="8273b-164">A `char` instance represents a 16-bit code unit.</span></span>

<span data-ttu-id="8273b-165">Una sola unidad de código de 16 bits puede representar cualquier punto de código en el intervalo de 16 bits del plano básico multilingüe.</span><span class="sxs-lookup"><span data-stu-id="8273b-165">A single 16-bit code unit can represent any code point in the 16-bit range of the Basic Multilingual Plane.</span></span> <span data-ttu-id="8273b-166">Sin embargo, un punto de código en el intervalo suplementario necesita dos instancias de `char`.</span><span class="sxs-lookup"><span data-stu-id="8273b-166">But for a code point in the supplementary range, two `char` instances are needed.</span></span>

## <a name="surrogate-pairs"></a><span data-ttu-id="8273b-167">Pares suplentes</span><span class="sxs-lookup"><span data-stu-id="8273b-167">Surrogate pairs</span></span>

<span data-ttu-id="8273b-168">La conversión de dos valores de 16 bits en un único valor de 21 bits se facilita mediante un intervalo especial denominado *puntos de código suplentes*, de `U+D800` a `U+DFFF` (decimal 55.296 a 57.343), ambos incluidos.</span><span class="sxs-lookup"><span data-stu-id="8273b-168">The translation of two 16-bit values to a single 21-bit value is facilitated by a special range called the *surrogate code points*, from `U+D800` to `U+DFFF` (decimal 55,296 to 57,343), inclusive.</span></span>

<span data-ttu-id="8273b-169">En el diagrama siguiente se ilustra la relación entre el BMP y los puntos de código suplentes.</span><span class="sxs-lookup"><span data-stu-id="8273b-169">The following diagram illustrates the relationship between the BMP and the surrogate code points.</span></span>

:::image type="content" source="media/character-encoding-introduction/bmp-and-surrogate.svg" alt-text="BMP y los puntos de código suplentes":::

<span data-ttu-id="8273b-171">Cuando un punto de código *suplente superior* (`U+D800..U+DBFF`) va seguido inmediatamente por un punto de código *suplente inferior* (`U+DC00..U+DFFF`), el par se interpreta como un punto de código suplementario mediante la fórmula siguiente:</span><span class="sxs-lookup"><span data-stu-id="8273b-171">When a *high surrogate* code point (`U+D800..U+DBFF`) is immediately followed by a *low surrogate* code point (`U+DC00..U+DFFF`), the pair is interpreted as a supplementary code point by using the following formula:</span></span>

```
code point = 0x10000 +
  ((high surrogate code point - 0xD800) * 0x0400) +
  (low surrogate code point - 0xDC00)
```

<span data-ttu-id="8273b-172">Esta es la misma fórmula, pero con notación decimal:</span><span class="sxs-lookup"><span data-stu-id="8273b-172">Here's the same formula using decimal notation:</span></span>

```
code point = 65,536 +
  ((high surrogate code point - 55,296) * 1,024) +
  (low surrogate code point - 56,320)
```

<span data-ttu-id="8273b-173">Un punto de código suplente *superior* no tiene un valor numérico mayor que un punto de código suplente *inferior*.</span><span class="sxs-lookup"><span data-stu-id="8273b-173">A *high* surrogate code point doesn't have a higher number value than a *low* surrogate code point.</span></span> <span data-ttu-id="8273b-174">El punto de código suplente superior se denomina así porque se usa para calcular los 11 bits de orden superior del intervalo completo de puntos de código de 21 bits.</span><span class="sxs-lookup"><span data-stu-id="8273b-174">The high surrogate code point is called "high" because it's used to calculate the higher-order 11 bits of the full 21-bit code point range.</span></span> <span data-ttu-id="8273b-175">El punto de código suplente inferior se usa para calcular los 10 bits de orden inferior.</span><span class="sxs-lookup"><span data-stu-id="8273b-175">The low surrogate code point is used to calculate the lower-order 10 bits.</span></span>

<span data-ttu-id="8273b-176">Por ejemplo, el punto de código real que corresponde al par suplente `0xD83C` y `0xDF39` se calcula de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="8273b-176">For example, the actual code point that corresponds to the surrogate pair `0xD83C` and `0xDF39`  is computed as follows:</span></span>

```
actual = 0x10000 + ((0xD83C - 0xD800) * 0x0400) + (0xDF39 - 0xDC00)
       = 0x10000 + (          0x003C  * 0x0400) +           0x0339
       = 0x10000 +                      0xF000  +           0x0339
       = 0x1F339
```

<span data-ttu-id="8273b-177">Este es el mismo cálculo, pero con notación decimal:</span><span class="sxs-lookup"><span data-stu-id="8273b-177">Here's the same calculation using decimal notation:</span></span>

```
actual =  65,536 + ((55,356 - 55,296) * 1,024) + (57,145 - 56320)
       =  65,536 + (              60  * 1,024) +             825
       =  65,536 +                     61,440  +             825
       = 127,801
```

<span data-ttu-id="8273b-178">En el ejemplo anterior se muestra que `"\ud83c\udf39"` es la codificación UTF-16 del punto de código `U+1F339 ROSE ('🌹')` mencionado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8273b-178">The preceding example demonstrates that `"\ud83c\udf39"` is the UTF-16 encoding of the `U+1F339 ROSE ('🌹')` code point mentioned earlier.</span></span>

## <a name="unicode-scalar-values"></a><span data-ttu-id="8273b-179">Valores escalares Unicode</span><span class="sxs-lookup"><span data-stu-id="8273b-179">Unicode scalar values</span></span>

<span data-ttu-id="8273b-180">El término [valor escalar Unicode](https://www.unicode.org/glossary/#unicode_scalar_value) hace referencia a todos los puntos de código distintos de los puntos de código suplentes.</span><span class="sxs-lookup"><span data-stu-id="8273b-180">The term [Unicode scalar value](https://www.unicode.org/glossary/#unicode_scalar_value) refers to all code points other than the surrogate code points.</span></span> <span data-ttu-id="8273b-181">En otras palabras, un valor escalar es cualquier punto de código al que se le asigna un carácter o se le puede asignar en el futuro.</span><span class="sxs-lookup"><span data-stu-id="8273b-181">In other words, a scalar value is any code point that is assigned a character or can be assigned a character in the future.</span></span> <span data-ttu-id="8273b-182">Aquí "carácter" hace referencia a todo lo que se puede asignar a un punto de código, lo que incluye cosas como acciones que controlan cómo se muestra el texto o los caracteres.</span><span class="sxs-lookup"><span data-stu-id="8273b-182">"Character" here refers to anything that can be assigned to a code point, which includes such things as actions that control how text or characters are displayed.</span></span>

<span data-ttu-id="8273b-183">En el diagrama siguiente se muestran los puntos de código de valor escalar.</span><span class="sxs-lookup"><span data-stu-id="8273b-183">The following diagram illustrates the scalar value code points.</span></span>

:::image type="content" source="media/character-encoding-introduction/scalar-values.svg" alt-text="Valores escalares":::

### <a name="the-opno-locrune-type-as-a-scalar-value"></a><span data-ttu-id="8273b-185">El tipo Rune como un valor escalar.</span><span class="sxs-lookup"><span data-stu-id="8273b-185">The Rune type as a scalar value</span></span>

<span data-ttu-id="8273b-186">A partir de .NET Core 3.0, el tipo <xref:System.Text.Rune?displayProperty=fullName> representa un valor escalar Unicode.</span><span class="sxs-lookup"><span data-stu-id="8273b-186">Beginning with .NET Core 3.0, the <xref:System.Text.Rune?displayProperty=fullName> type represents a Unicode scalar value.</span></span> <span data-ttu-id="8273b-187">**`Rune` no está disponible en .NET Core 2. x o .NET Framework 4.x.**</span><span class="sxs-lookup"><span data-stu-id="8273b-187">**`Rune` is not available in .NET Core 2.x or .NET Framework 4.x.**</span></span>

<span data-ttu-id="8273b-188">Los constructores `Rune` validan que la instancia resultante sea un valor escalar Unicode válido; de lo contrario, inician una excepción.</span><span class="sxs-lookup"><span data-stu-id="8273b-188">The `Rune` constructors validate that the resulting instance is a valid Unicode scalar value, otherwise they throw an exception.</span></span> <span data-ttu-id="8273b-189">En el ejemplo siguiente se muestra código que crea una instancia correcta de las instancias de `Rune` porque la entrada representa valores escalares válidos:</span><span class="sxs-lookup"><span data-stu-id="8273b-189">The following example shows code that successfully instantiates `Rune` instances because the input represents valid scalar values:</span></span>

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetValid":::

<span data-ttu-id="8273b-190">En el siguiente ejemplo se produce una excepción porque el punto de código está en el intervalo suplente y no es parte de un par suplente:</span><span class="sxs-lookup"><span data-stu-id="8273b-190">The following example throws an exception because the code point is in the surrogate range and isn't part of a surrogate pair:</span></span>

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidSurrogate":::

<span data-ttu-id="8273b-191">En el siguiente ejemplo se produce una excepción porque el punto de código está por encima del intervalo suplementario:</span><span class="sxs-lookup"><span data-stu-id="8273b-191">The following example throws an exception because the code point is beyond the supplementary range:</span></span>

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidHigh":::

### <a name="opno-locrune-usage-example-changing-letter-case"></a><span data-ttu-id="8273b-192">Ejemplo de uso de Rune: cambio de las mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="8273b-192">Rune usage example: changing letter case</span></span>

<span data-ttu-id="8273b-193">Una API que toma una instancia de `char` y da por supuesto que trabaja con un punto de código que es un valor escalar no funciona correctamente si `char` procede de un par suplente.</span><span class="sxs-lookup"><span data-stu-id="8273b-193">An API that takes a `char` and assumes it is working with a code point that is a scalar value doesn't work correctly if the `char` is from a surrogate pair.</span></span> <span data-ttu-id="8273b-194">Por ejemplo, considere el siguiente método que llama a <xref:System.Char.ToUpperInvariant%2A?displayProperty=nameWithType> en cada char en una instancia de string:</span><span class="sxs-lookup"><span data-stu-id="8273b-194">For example, consider the following method that calls <xref:System.Char.ToUpperInvariant%2A?displayProperty=nameWithType> on each char in a string:</span></span>

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetBadExample":::

<span data-ttu-id="8273b-195">Si string de `input` contiene la letra minúscula `er` de Deseret (`𐑉`), este código no lo convertirá a mayúsculas (`𐐡`).</span><span class="sxs-lookup"><span data-stu-id="8273b-195">If the `input` string contains the lowercase Deseret letter `er` (`𐑉`), this code won't convert it to uppercase (`𐐡`).</span></span> <span data-ttu-id="8273b-196">El código llama a `char.ToUpperInvariant` por separado en cada punto de código suplente, `U+D801` y `U+DC49`.</span><span class="sxs-lookup"><span data-stu-id="8273b-196">The code calls `char.ToUpperInvariant` separately on each surrogate code point, `U+D801` and `U+DC49`.</span></span> <span data-ttu-id="8273b-197">Sin embargo, `U+D801` no tiene suficiente información para identificarlo como una letra minúscula, por lo que `char.ToUpperInvariant` lo deja así.</span><span class="sxs-lookup"><span data-stu-id="8273b-197">But `U+D801` doesn't have enough information by itself to identify it as a lowercase letter, so `char.ToUpperInvariant` leaves it alone.</span></span> <span data-ttu-id="8273b-198">Y trata `U+DC49` de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="8273b-198">And it handles `U+DC49` the same way.</span></span> <span data-ttu-id="8273b-199">El resultado es que la "𐑉" minúscula de la instancia de string de `input` no se convierte a "𐐡" mayúscula.</span><span class="sxs-lookup"><span data-stu-id="8273b-199">The result is that lowercase '𐑉' in the `input` string doesn't get converted to uppercase '𐐡'.</span></span>

<span data-ttu-id="8273b-200">A continuación se muestran dos opciones para convertir correctamente una instancia de string a mayúsculas:</span><span class="sxs-lookup"><span data-stu-id="8273b-200">Here are two options for correctly converting a string to uppercase:</span></span>

* <span data-ttu-id="8273b-201">Llame a <xref:System.String.ToUpperInvariant%2A?displayProperty=nameWithType> en la instancia de string de entrada en lugar de recorrer en iteración `char` mediante `char`.</span><span class="sxs-lookup"><span data-stu-id="8273b-201">Call <xref:System.String.ToUpperInvariant%2A?displayProperty=nameWithType> on the input string rather than iterating `char`-by-`char`.</span></span> <span data-ttu-id="8273b-202">El método `string.ToUpperInvariant` tiene acceso a ambas partes de cada par suplente, por lo que puede tratar correctamente todos los puntos de código Unicode.</span><span class="sxs-lookup"><span data-stu-id="8273b-202">The `string.ToUpperInvariant` method has access to both parts of each surrogate pair, so it can handle all Unicode code points correctly.</span></span>
* <span data-ttu-id="8273b-203">Recorra en iteración los valores escalares Unicode como instancias de `Rune` y no de `char`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="8273b-203">Iterate through the Unicode scalar values as `Rune` instances instead of `char` instances, as shown in the following example.</span></span> <span data-ttu-id="8273b-204">Dado que una instancia de `Rune` es un valor escalar Unicode válido, se puede pasar a las API que esperan operar en un valor escalar.</span><span class="sxs-lookup"><span data-stu-id="8273b-204">Since a `Rune` instance is a valid Unicode scalar value, it can be passed to APIs that expect to operate on a scalar value.</span></span> <span data-ttu-id="8273b-205">Por ejemplo, al llamar a <xref:System.Text.Rune.ToUpperInvariant%2A?displayProperty=nameWithType>, como se ilustra en el ejemplo siguiente, se muestran los resultados correctos:</span><span class="sxs-lookup"><span data-stu-id="8273b-205">For example, calling <xref:System.Text.Rune.ToUpperInvariant%2A?displayProperty=nameWithType> as shown in the following example gives correct results:</span></span>

  :::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetGoodExample":::

### <a name="other-opno-locrune-apis"></a><span data-ttu-id="8273b-206">Otras API de Rune</span><span class="sxs-lookup"><span data-stu-id="8273b-206">Other Rune APIs</span></span>

<span data-ttu-id="8273b-207">El tipo `Rune` expone las analogías de muchas de las API de `char`.</span><span class="sxs-lookup"><span data-stu-id="8273b-207">The `Rune` type exposes analogs of many of the `char` APIs.</span></span> <span data-ttu-id="8273b-208">Por ejemplo, los métodos siguientes reflejan las API estáticas en el tipo `char`:</span><span class="sxs-lookup"><span data-stu-id="8273b-208">For example, the following methods mirror static APIs on the `char` type:</span></span>

* <xref:System.Text.Rune.IsLetter%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.IsWhiteSpace%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.IsLetterOrDigit%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.GetUnicodeCategory%2A?displayProperty=nameWithType>

<span data-ttu-id="8273b-209">Para obtener el valor escalar sin formato de una instancia de `Rune`, utilice la propiedad <xref:System.Text.Rune.Value%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8273b-209">To get the raw scalar value from a `Rune` instance, use the <xref:System.Text.Rune.Value%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="8273b-210">Para volver a convertir una instancia de `Rune` en una secuencia de instancias de `char`, use <xref:System.Text.Rune.ToString%2A?displayProperty=nameWithType> o el método <xref:System.Text.Rune.EncodeToUtf16%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8273b-210">To convert a `Rune` instance back to a sequence of `char`s, use <xref:System.Text.Rune.ToString%2A?displayProperty=nameWithType> or the <xref:System.Text.Rune.EncodeToUtf16%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="8273b-211">Dado que cualquier valor escalar Unicode se puede representar con una sola instancia de `char` o mediante un par suplente, cualquier instancia de `Rune` se puede representar como máximo con 2 instancias de `char`.</span><span class="sxs-lookup"><span data-stu-id="8273b-211">Since any Unicode scalar value is representable by a single `char` or by a surrogate pair, any `Rune` instance can be represented by at most 2 `char` instances.</span></span> <span data-ttu-id="8273b-212">Use <xref:System.Text.Rune.Utf16SequenceLength%2A?displayProperty=nameWithType> para ver el número de instancias de `char` necesarias para representar una instancia de `Rune`.</span><span class="sxs-lookup"><span data-stu-id="8273b-212">Use <xref:System.Text.Rune.Utf16SequenceLength%2A?displayProperty=nameWithType> to see how many `char` instances are required to represent a `Rune` instance.</span></span>

<span data-ttu-id="8273b-213">Para más información sobre el tipo `Rune` de .NET, consulte la referencia de API [`Rune`](xref:System.Text.Rune).</span><span class="sxs-lookup"><span data-stu-id="8273b-213">For more information about the .NET `Rune` type, see the [`Rune` API reference](xref:System.Text.Rune).</span></span>

## <a name="grapheme-clusters"></a><span data-ttu-id="8273b-214">Clústeres de grafemas</span><span class="sxs-lookup"><span data-stu-id="8273b-214">Grapheme clusters</span></span>

<span data-ttu-id="8273b-215">Lo que parece un carácter podría ser el resultado de una combinación de varios puntos de código, por lo que un término más descriptivo que se usa a menudo en lugar de "carácter" es [clúster de grafemas](https://www.unicode.org/glossary/#grapheme_cluster).</span><span class="sxs-lookup"><span data-stu-id="8273b-215">What looks like one character might result from a combination of multiple code points, so a more descriptive term that is often used in place of "character" is [grapheme cluster](https://www.unicode.org/glossary/#grapheme_cluster).</span></span> <span data-ttu-id="8273b-216">El término equivalente en .NET es [elemento de texto](xref:System.Globalization.StringInfo.GetTextElementEnumerator%2A).</span><span class="sxs-lookup"><span data-stu-id="8273b-216">The equivalent term in .NET is [text element](xref:System.Globalization.StringInfo.GetTextElementEnumerator%2A).</span></span>

<span data-ttu-id="8273b-217">Tenga en cuenta las instancias de `string` "a", "á".</span><span class="sxs-lookup"><span data-stu-id="8273b-217">Consider the `string` instances "a", "á".</span></span> <span data-ttu-id="8273b-218">"á" y "`👩🏽‍🚒`".</span><span class="sxs-lookup"><span data-stu-id="8273b-218">"á", and "`👩🏽‍🚒`".</span></span> <span data-ttu-id="8273b-219">Si el sistema operativo las trata como se especifica en el estándar Unicode, cada una de estas instancias de `string` aparece como un solo elemento de texto o clúster de grafemas.</span><span class="sxs-lookup"><span data-stu-id="8273b-219">If your operating system handles them as specified by the Unicode standard, each of these `string` instances appears as a single text element or grapheme cluster.</span></span> <span data-ttu-id="8273b-220">Sin embargo, las dos últimas están representadas por más de un punto de código de valor escalar.</span><span class="sxs-lookup"><span data-stu-id="8273b-220">But the last two are represented by more than one scalar value code point.</span></span>

* <span data-ttu-id="8273b-221">La instancia "a" de string está representada por un valor escalar y contiene una instancia de `char`.</span><span class="sxs-lookup"><span data-stu-id="8273b-221">The string "a" is represented by one scalar value and contains one `char` instance.</span></span>

  * `U+0061 LATIN SMALL LETTER A`

* <span data-ttu-id="8273b-222">La instancia "á" de string está representada por un valor escalar y contiene una instancia de `char`.</span><span class="sxs-lookup"><span data-stu-id="8273b-222">The string "á" is represented by one scalar value and contains one `char` instance.</span></span>

  * `U+00E1 LATIN SMALL LETTER E WITH ACUTE`

* <span data-ttu-id="8273b-223">La instancia "á" de string parece igual que "á" pero está representada por dos valores escalares y contiene dos instancias de `char`.</span><span class="sxs-lookup"><span data-stu-id="8273b-223">The string "á" looks the same as "á" but is represented by two scalar values and contains two `char` instances.</span></span>

  * `U+0065 LATIN SMALL LETTER A`
  * `U+0301 COMBINING ACUTE ACCENT`

* <span data-ttu-id="8273b-224">Por último, la instancia "`👩🏽‍🚒`" de string está representada por cuatro valores y contiene siete instancias de `char`.</span><span class="sxs-lookup"><span data-stu-id="8273b-224">Finally, the string "`👩🏽‍🚒`" is represented by four scalar values and contains seven `char` instances.</span></span>

  * <span data-ttu-id="8273b-225">`U+1F469 WOMAN` (intervalo suplementario, requiere un par suplente)</span><span class="sxs-lookup"><span data-stu-id="8273b-225">`U+1F469 WOMAN` (supplementary range, requires a surrogate pair)</span></span>
  * <span data-ttu-id="8273b-226">`U+1F3FD EMOJI MODIFIER FITZPATRICK TYPE-4` (intervalo suplementario, requiere un par suplente)</span><span class="sxs-lookup"><span data-stu-id="8273b-226">`U+1F3FD EMOJI MODIFIER FITZPATRICK TYPE-4` (supplementary range, requires a surrogate pair)</span></span>
  * `U+200D ZERO WIDTH JOINER`
  * <span data-ttu-id="8273b-227">`U+1F692 FIRE ENGINE` (intervalo suplementario, requiere un par suplente)</span><span class="sxs-lookup"><span data-stu-id="8273b-227">`U+1F692 FIRE ENGINE` (supplementary range, requires a surrogate pair)</span></span>

<span data-ttu-id="8273b-228">En algunos de los ejemplos anteriores, como el de la combinación del modificador del acento o el modificador del tono de piel, el punto de código no se muestra como un elemento independiente en la pantalla,</span><span class="sxs-lookup"><span data-stu-id="8273b-228">In some of the preceding examples - such as the combining accent modifier or the skin tone modifier - the code point does not display as a standalone element on the screen.</span></span> <span data-ttu-id="8273b-229">sino que sirve para modificar el aspecto de un elemento de texto que venía antes.</span><span class="sxs-lookup"><span data-stu-id="8273b-229">Rather, it serves to modify the appearance of a text element that came before it.</span></span> <span data-ttu-id="8273b-230">En estos ejemplos se muestra que puede tomar varios valores escalares para componer lo que consideramos un solo "carácter" o un "clúster de grafemas".</span><span class="sxs-lookup"><span data-stu-id="8273b-230">These examples show that it might take multiple scalar values to make up what we think of as a single "character," or "grapheme cluster."</span></span>

<span data-ttu-id="8273b-231">Para enumerar los clústeres de grafemas de una instancia de `string`, use la clase <xref:System.Globalization.StringInfo> como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="8273b-231">To enumerate the grapheme clusters of a `string`, use the <xref:System.Globalization.StringInfo> class as shown in the following example.</span></span> <span data-ttu-id="8273b-232">Si está familiarizado con Swift, el tipo `StringInfo` de .NET es conceptualmente similar al tipo `character` de [Swift](https://developer.apple.com/documentation/swift/character).</span><span class="sxs-lookup"><span data-stu-id="8273b-232">If you're familiar with Swift, the .NET `StringInfo` type is conceptually similar to [Swift's `character` type](https://developer.apple.com/documentation/swift/character).</span></span>

### <a name="example-count-opno-locchar-opno-locrune-and-text-element-instances"></a><span data-ttu-id="8273b-233">Ejemplo: recuento de instancias de elementos char, Rune y de texto</span><span class="sxs-lookup"><span data-stu-id="8273b-233">Example: count char, Rune, and text element instances</span></span>

<span data-ttu-id="8273b-234">En las API de .NET, un clúster de grafemas se conoce como *elemento de texto*.</span><span class="sxs-lookup"><span data-stu-id="8273b-234">In .NET APIs, a grapheme cluster is called a *text element*.</span></span> <span data-ttu-id="8273b-235">El método siguiente muestra las diferencias entre las instancias de elementos `char`, `Rune` y de texto en una instancia de `string`:</span><span class="sxs-lookup"><span data-stu-id="8273b-235">The following method demonstrates the differences between `char`, `Rune`, and text element instances in a `string`:</span></span>

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCountMethod":::

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCallCountMethod":::

<span data-ttu-id="8273b-236">Si ejecuta este código en .NET Framework o .NET Core 3.1 o una versión anterior, el recuento de elementos de texto para el emoji muestra `4`.</span><span class="sxs-lookup"><span data-stu-id="8273b-236">If you run this code in .NET Framework or .NET Core 3.1 or earlier, the text element count for the emoji shows `4`.</span></span> <span data-ttu-id="8273b-237">Esto se debe a un error en la clase `StringInfo` que se ha corregido en .NET 5.</span><span class="sxs-lookup"><span data-stu-id="8273b-237">That is due to a bug in the `StringInfo` class that is fixed in .NET 5.</span></span>

### <a name="example-splitting-opno-locstring-instances"></a><span data-ttu-id="8273b-238">Ejemplo: división de las instancias de string</span><span class="sxs-lookup"><span data-stu-id="8273b-238">Example: splitting string instances</span></span>

<span data-ttu-id="8273b-239">Al dividir las instancias de `string`, evite dividir los pares suplentes y los clústeres de grafemas.</span><span class="sxs-lookup"><span data-stu-id="8273b-239">When splitting `string` instances, avoid splitting surrogate pairs and grapheme clusters.</span></span> <span data-ttu-id="8273b-240">Considere el siguiente ejemplo de código incorrecto, que intenta insertar saltos de línea cada 10 caracteres en una instancia de string:</span><span class="sxs-lookup"><span data-stu-id="8273b-240">Consider the following example of incorrect code, which intends to insert line breaks every 10 characters in a string:</span></span>

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetBadExample":::

<span data-ttu-id="8273b-241">Dado que este código enumera instancias de `char`, un par suplente que abarca un límite de 10 instancias de `char` se dividirá y una nueva línea se insertará entre ellas.</span><span class="sxs-lookup"><span data-stu-id="8273b-241">Because this code enumerates `char` instances, a surrogate pair that happens to straddle a 10-`char` boundary will be split and a newline injected between them.</span></span> <span data-ttu-id="8273b-242">Esta inserción introduce daños en los datos, porque los puntos de código suplentes solo son significativos como pares.</span><span class="sxs-lookup"><span data-stu-id="8273b-242">This insertion introduces data corruption, because surrogate code points are meaningful only as pairs.</span></span>

<span data-ttu-id="8273b-243">No se elimina la posibilidad de daños en los datos si se enumeran instancias de `Rune` (valores escalares) en lugar de instancias de `char`.</span><span class="sxs-lookup"><span data-stu-id="8273b-243">The potential for data corruption isn't eliminated if you enumerate `Rune` instances (scalar values) instead of `char` instances.</span></span> <span data-ttu-id="8273b-244">Un conjunto de instancias de `Rune` podría constituir un clúster de grafemas que abarca un límite de 10 instancias de `char`.</span><span class="sxs-lookup"><span data-stu-id="8273b-244">A set of `Rune` instances might make up a grapheme cluster that straddles a 10-`char` boundary.</span></span> <span data-ttu-id="8273b-245">Si el conjunto de clústeres de grafemas está dividido, no se podrá interpretar correctamente.</span><span class="sxs-lookup"><span data-stu-id="8273b-245">If the grapheme cluster set is split up, it can't be interpreted correctly.</span></span>

<span data-ttu-id="8273b-246">Lo mejor sería romper la instancia de string mediante el recuento de clústeres de grafemas, o elementos de texto, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8273b-246">A better approach is to break the string by counting grapheme clusters, or text elements, as in the following example:</span></span>

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetGoodExample":::

<span data-ttu-id="8273b-247">Como se indicó anteriormente, sin embargo, en implementaciones de .NET distintas de .NET 5, la clase `StringInfo` podría tratar de forma incorrecta algunos clústeres de grafemas.</span><span class="sxs-lookup"><span data-stu-id="8273b-247">As noted earlier, however, in implementations of .NET other than .NET 5, the `StringInfo` class might handle some grapheme clusters incorrectly.</span></span>

## <a name="utf-8-and-utf-32"></a><span data-ttu-id="8273b-248">UTF-8 y UTF-32</span><span class="sxs-lookup"><span data-stu-id="8273b-248">UTF-8 and UTF-32</span></span>

<span data-ttu-id="8273b-249">Las secciones anteriores se centraban en UTF-16 porque es lo que usa .NET para codificar instancias de `string`.</span><span class="sxs-lookup"><span data-stu-id="8273b-249">The preceding sections focused on UTF-16 because that's what .NET uses to encode `string` instances.</span></span> <span data-ttu-id="8273b-250">Existen otros sistemas de codificación para Unicode: [UTF-8](https://www.unicode.org/faq/utf_bom.html#UTF8) y [UTF-32](https://www.unicode.org/faq/utf_bom.html#UTF32).</span><span class="sxs-lookup"><span data-stu-id="8273b-250">There are other encoding systems for Unicode - [UTF-8](https://www.unicode.org/faq/utf_bom.html#UTF8) and [UTF-32](https://www.unicode.org/faq/utf_bom.html#UTF32).</span></span> <span data-ttu-id="8273b-251">Estas codificaciones usan unidades de código de 8 bits y unidades de código de 32 bits, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="8273b-251">These encodings use 8-bit code units and 32-bit code units, respectively.</span></span>

<span data-ttu-id="8273b-252">Al igual que UTF-16, UTF-8 requiere varias unidades de código para representar algunos valores escalares Unicode.</span><span class="sxs-lookup"><span data-stu-id="8273b-252">Like UTF-16, UTF-8 requires multiple code units to represent some Unicode scalar values.</span></span> <span data-ttu-id="8273b-253">UTF-32 puede representar cualquier valor escalar en una sola unidad de código de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="8273b-253">UTF-32 can represent any scalar value in a single 32-bit code unit.</span></span>

<span data-ttu-id="8273b-254">Estos son algunos ejemplos en los que se muestra cómo se representa el mismo punto de código Unicode en cada uno de estos tres sistemas de codificación Unicode:</span><span class="sxs-lookup"><span data-stu-id="8273b-254">Here are some examples showing how the same Unicode code point is represented in each of these three Unicode encoding systems:</span></span>

```
Scalar: U+0061 LATIN SMALL LETTER A ('a')
UTF-8 : [ 61 ]           (1x  8-bit code unit  = 8 bits total)
UTF-16: [ 0061 ]         (1x 16-bit code unit  = 16 bits total)
UTF-32: [ 00000061 ]     (1x 32-bit code unit  = 32 bits total)

Scalar: U+0429 CYRILLIC CAPITAL LETTER SHCHA ('Щ')
UTF-8 : [ D0 A9 ]        (2x  8-bit code units = 16 bits total)
UTF-16: [ 0429 ]         (1x 16-bit code unit  = 16 bits total)
UTF-32: [ 00000429 ]     (1x 32-bit code unit  = 32 bits total)

Scalar: U+A992 JAVANESE LETTER GA ('ꦒ')
UTF-8 : [ EA A6 92 ]     (3x  8-bit code units = 24 bits total)
UTF-16: [ A992 ]         (1x 16-bit code unit  = 16 bits total)
UTF-32: [ 0000A992 ]     (1x 32-bit code unit  = 32 bits total)

Scalar: U+104CC OSAGE CAPITAL LETTER TSHA ('𐓌')
UTF-8 : [ F0 90 93 8C ]  (4x  8-bit code units = 32 bits total)
UTF-16: [ D801 DCCC ]    (2x 16-bit code units = 32 bits total)
UTF-32: [ 000104CC ]     (1x 32-bit code unit  = 32 bits total)
```

<span data-ttu-id="8273b-255">Como se indicó anteriormente, una única unidad de código UTF-16 de un [par suplente](#surrogate-pairs) no tiene sentido.</span><span class="sxs-lookup"><span data-stu-id="8273b-255">As noted earlier, a single UTF-16 code unit from a [surrogate pair](#surrogate-pairs) is meaningless by itself.</span></span> <span data-ttu-id="8273b-256">Del mismo modo, una sola unidad de código UTF-8 no tiene sentido si se encuentra en una secuencia de dos, tres o cuatro usadas para calcular un valor escalar.</span><span class="sxs-lookup"><span data-stu-id="8273b-256">In the same way, a single UTF-8 code unit is meaningless by itself if it's in a sequence of two, three, or four used to calculate a scalar value.</span></span>

### <a name="endianness"></a><span data-ttu-id="8273b-257">Modos endian</span><span class="sxs-lookup"><span data-stu-id="8273b-257">Endianness</span></span>

<span data-ttu-id="8273b-258">En .NET, las unidades de código UTF-16 de una instancia de string se almacenan en memoria contigua como una secuencia de enteros de 16 bits (instancias de `char`).</span><span class="sxs-lookup"><span data-stu-id="8273b-258">In .NET, the UTF-16 code units of a string are stored in contiguous memory as a sequence of 16-bit integers (`char` instances).</span></span> <span data-ttu-id="8273b-259">Los bits de las unidades de código individuales se disponen de acuerdo con el [modo endian](https://en.wikipedia.org/wiki/Endianness) de la arquitectura actual.</span><span class="sxs-lookup"><span data-stu-id="8273b-259">The bits of individual code units are laid out according to the [endianness](https://en.wikipedia.org/wiki/Endianness) of the current architecture.</span></span>

<span data-ttu-id="8273b-260">En una arquitectura little-endian, la instancia de string que consta de los puntos de código UTF-16 `[ D801 DCCC ]` se dispondría en memoria como los bytes `[ 0x01, 0xD8, 0xCC, 0xDC ]`.</span><span class="sxs-lookup"><span data-stu-id="8273b-260">On a little-endian architecture, the string consisting of the UTF-16 code points `[ D801 DCCC ]` would be laid out in memory as the bytes `[ 0x01, 0xD8, 0xCC, 0xDC ]`.</span></span> <span data-ttu-id="8273b-261">En una arquitectura big-endian, la misma instancia de string se dispondría en memoria como los bytes `[ 0xD8, 0x01, 0xDC, 0xCC ]`.</span><span class="sxs-lookup"><span data-stu-id="8273b-261">On a big-endian architecture that same string would be laid out in memory as the bytes `[ 0xD8, 0x01, 0xDC, 0xCC ]`.</span></span>

<span data-ttu-id="8273b-262">Los sistemas informáticos que se comunican entre sí deben estar de acuerdo con la representación de los datos que atraviesan la conexión.</span><span class="sxs-lookup"><span data-stu-id="8273b-262">Computer systems that communicate with each other must agree on the representation of data crossing the wire.</span></span> <span data-ttu-id="8273b-263">La mayoría de los protocolos de red usan UTF-8 como estándar al transmitir texto, en parte para evitar problemas que podrían derivarse de una máquina big-endian que se comunica con una máquina little-endian.</span><span class="sxs-lookup"><span data-stu-id="8273b-263">Most network protocols use UTF-8 as a standard when transmitting text, partly to avoid issues that might result from a big-endian machine communicating with a little-endian machine.</span></span> <span data-ttu-id="8273b-264">La instancia de string que consta de los puntos de código UTF-8 `[ F0 90 93 8C ]` siempre se representará como los bytes `[ 0xF0, 0x90, 0x93, 0x8C ]` con independencia del modo endian.</span><span class="sxs-lookup"><span data-stu-id="8273b-264">The string consisting of the UTF-8 code points `[ F0 90 93 8C ]` will always be represented as the bytes `[ 0xF0, 0x90, 0x93, 0x8C ]` regardless of endianness.</span></span>

<span data-ttu-id="8273b-265">Para usar UTF-8 para transmitir texto, las aplicaciones .NET a menudo usan código como el del ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8273b-265">To use UTF-8 for transmitting text, .NET applications often use code like the following example:</span></span>

```csharp
string stringToWrite = GetString();
byte[] stringAsUtf8Bytes = Encoding.UTF8.GetBytes(stringToWrite);
await outputStream.WriteAsync(stringAsUtf8Bytes, 0, stringAsUtf8Bytes.Length);
```

<span data-ttu-id="8273b-266">En el ejemplo anterior, el método [Encoding.UTF8.GetBytes](xref:System.Text.UTF8Encoding.GetBytes%2A) descodifica de nuevo la instancia de `string` UTF-16 en una serie de valores escalares Unicode, después vuelve a codificar esos valores escalares en UTF-8 y coloca la secuencia resultante en una matriz de `byte`.</span><span class="sxs-lookup"><span data-stu-id="8273b-266">In the preceding example, the method [Encoding.UTF8.GetBytes](xref:System.Text.UTF8Encoding.GetBytes%2A) decodes the UTF-16 `string` back into a series of Unicode scalar values, then it re-encodes those scalar values into UTF-8 and places the resulting sequence into a `byte` array.</span></span> <span data-ttu-id="8273b-267">El método [Encoding.UTF8.GetString](xref:System.Text.UTF8Encoding.GetString%2A) realiza la transformación opuesta, al convertir una matriz de `byte` UTF-8 en una instancia de `string` UTF-16.</span><span class="sxs-lookup"><span data-stu-id="8273b-267">The method [Encoding.UTF8.GetString](xref:System.Text.UTF8Encoding.GetString%2A) performs the opposite transformation, converting a UTF-8 `byte` array to a UTF-16 `string`.</span></span>

> [!WARNING]
> <span data-ttu-id="8273b-268">Dado que UTF-8 es habitual en Internet, puede resultar tentador leer los bytes sin formato de la conexión y tratar los datos como si fueran UTF-8.</span><span class="sxs-lookup"><span data-stu-id="8273b-268">Since UTF-8 is commonplace on the internet, it may be tempting to read raw bytes from the wire and to treat the data as if it were UTF-8.</span></span> <span data-ttu-id="8273b-269">Sin embargo, debe validar que el formato es correcto.</span><span class="sxs-lookup"><span data-stu-id="8273b-269">However, you should validate that it is indeed well-formed.</span></span> <span data-ttu-id="8273b-270">Un cliente malintencionado podría enviar UTF-8 con un formato incorrecto a su servicio.</span><span class="sxs-lookup"><span data-stu-id="8273b-270">A malicious client might submit ill-formed UTF-8 to your service.</span></span> <span data-ttu-id="8273b-271">Si trabaja en esos datos como si tuvieran el formato correcto, podría provocar errores o vulnerabilidades de seguridad en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8273b-271">If you operate on that data as if it were well-formed, it could cause errors or security holes in your application.</span></span> <span data-ttu-id="8273b-272">Para validar los datos UTF-8, puede usar un método como `Encoding.UTF8.GetString`, que realizará la validación mientras convierte los datos entrantes en una instancia de `string`.</span><span class="sxs-lookup"><span data-stu-id="8273b-272">To validate UTF-8 data, you can use a method like `Encoding.UTF8.GetString`, which will perform validation while converting the incoming data to a `string`.</span></span>

### <a name="well-formed-encoding"></a><span data-ttu-id="8273b-273">Codificación con un formato correcto</span><span class="sxs-lookup"><span data-stu-id="8273b-273">Well-formed encoding</span></span>

<span data-ttu-id="8273b-274">Una codificación Unicode con un formato correcto es una instancia de string de unidades de código que se puede descodificar de forma inequívoca y sin errores en una secuencia de valores escalares Unicode.</span><span class="sxs-lookup"><span data-stu-id="8273b-274">A well-formed Unicode encoding is a string of code units that can be decoded unambiguously and without error into a sequence of Unicode scalar values.</span></span> <span data-ttu-id="8273b-275">Los datos con un formato correcto se pueden transcodificar libremente entre UTF-8, UTF-16 y UTF-32.</span><span class="sxs-lookup"><span data-stu-id="8273b-275">Well-formed data can be transcoded freely back and forth between UTF-8, UTF-16, and UTF-32.</span></span>

<span data-ttu-id="8273b-276">La cuestión de si una secuencia de codificación tiene el formato correcto o no está relacionada con el modo endian de la arquitectura de una máquina.</span><span class="sxs-lookup"><span data-stu-id="8273b-276">The question of whether an encoding sequence is well-formed or not is unrelated to the endianness of a machine's architecture.</span></span> <span data-ttu-id="8273b-277">Una secuencia UTF-8 mal formada tiene un formato incorrecto tanto en máquinas big-endian como little-endian.</span><span class="sxs-lookup"><span data-stu-id="8273b-277">An ill-formed UTF-8 sequence is ill-formed in the same way on both big-endian and little-endian machines.</span></span>

<span data-ttu-id="8273b-278">Estos son algunos ejemplos de codificaciones con un formato incorrecto:</span><span class="sxs-lookup"><span data-stu-id="8273b-278">Here are some examples of ill-formed encodings:</span></span>

* <span data-ttu-id="8273b-279">En UTF-8, la secuencia `[ 6C C2 61 ]` tiene un formato incorrecto porque `C2` no puede ir seguido de `61`.</span><span class="sxs-lookup"><span data-stu-id="8273b-279">In UTF-8, the sequence `[ 6C C2 61 ]` is ill-formed because `C2` cannot be followed by `61`.</span></span>

* <span data-ttu-id="8273b-280">En UTF-16, la secuencia `[ DC00 DD00 ]` (o, en C#, la instancia de string `"\udc00\udd00"`) tiene un formato incorrecto porque el suplente inferior `DC00` no puede ir seguido de otro suplente inferior `DD00`.</span><span class="sxs-lookup"><span data-stu-id="8273b-280">In UTF-16, the sequence `[ DC00 DD00 ]` (or, in C#, the string `"\udc00\udd00"`) is ill-formed because the low surrogate `DC00` cannot be followed by another low surrogate `DD00`.</span></span>

* <span data-ttu-id="8273b-281">En UTF-32, la secuencia `[ 0011ABCD ]` tiene un formato incorrecto porque `0011ABCD` está fuera del intervalo de valores escalares Unicode.</span><span class="sxs-lookup"><span data-stu-id="8273b-281">In UTF-32, the sequence `[ 0011ABCD ]` is ill-formed because `0011ABCD` is outside the range of Unicode scalar values.</span></span>

<span data-ttu-id="8273b-282">En .NET, las instancias de `string` casi siempre contienen datos UTF-16 con un formato correcto, pero no se garantiza.</span><span class="sxs-lookup"><span data-stu-id="8273b-282">In .NET, `string` instances almost always contain well-formed UTF-16 data, but that isn't guaranteed.</span></span> <span data-ttu-id="8273b-283">En los siguientes ejemplos se muestra un código válido de C# que crea datos UTF-16 con un formato incorrecto en instancias de `string`.</span><span class="sxs-lookup"><span data-stu-id="8273b-283">The following examples show valid C# code that creates ill-formed UTF-16 data in `string` instances.</span></span>

* <span data-ttu-id="8273b-284">Un literal con un formato incorrecto:</span><span class="sxs-lookup"><span data-stu-id="8273b-284">An ill-formed literal:</span></span>

  ```csharp
  const string s = "\ud800";
  ```

* <span data-ttu-id="8273b-285">Una subcadena que divide un par suplente:</span><span class="sxs-lookup"><span data-stu-id="8273b-285">A substring that splits up a surrogate pair:</span></span>

  ```csharp
  string x = "\ud83e\udd70"; // "🥰"
  string y = x.Substring(1, 1); // "\udd70" standalone low surrogate
  ```

<span data-ttu-id="8273b-286">Las API como [`Encoding.UTF8.GetString`](xref:System.Text.UTF8Encoding.GetString%2A) nunca devuelven instancias de `string` con un formato incorrecto.</span><span class="sxs-lookup"><span data-stu-id="8273b-286">APIs like [`Encoding.UTF8.GetString`](xref:System.Text.UTF8Encoding.GetString%2A) never return ill-formed `string` instances.</span></span> <span data-ttu-id="8273b-287">Los métodos `Encoding.GetString` y `Encoding.GetBytes` detectan secuencias con un formato incorrecto en la entrada y realizan la sustitución de caracteres al generar la salida.</span><span class="sxs-lookup"><span data-stu-id="8273b-287">`Encoding.GetString` and `Encoding.GetBytes` methods detect ill-formed sequences in the input and perform character substitution when generating the output.</span></span> <span data-ttu-id="8273b-288">Por ejemplo, si [`Encoding.ASCII.GetString(byte[])`](xref:System.Text.ASCIIEncoding.GetString%2A) observa un byte no ASCII en la entrada (fuera del intervalo de U+0000..U+007F), inserta un "?" en la instancia de `string` devuelta.</span><span class="sxs-lookup"><span data-stu-id="8273b-288">For example, if [`Encoding.ASCII.GetString(byte[])`](xref:System.Text.ASCIIEncoding.GetString%2A) sees a non-ASCII byte in the input (outside the range U+0000..U+007F), it inserts a '?' into the returned `string` instance.</span></span> <span data-ttu-id="8273b-289">[`Encoding.UTF8.GetString(byte[])`](xref:System.Text.UTF8Encoding.GetString%2A) reemplaza las secuencias UTF-8 con un formato incorrecto por `U+FFFD REPLACEMENT CHARACTER ('�')` en la instancia de `string` devuelta.</span><span class="sxs-lookup"><span data-stu-id="8273b-289">[`Encoding.UTF8.GetString(byte[])`](xref:System.Text.UTF8Encoding.GetString%2A) replaces ill-formed UTF-8 sequences with `U+FFFD REPLACEMENT CHARACTER ('�')` in the returned `string` instance.</span></span> <span data-ttu-id="8273b-290">Para más información, consulte [el estándar Unicode](https://www.unicode.org/versions/latest/), secciones 5.22 y 3.9.</span><span class="sxs-lookup"><span data-stu-id="8273b-290">For more information, see [the Unicode Standard](https://www.unicode.org/versions/latest/), Sections 5.22 and 3.9.</span></span>

<span data-ttu-id="8273b-291">Las clases `Encoding` integradas también se pueden configurar para producir una excepción en lugar de realizar la sustitución de caracteres cuando se observan secuencias con un formato incorrecto.</span><span class="sxs-lookup"><span data-stu-id="8273b-291">The built-in `Encoding` classes can also be configured to throw an exception rather than perform character substitution when ill-formed sequences are seen.</span></span> <span data-ttu-id="8273b-292">Este enfoque se suele usar en aplicaciones que dependen de la seguridad donde la sustitución de caracteres podría no ser aceptable.</span><span class="sxs-lookup"><span data-stu-id="8273b-292">This approach is often used in security-sensitive applications where character substitution might not be acceptable.</span></span>

```csharp
byte[] utf8Bytes = ReadFromNetwork();
UTF8Encoding encoding = new UTF8Encoding(encoderShouldEmitUTF8Identifier: false, throwOnInvalidBytes: true);
string asString = encoding.GetString(utf8Bytes); // will throw if 'utf8Bytes' is ill-formed
```

<span data-ttu-id="8273b-293">Para información sobre cómo usar las clases `Encoding` integradas, consulte [Uso de las clases de codificación de caracteres en .NET](character-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="8273b-293">For information about how to use the built-in `Encoding` classes, see [How to use character encoding classes in .NET](character-encoding.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8273b-294">Vea también</span><span class="sxs-lookup"><span data-stu-id="8273b-294">See also</span></span>

- <xref:System.String>
- <xref:System.Char>
- <xref:System.Text.Rune>
- [<span data-ttu-id="8273b-295">Globalización y localización</span><span class="sxs-lookup"><span data-stu-id="8273b-295">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)
