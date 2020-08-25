---
title: Cadenas
description: "Obtenga información sobre cómo el tipo de F # ' cadena ' representa texto inmutable como una secuencia de caracteres Unicode."
ms.date: 08/15/2020
ms.openlocfilehash: f6ec36feeb197bf785c702e7b626cf5cf80696ab
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812216"
---
# <a name="strings"></a><span data-ttu-id="2857f-103">Cadenas</span><span class="sxs-lookup"><span data-stu-id="2857f-103">Strings</span></span>

<span data-ttu-id="2857f-104">El `string` tipo representa el texto inmutable como una secuencia de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="2857f-104">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="2857f-105">`string` es un alias de `System.String` en .NET.</span><span class="sxs-lookup"><span data-stu-id="2857f-105">`string` is an alias for `System.String` in .NET.</span></span>

## <a name="remarks"></a><span data-ttu-id="2857f-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2857f-106">Remarks</span></span>

<span data-ttu-id="2857f-107">Los literales de cadena se delimitan mediante el carácter de Comillas (").</span><span class="sxs-lookup"><span data-stu-id="2857f-107">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="2857f-108">El carácter de barra diagonal inversa ( \\ ) se usa para codificar determinados caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="2857f-108">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="2857f-109">La barra diagonal inversa y el siguiente carácter juntos se conocen como una *secuencia de escape*.</span><span class="sxs-lookup"><span data-stu-id="2857f-109">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="2857f-110">En la tabla siguiente se muestran las secuencias de escape que se admiten en literales de cadena de F #.</span><span class="sxs-lookup"><span data-stu-id="2857f-110">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="2857f-111">Carácter</span><span class="sxs-lookup"><span data-stu-id="2857f-111">Character</span></span>|<span data-ttu-id="2857f-112">Secuencia de escape</span><span class="sxs-lookup"><span data-stu-id="2857f-112">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="2857f-113">Alerta</span><span class="sxs-lookup"><span data-stu-id="2857f-113">Alert</span></span>|`\a`|
|<span data-ttu-id="2857f-114">Retroceso</span><span class="sxs-lookup"><span data-stu-id="2857f-114">Backspace</span></span>|`\b`|
|<span data-ttu-id="2857f-115">Avance de página</span><span class="sxs-lookup"><span data-stu-id="2857f-115">Form feed</span></span>|`\f`|
|<span data-ttu-id="2857f-116">Nueva línea</span><span class="sxs-lookup"><span data-stu-id="2857f-116">Newline</span></span>|`\n`|
|<span data-ttu-id="2857f-117">Retorno de carro</span><span class="sxs-lookup"><span data-stu-id="2857f-117">Carriage return</span></span>|`\r`|
|<span data-ttu-id="2857f-118">Pestaña</span><span class="sxs-lookup"><span data-stu-id="2857f-118">Tab</span></span>|`\t`|
|<span data-ttu-id="2857f-119">Tabulación vertical</span><span class="sxs-lookup"><span data-stu-id="2857f-119">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="2857f-120">Barra diagonal inversa</span><span class="sxs-lookup"><span data-stu-id="2857f-120">Backslash</span></span>|`\\`|
|<span data-ttu-id="2857f-121">Comillas</span><span class="sxs-lookup"><span data-stu-id="2857f-121">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="2857f-122">Apóstrofo</span><span class="sxs-lookup"><span data-stu-id="2857f-122">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="2857f-123">carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="2857f-123">Unicode character</span></span>|<span data-ttu-id="2857f-124">`\DDD` (donde `D` indica un dígito decimal; intervalo de 000-255; por ejemplo, `\231` = "ç")</span><span class="sxs-lookup"><span data-stu-id="2857f-124">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="2857f-125">carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="2857f-125">Unicode character</span></span>|<span data-ttu-id="2857f-126">`\xHH` (donde `H` indica un dígito hexadecimal; intervalo de 00-FF; por ejemplo, `\xE7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="2857f-126">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="2857f-127">carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="2857f-127">Unicode character</span></span>|<span data-ttu-id="2857f-128">`\uHHHH` (UTF-16) (donde `H` indica un dígito hexadecimal; intervalo de 0000-ffff;  por ejemplo, `\u00E7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="2857f-128">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="2857f-129">carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="2857f-129">Unicode character</span></span>|<span data-ttu-id="2857f-130">`\U00HHHHHH` (UTF-32) (donde `H` indica un dígito hexadecimal; intervalo de 000000-10FFFF;  por ejemplo, `\U0001F47D` = " 👽 ")</span><span class="sxs-lookup"><span data-stu-id="2857f-130">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="2857f-131">La `\DDD` secuencia de escape es notación decimal, no notación octal, como en la mayoría de los demás lenguajes.</span><span class="sxs-lookup"><span data-stu-id="2857f-131">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="2857f-132">Por lo tanto, los dígitos `8` y `9` son válidos, y una secuencia de `\032` representa un espacio (U + 0020), mientras que el mismo punto de código en la notación octal sería `\040` .</span><span class="sxs-lookup"><span data-stu-id="2857f-132">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="2857f-133">Al estar restringido a un intervalo de 0-255 (0xFF), las `\DDD` `\x` secuencias de escape y son, de hecho, el juego de caracteres [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) , ya que coincide con los primeros 256 puntos de código Unicode.</span><span class="sxs-lookup"><span data-stu-id="2857f-133">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

## <a name="verbatim-strings"></a><span data-ttu-id="2857f-134">Cadenas textuales</span><span class="sxs-lookup"><span data-stu-id="2857f-134">Verbatim Strings</span></span>

<span data-ttu-id="2857f-135">Si va precedido por el símbolo @, el literal es una cadena textual.</span><span class="sxs-lookup"><span data-stu-id="2857f-135">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="2857f-136">Esto significa que se omiten las secuencias de escape, salvo que dos caracteres de Comillas se interpretan como un carácter de comilla.</span><span class="sxs-lookup"><span data-stu-id="2857f-136">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

## <a name="triple-quoted-strings"></a><span data-ttu-id="2857f-137">Triples cadenas entre comillas</span><span class="sxs-lookup"><span data-stu-id="2857f-137">Triple Quoted Strings</span></span>

<span data-ttu-id="2857f-138">Además, una cadena se puede incluir entre comillas triples.</span><span class="sxs-lookup"><span data-stu-id="2857f-138">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="2857f-139">En este caso, se omiten todas las secuencias de escape, incluidos los caracteres de comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="2857f-139">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="2857f-140">Para especificar una cadena que contenga una cadena entrecomillada insertada, puede usar una cadena textual o una cadena entre comillas triples.</span><span class="sxs-lookup"><span data-stu-id="2857f-140">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="2857f-141">Si utiliza una cadena textual, debe especificar dos caracteres de comillas para indicar un carácter de comilla simple.</span><span class="sxs-lookup"><span data-stu-id="2857f-141">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="2857f-142">Si utiliza una cadena entre comillas triples, puede utilizar los caracteres de comilla simple sin analizarlos como el final de la cadena.</span><span class="sxs-lookup"><span data-stu-id="2857f-142">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="2857f-143">Esta técnica puede ser útil cuando se trabaja con XML u otras estructuras que incluyen comillas incrustadas.</span><span class="sxs-lookup"><span data-stu-id="2857f-143">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="2857f-144">En el código, se aceptan cadenas con saltos de línea y los saltos de línea se interpretan literalmente como líneas nuevas, a menos que un carácter de barra diagonal inversa sea el último carácter antes del salto de línea.</span><span class="sxs-lookup"><span data-stu-id="2857f-144">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="2857f-145">El espacio en blanco inicial en la línea siguiente se omite cuando se usa el carácter de barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="2857f-145">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="2857f-146">El código siguiente genera una cadena `str1` que tiene el valor `"abc\ndef"` y una cadena `str2` que tiene el valor `"abcdef"` .</span><span class="sxs-lookup"><span data-stu-id="2857f-146">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a><span data-ttu-id="2857f-147">Indización y segmentación de cadenas</span><span class="sxs-lookup"><span data-stu-id="2857f-147">String Indexing and Slicing</span></span>

<span data-ttu-id="2857f-148">Puede tener acceso a caracteres individuales de una cadena mediante la sintaxis de tipo matriz, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="2857f-148">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="2857f-149">La salida es `b`.</span><span class="sxs-lookup"><span data-stu-id="2857f-149">The output is `b`.</span></span>

<span data-ttu-id="2857f-150">O bien, puede extraer subcadenas mediante la sintaxis de segmento de matriz, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="2857f-150">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="2857f-151">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="2857f-151">The output is as follows.</span></span>

```console
abc
def
```

<span data-ttu-id="2857f-152">Puede representar cadenas ASCII por matrices de bytes sin signo, tipo `byte[]` .</span><span class="sxs-lookup"><span data-stu-id="2857f-152">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="2857f-153">Agregue el sufijo `B` a un literal de cadena para indicar que es una cadena ASCII.</span><span class="sxs-lookup"><span data-stu-id="2857f-153">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="2857f-154">Los literales de cadena ASCII usados con matrices de bytes admiten las mismas secuencias de escape que las cadenas Unicode, excepto las secuencias de escape Unicode.</span><span class="sxs-lookup"><span data-stu-id="2857f-154">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="2857f-155">Operadores de cadena</span><span class="sxs-lookup"><span data-stu-id="2857f-155">String Operators</span></span>

<span data-ttu-id="2857f-156">El `+` operador se puede utilizar para concatenar cadenas, manteniendo la compatibilidad con las características de control de cadenas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2857f-156">The `+` operator can be used to concatenate strings, maintaining compatibility with the .NET Framework string handling features.</span></span> <span data-ttu-id="2857f-157">En el ejemplo siguiente se muestra la concatenación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="2857f-157">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="2857f-158">String (clase)</span><span class="sxs-lookup"><span data-stu-id="2857f-158">String Class</span></span>

<span data-ttu-id="2857f-159">Dado que el tipo de cadena en F # es realmente un `System.String` tipo .NET Framework, todos los `System.String` miembros están disponibles.</span><span class="sxs-lookup"><span data-stu-id="2857f-159">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="2857f-160">Esto incluye el `+` operador, que se usa para concatenar cadenas, la `Length` propiedad y la `Chars` propiedad, que devuelve la cadena como una matriz de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="2857f-160">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="2857f-161">Para obtener más información sobre las cadenas, vea `System.String` .</span><span class="sxs-lookup"><span data-stu-id="2857f-161">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="2857f-162">Mediante el uso `Chars` de la propiedad de `System.String` , se puede tener acceso a los caracteres individuales de una cadena mediante la especificación de un índice, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="2857f-162">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="2857f-163">Módulo de cadena</span><span class="sxs-lookup"><span data-stu-id="2857f-163">String Module</span></span>

<span data-ttu-id="2857f-164">En el `String` módulo del espacio de nombres se incluye funcionalidad adicional para el control de cadenas `FSharp.Core` .</span><span class="sxs-lookup"><span data-stu-id="2857f-164">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="2857f-165">Para obtener más información, vea [String (módulo](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-stringmodule.html)).</span><span class="sxs-lookup"><span data-stu-id="2857f-165">For more information, see [String Module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-stringmodule.html).</span></span>

## <a name="see-also"></a><span data-ttu-id="2857f-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="2857f-166">See also</span></span>

- [<span data-ttu-id="2857f-167">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="2857f-167">F# Language Reference</span></span>](index.md)
