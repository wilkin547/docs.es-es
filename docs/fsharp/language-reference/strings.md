---
title: Cadenas
description: Obtenga información sobre F# cómo el tipo ' cadena ' representa texto inmutable como una secuencia de caracteres Unicode.
ms.date: 07/05/2019
ms.openlocfilehash: 002de464d09a49b6161608db6e46c619369f5ceb
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452823"
---
# <a name="strings"></a><span data-ttu-id="a82ff-103">Cadenas</span><span class="sxs-lookup"><span data-stu-id="a82ff-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="a82ff-104">Los vínculos de la referencia de API de este artículo le llevarán a MSDN.</span><span class="sxs-lookup"><span data-stu-id="a82ff-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="a82ff-105">La referencia de API de docs.microsoft.com no está completa.</span><span class="sxs-lookup"><span data-stu-id="a82ff-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="a82ff-106">El tipo de `string` representa el texto inmutable como una secuencia de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="a82ff-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="a82ff-107">`string` es un alias de `System.String` en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a82ff-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="a82ff-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a82ff-108">Remarks</span></span>

<span data-ttu-id="a82ff-109">Los literales de cadena se delimitan mediante el carácter de Comillas (").</span><span class="sxs-lookup"><span data-stu-id="a82ff-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="a82ff-110">El carácter de barra diagonal inversa (\\) se usa para codificar determinados caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="a82ff-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="a82ff-111">La barra diagonal inversa y el siguiente carácter juntos se conocen como una *secuencia de escape*.</span><span class="sxs-lookup"><span data-stu-id="a82ff-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="a82ff-112">En la tabla siguiente F# se muestran las secuencias de escape que se admiten en literales de cadena.</span><span class="sxs-lookup"><span data-stu-id="a82ff-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="a82ff-113">Carácter</span><span class="sxs-lookup"><span data-stu-id="a82ff-113">Character</span></span>|<span data-ttu-id="a82ff-114">Secuencia de escape</span><span class="sxs-lookup"><span data-stu-id="a82ff-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="a82ff-115">Alerta</span><span class="sxs-lookup"><span data-stu-id="a82ff-115">Alert</span></span>|`\a`|
|<span data-ttu-id="a82ff-116">Retroceso</span><span class="sxs-lookup"><span data-stu-id="a82ff-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="a82ff-117">Avance de página</span><span class="sxs-lookup"><span data-stu-id="a82ff-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="a82ff-118">Nueva línea</span><span class="sxs-lookup"><span data-stu-id="a82ff-118">Newline</span></span>|`\n`|
|<span data-ttu-id="a82ff-119">Retorno de carro</span><span class="sxs-lookup"><span data-stu-id="a82ff-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="a82ff-120">Pestaña</span><span class="sxs-lookup"><span data-stu-id="a82ff-120">Tab</span></span>|`\t`|
|<span data-ttu-id="a82ff-121">Tabulación vertical</span><span class="sxs-lookup"><span data-stu-id="a82ff-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="a82ff-122">Barra diagonal inversa</span><span class="sxs-lookup"><span data-stu-id="a82ff-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="a82ff-123">Comillas</span><span class="sxs-lookup"><span data-stu-id="a82ff-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="a82ff-124">Ni</span><span class="sxs-lookup"><span data-stu-id="a82ff-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="a82ff-125">carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="a82ff-125">Unicode character</span></span>|<span data-ttu-id="a82ff-126">`\DDD` (donde `D` indica un dígito decimal; intervalo de 000-255; por ejemplo, `\231` = "ç")</span><span class="sxs-lookup"><span data-stu-id="a82ff-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="a82ff-127">carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="a82ff-127">Unicode character</span></span>|<span data-ttu-id="a82ff-128">`\xHH` (donde `H` indica un dígito hexadecimal; intervalo de 00-FF; por ejemplo, `\xE7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="a82ff-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="a82ff-129">carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="a82ff-129">Unicode character</span></span>|<span data-ttu-id="a82ff-130">`\uHHHH` (UTF-16) (donde `H` indica un dígito hexadecimal; rango de 0000-FFFF;  por ejemplo, `\u00E7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="a82ff-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="a82ff-131">carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="a82ff-131">Unicode character</span></span>|<span data-ttu-id="a82ff-132">`\U00HHHHHH` (UTF-32) (donde `H` indica un dígito hexadecimal; intervalo de 000000-10FFFF;  por ejemplo, `\U0001F47D` = "👽")</span><span class="sxs-lookup"><span data-stu-id="a82ff-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="a82ff-133">La secuencia de escape `\DDD` es notación decimal, no notación octal como en la mayoría de los demás lenguajes.</span><span class="sxs-lookup"><span data-stu-id="a82ff-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="a82ff-134">Por lo tanto, los dígitos `8` y `9` son válidos, y una secuencia de `\032` representa un espacio (U + 0020), mientras que el mismo punto de código en la notación octal sería `\040`.</span><span class="sxs-lookup"><span data-stu-id="a82ff-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="a82ff-135">Al estar restringido a un intervalo de 0-255 (0xFF), las secuencias de escape `\DDD` y `\x` son, de hecho, el juego de caracteres [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) , ya que coincide con los primeros 256 puntos de código Unicode.</span><span class="sxs-lookup"><span data-stu-id="a82ff-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

## <a name="verbatim-strings"></a><span data-ttu-id="a82ff-136">Cadenas textuales</span><span class="sxs-lookup"><span data-stu-id="a82ff-136">Verbatim Strings</span></span>

<span data-ttu-id="a82ff-137">Si va precedido por el símbolo @, el literal es una cadena textual.</span><span class="sxs-lookup"><span data-stu-id="a82ff-137">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="a82ff-138">Esto significa que se omiten las secuencias de escape, salvo que dos caracteres de Comillas se interpretan como un carácter de comilla.</span><span class="sxs-lookup"><span data-stu-id="a82ff-138">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

## <a name="triple-quoted-strings"></a><span data-ttu-id="a82ff-139">Triples cadenas entre comillas</span><span class="sxs-lookup"><span data-stu-id="a82ff-139">Triple Quoted Strings</span></span>

<span data-ttu-id="a82ff-140">Además, una cadena se puede incluir entre comillas triples.</span><span class="sxs-lookup"><span data-stu-id="a82ff-140">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="a82ff-141">En este caso, se omiten todas las secuencias de escape, incluidos los caracteres de comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="a82ff-141">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="a82ff-142">Para especificar una cadena que contenga una cadena entrecomillada insertada, puede usar una cadena textual o una cadena entre comillas triples.</span><span class="sxs-lookup"><span data-stu-id="a82ff-142">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="a82ff-143">Si utiliza una cadena textual, debe especificar dos caracteres de comillas para indicar un carácter de comilla simple.</span><span class="sxs-lookup"><span data-stu-id="a82ff-143">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="a82ff-144">Si utiliza una cadena entre comillas triples, puede utilizar los caracteres de comilla simple sin analizarlos como el final de la cadena.</span><span class="sxs-lookup"><span data-stu-id="a82ff-144">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="a82ff-145">Esta técnica puede ser útil cuando se trabaja con XML u otras estructuras que incluyen comillas incrustadas.</span><span class="sxs-lookup"><span data-stu-id="a82ff-145">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="a82ff-146">En el código, se aceptan cadenas con saltos de línea y los saltos de línea se interpretan literalmente como líneas nuevas, a menos que un carácter de barra diagonal inversa sea el último carácter antes del salto de línea.</span><span class="sxs-lookup"><span data-stu-id="a82ff-146">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="a82ff-147">El espacio en blanco inicial en la línea siguiente se omite cuando se usa el carácter de barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="a82ff-147">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="a82ff-148">El código siguiente genera un `str1` de cadena que tiene `"abc\ndef"` de valor y un `str2` de cadena que tiene `"abcdef"`de valor.</span><span class="sxs-lookup"><span data-stu-id="a82ff-148">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a><span data-ttu-id="a82ff-149">Indización y segmentación de cadenas</span><span class="sxs-lookup"><span data-stu-id="a82ff-149">String Indexing and Slicing</span></span>

<span data-ttu-id="a82ff-150">Puede tener acceso a caracteres individuales de una cadena mediante la sintaxis de tipo matriz, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="a82ff-150">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="a82ff-151">El resultado es `b`</span><span class="sxs-lookup"><span data-stu-id="a82ff-151">The output is `b`.</span></span>

<span data-ttu-id="a82ff-152">O bien, puede extraer subcadenas mediante la sintaxis de segmento de matriz, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a82ff-152">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="a82ff-153">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="a82ff-153">The output is as follows.</span></span>

```console
abc
def
```

<span data-ttu-id="a82ff-154">Puede representar cadenas ASCII por matrices de bytes sin signo, escriba `byte[]`.</span><span class="sxs-lookup"><span data-stu-id="a82ff-154">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="a82ff-155">Agregue el sufijo `B` a un literal de cadena para indicar que es una cadena ASCII.</span><span class="sxs-lookup"><span data-stu-id="a82ff-155">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="a82ff-156">Los literales de cadena ASCII usados con matrices de bytes admiten las mismas secuencias de escape que las cadenas Unicode, excepto las secuencias de escape Unicode.</span><span class="sxs-lookup"><span data-stu-id="a82ff-156">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="a82ff-157">Operadores de cadena</span><span class="sxs-lookup"><span data-stu-id="a82ff-157">String Operators</span></span>

<span data-ttu-id="a82ff-158">Hay dos maneras de concatenar cadenas: mediante el operador `+` o mediante el operador `^`.</span><span class="sxs-lookup"><span data-stu-id="a82ff-158">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="a82ff-159">El operador `+` mantiene la compatibilidad con las características de control de cadenas .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a82ff-159">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="a82ff-160">En el ejemplo siguiente se muestra la concatenación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="a82ff-160">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="a82ff-161">String (clase)</span><span class="sxs-lookup"><span data-stu-id="a82ff-161">String Class</span></span>

<span data-ttu-id="a82ff-162">Dado que el tipo de F# cadena en es realmente un .NET Framework tipo de `System.String`, todos los miembros de `System.String` están disponibles.</span><span class="sxs-lookup"><span data-stu-id="a82ff-162">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="a82ff-163">Esto incluye el operador `+`, que se usa para concatenar cadenas, la propiedad `Length` y la propiedad `Chars`, que devuelve la cadena como una matriz de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="a82ff-163">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="a82ff-164">Para obtener más información sobre las cadenas, vea `System.String`.</span><span class="sxs-lookup"><span data-stu-id="a82ff-164">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="a82ff-165">Mediante el uso de la propiedad `Chars` de `System.String`, puede tener acceso a los caracteres individuales de una cadena especificando un índice, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a82ff-165">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="a82ff-166">Módulo de cadena</span><span class="sxs-lookup"><span data-stu-id="a82ff-166">String Module</span></span>

<span data-ttu-id="a82ff-167">En el módulo `String` del espacio de nombres `FSharp.Core` se incluye funcionalidad adicional para el control de cadenas.</span><span class="sxs-lookup"><span data-stu-id="a82ff-167">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="a82ff-168">Para obtener más información, vea [módulo Core. String](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="a82ff-168">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="a82ff-169">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a82ff-169">See also</span></span>

- [<span data-ttu-id="a82ff-170">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="a82ff-170">F# Language Reference</span></span>](index.md)
