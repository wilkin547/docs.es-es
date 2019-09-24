---
title: Cadenas
description: Obtenga información sobre F# cómo el tipo ' cadena ' representa texto inmutable como una secuencia de caracteres Unicode.
ms.date: 07/05/2019
ms.openlocfilehash: 25f5d7ce5059ba5ddb4e938313c511734c2d7320
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216733"
---
# <a name="strings"></a><span data-ttu-id="150e4-103">Cadenas</span><span class="sxs-lookup"><span data-stu-id="150e4-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="150e4-104">Los vínculos de la referencia de API de este artículo le llevarán a MSDN.</span><span class="sxs-lookup"><span data-stu-id="150e4-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="150e4-105">La referencia de API de docs.microsoft.com no está completa.</span><span class="sxs-lookup"><span data-stu-id="150e4-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="150e4-106">El `string` tipo representa el texto inmutable como una secuencia de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="150e4-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="150e4-107">`string` es un alias de `System.String` en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="150e4-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="150e4-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="150e4-108">Remarks</span></span>

<span data-ttu-id="150e4-109">Los literales de cadena se delimitan mediante el carácter de Comillas (").</span><span class="sxs-lookup"><span data-stu-id="150e4-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="150e4-110">El carácter de barra diagonal \\ inversa () se usa para codificar determinados caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="150e4-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="150e4-111">La barra diagonal inversa y el siguiente carácter juntos se conocen como una *secuencia de escape*.</span><span class="sxs-lookup"><span data-stu-id="150e4-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="150e4-112">En la tabla siguiente F# se muestran las secuencias de escape que se admiten en literales de cadena.</span><span class="sxs-lookup"><span data-stu-id="150e4-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="150e4-113">Carácter</span><span class="sxs-lookup"><span data-stu-id="150e4-113">Character</span></span>|<span data-ttu-id="150e4-114">Secuencia de escape</span><span class="sxs-lookup"><span data-stu-id="150e4-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="150e4-115">Alerta</span><span class="sxs-lookup"><span data-stu-id="150e4-115">Alert</span></span>|`\a`|
|<span data-ttu-id="150e4-116">Retroceso</span><span class="sxs-lookup"><span data-stu-id="150e4-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="150e4-117">Avance de página</span><span class="sxs-lookup"><span data-stu-id="150e4-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="150e4-118">Nueva línea</span><span class="sxs-lookup"><span data-stu-id="150e4-118">Newline</span></span>|`\n`|
|<span data-ttu-id="150e4-119">Retorno de carro</span><span class="sxs-lookup"><span data-stu-id="150e4-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="150e4-120">Tab</span><span class="sxs-lookup"><span data-stu-id="150e4-120">Tab</span></span>|`\t`|
|<span data-ttu-id="150e4-121">Tabulación vertical</span><span class="sxs-lookup"><span data-stu-id="150e4-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="150e4-122">Barra diagonal inversa</span><span class="sxs-lookup"><span data-stu-id="150e4-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="150e4-123">Comilla</span><span class="sxs-lookup"><span data-stu-id="150e4-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="150e4-124">Ni</span><span class="sxs-lookup"><span data-stu-id="150e4-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="150e4-125">Carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="150e4-125">Unicode character</span></span>|<span data-ttu-id="150e4-126">`\DDD`(donde `D` indica un dígito decimal; intervalo de 000-255; por ejemplo, `\231` = "ç")</span><span class="sxs-lookup"><span data-stu-id="150e4-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="150e4-127">Carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="150e4-127">Unicode character</span></span>|<span data-ttu-id="150e4-128">`\xHH`(donde `H` indica un dígito hexadecimal; intervalo de 00-FF; por ejemplo, `\xE7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="150e4-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="150e4-129">Carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="150e4-129">Unicode character</span></span>|<span data-ttu-id="150e4-130">`\uHHHH`(UTF-16) (donde `H` indica un dígito hexadecimal; intervalo de 0000-ffff;  por ejemplo, `\u00E7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="150e4-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="150e4-131">Carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="150e4-131">Unicode character</span></span>|<span data-ttu-id="150e4-132">`\U00HHHHHH`(UTF-32) (donde `H` indica un dígito hexadecimal; intervalo de 000000-10FFFF;  por ejemplo, `\U0001F47D` = "👽")</span><span class="sxs-lookup"><span data-stu-id="150e4-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="150e4-133">La `\DDD` secuencia de escape es notación decimal, no notación octal, como en la mayoría de los demás lenguajes.</span><span class="sxs-lookup"><span data-stu-id="150e4-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="150e4-134">Por lo tanto `8` , `9` los dígitos y son válidos, `\032` y una secuencia de representa un espacio (U + 0020), mientras que el `\040`mismo punto de código en la notación octal sería.</span><span class="sxs-lookup"><span data-stu-id="150e4-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="150e4-135">Al estar restringido a un intervalo de 0-255 (0xFF), las `\DDD` secuencias `\x` de escape y son, de hecho, el juego de caracteres [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) , ya que coincide con los primeros 256 puntos de código Unicode.</span><span class="sxs-lookup"><span data-stu-id="150e4-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

<span data-ttu-id="150e4-136">Si va precedido por el símbolo @, el literal es una cadena textual.</span><span class="sxs-lookup"><span data-stu-id="150e4-136">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="150e4-137">Esto significa que se omiten las secuencias de escape, salvo que dos caracteres de Comillas se interpretan como un carácter de comilla.</span><span class="sxs-lookup"><span data-stu-id="150e4-137">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="150e4-138">Además, una cadena se puede incluir entre comillas triples.</span><span class="sxs-lookup"><span data-stu-id="150e4-138">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="150e4-139">En este caso, se omiten todas las secuencias de escape, incluidos los caracteres de comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="150e4-139">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="150e4-140">Para especificar una cadena que contenga una cadena entrecomillada insertada, puede usar una cadena textual o una cadena entre comillas triples.</span><span class="sxs-lookup"><span data-stu-id="150e4-140">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="150e4-141">Si utiliza una cadena textual, debe especificar dos caracteres de comillas para indicar un carácter de comilla simple.</span><span class="sxs-lookup"><span data-stu-id="150e4-141">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="150e4-142">Si utiliza una cadena entre comillas triples, puede utilizar los caracteres de comilla simple sin analizarlos como el final de la cadena.</span><span class="sxs-lookup"><span data-stu-id="150e4-142">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="150e4-143">Esta técnica puede ser útil cuando se trabaja con XML u otras estructuras que incluyen comillas incrustadas.</span><span class="sxs-lookup"><span data-stu-id="150e4-143">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="150e4-144">En el código, se aceptan cadenas con saltos de línea y los saltos de línea se interpretan literalmente como líneas nuevas, a menos que un carácter de barra diagonal inversa sea el último carácter antes del salto de línea.</span><span class="sxs-lookup"><span data-stu-id="150e4-144">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="150e4-145">El espacio en blanco inicial en la línea siguiente se omite cuando se usa el carácter de barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="150e4-145">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="150e4-146">El código siguiente genera una cadena `str1` que tiene el `"abc\ndef"` valor y una `str2` cadena que tiene `"abcdef"`el valor.</span><span class="sxs-lookup"><span data-stu-id="150e4-146">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="150e4-147">Puede tener acceso a caracteres individuales de una cadena mediante la sintaxis de tipo matriz, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="150e4-147">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="150e4-148">El resultado es `b`</span><span class="sxs-lookup"><span data-stu-id="150e4-148">The output is `b`.</span></span>

<span data-ttu-id="150e4-149">O bien, puede extraer subcadenas mediante la sintaxis de segmento de matriz, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="150e4-149">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="150e4-150">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="150e4-150">The output is as follows.</span></span>

```console
abc
def
```

<span data-ttu-id="150e4-151">Puede representar cadenas ASCII por matrices de bytes sin signo, tipo `byte[]`.</span><span class="sxs-lookup"><span data-stu-id="150e4-151">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="150e4-152">Agregue el sufijo `B` a un literal de cadena para indicar que es una cadena ASCII.</span><span class="sxs-lookup"><span data-stu-id="150e4-152">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="150e4-153">Los literales de cadena ASCII usados con matrices de bytes admiten las mismas secuencias de escape que las cadenas Unicode, excepto las secuencias de escape Unicode.</span><span class="sxs-lookup"><span data-stu-id="150e4-153">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="150e4-154">Operadores de cadena</span><span class="sxs-lookup"><span data-stu-id="150e4-154">String Operators</span></span>

<span data-ttu-id="150e4-155">Hay dos maneras de concatenar cadenas: mediante el `+` operador o mediante el `^` operador.</span><span class="sxs-lookup"><span data-stu-id="150e4-155">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="150e4-156">El `+` operador mantiene la compatibilidad con las características de control de cadenas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="150e4-156">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="150e4-157">En el ejemplo siguiente se muestra la concatenación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="150e4-157">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="150e4-158">String (clase)</span><span class="sxs-lookup"><span data-stu-id="150e4-158">String Class</span></span>

<span data-ttu-id="150e4-159">Dado que el tipo de F# cadena en es realmente `System.String` un tipo .NET Framework, `System.String` todos los miembros están disponibles.</span><span class="sxs-lookup"><span data-stu-id="150e4-159">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="150e4-160">Esto incluye el `+` operador, que se usa para concatenar cadenas, la `Length` propiedad y la `Chars` propiedad, que devuelve la cadena como una matriz de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="150e4-160">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="150e4-161">Para obtener más información sobre las cadenas `System.String`, vea.</span><span class="sxs-lookup"><span data-stu-id="150e4-161">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="150e4-162">Mediante el uso `Chars` de la `System.String`propiedad de, se puede tener acceso a los caracteres individuales de una cadena mediante la especificación de un índice, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="150e4-162">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="150e4-163">Módulo de cadena</span><span class="sxs-lookup"><span data-stu-id="150e4-163">String Module</span></span>

<span data-ttu-id="150e4-164">En el módulo del `String` `FSharp.Core` espacio de nombres se incluye funcionalidad adicional para el control de cadenas.</span><span class="sxs-lookup"><span data-stu-id="150e4-164">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="150e4-165">Para obtener más información, vea [módulo Core. String](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="150e4-165">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="150e4-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="150e4-166">See also</span></span>

- [<span data-ttu-id="150e4-167">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="150e4-167">F# Language Reference</span></span>](index.md)
