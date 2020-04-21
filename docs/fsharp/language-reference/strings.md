---
title: Cadenas
description: Obtenga información sobre cómo el tipo de "cadena" de F, representa el texto inmutable como una secuencia de caracteres Unicode.
ms.date: 07/05/2019
ms.openlocfilehash: 242a2cefa1cce8995090dddd1d1fd7181e0f5e0c
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739574"
---
# <a name="strings"></a><span data-ttu-id="83dfc-103">Cadenas</span><span class="sxs-lookup"><span data-stu-id="83dfc-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="83dfc-104">Los vínculos de la referencia de API de este artículo le llevarán a MSDN.</span><span class="sxs-lookup"><span data-stu-id="83dfc-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="83dfc-105">La referencia de API de docs.microsoft.com no está completa.</span><span class="sxs-lookup"><span data-stu-id="83dfc-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="83dfc-106">El `string` tipo representa texto inmutable como una secuencia de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="83dfc-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="83dfc-107">`string` es un alias de `System.String` en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="83dfc-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="83dfc-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="83dfc-108">Remarks</span></span>

<span data-ttu-id="83dfc-109">Los literales de cadena están delimitados por el carácter de comillas (").</span><span class="sxs-lookup"><span data-stu-id="83dfc-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="83dfc-110">El carácter \\ de barra diagonal inversa ( ) se utiliza para codificar ciertos caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="83dfc-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="83dfc-111">La barra diagonal inversa y el siguiente carácter juntos se conocen como una secuencia de *escape.*</span><span class="sxs-lookup"><span data-stu-id="83dfc-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="83dfc-112">En la tabla siguiente se muestran las secuencias de escape admitidas en los literales de cadena de F.</span><span class="sxs-lookup"><span data-stu-id="83dfc-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="83dfc-113">Carácter</span><span class="sxs-lookup"><span data-stu-id="83dfc-113">Character</span></span>|<span data-ttu-id="83dfc-114">Secuencia de escape</span><span class="sxs-lookup"><span data-stu-id="83dfc-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="83dfc-115">Alerta</span><span class="sxs-lookup"><span data-stu-id="83dfc-115">Alert</span></span>|`\a`|
|<span data-ttu-id="83dfc-116">Retroceso</span><span class="sxs-lookup"><span data-stu-id="83dfc-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="83dfc-117">Avance de página</span><span class="sxs-lookup"><span data-stu-id="83dfc-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="83dfc-118">Nueva línea</span><span class="sxs-lookup"><span data-stu-id="83dfc-118">Newline</span></span>|`\n`|
|<span data-ttu-id="83dfc-119">Retorno de carro</span><span class="sxs-lookup"><span data-stu-id="83dfc-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="83dfc-120">Pestaña</span><span class="sxs-lookup"><span data-stu-id="83dfc-120">Tab</span></span>|`\t`|
|<span data-ttu-id="83dfc-121">Tabulación vertical</span><span class="sxs-lookup"><span data-stu-id="83dfc-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="83dfc-122">Barra diagonal inversa</span><span class="sxs-lookup"><span data-stu-id="83dfc-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="83dfc-123">Comillas</span><span class="sxs-lookup"><span data-stu-id="83dfc-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="83dfc-124">Apóstrofo</span><span class="sxs-lookup"><span data-stu-id="83dfc-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="83dfc-125">carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="83dfc-125">Unicode character</span></span>|<span data-ttu-id="83dfc-126">`\DDD`(donde `D` indica un dígito decimal; rango de 000 - `\231` 255; por ejemplo, á "o")</span><span class="sxs-lookup"><span data-stu-id="83dfc-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="83dfc-127">carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="83dfc-127">Unicode character</span></span>|<span data-ttu-id="83dfc-128">`\xHH`(donde `H` se indica un dígito hexadecimal; rango de `\xE7` 00 - FF; por ejemplo, á "o")</span><span class="sxs-lookup"><span data-stu-id="83dfc-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="83dfc-129">carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="83dfc-129">Unicode character</span></span>|<span data-ttu-id="83dfc-130">`\uHHHH`(UTF-16) (donde `H` indica un dígito hexadecimal; rango de 0000 - FFFF;  por ejemplo, `\u00E7` "a")</span><span class="sxs-lookup"><span data-stu-id="83dfc-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="83dfc-131">carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="83dfc-131">Unicode character</span></span>|<span data-ttu-id="83dfc-132">`\U00HHHHHH`(UTF-32) (donde `H` indica un dígito hexadecimal; rango de 000000 - 10FFFF;  por ejemplo, `\U0001F47D` 👽" ")</span><span class="sxs-lookup"><span data-stu-id="83dfc-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="83dfc-133">La `\DDD` secuencia de escape es notación decimal, no notación octal como en la mayoría de los otros idiomas.</span><span class="sxs-lookup"><span data-stu-id="83dfc-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="83dfc-134">Por lo `8` `9` tanto, los dígitos `\032` y son válidos, y una secuencia de representa un espacio (U+0020), mientras que ese mismo punto de código en notación octal sería `\040`.</span><span class="sxs-lookup"><span data-stu-id="83dfc-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="83dfc-135">Al estar restringidos a un rango de 0 - `\DDD` `\x` 255 (0xFF), las secuencias y las secuencias de escape son efectivamente el juego de caracteres [ISO-8859-1,](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) ya que coincide con los primeros 256 puntos de código Unicode.</span><span class="sxs-lookup"><span data-stu-id="83dfc-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

## <a name="verbatim-strings"></a><span data-ttu-id="83dfc-136">Cuerdas literales</span><span class="sxs-lookup"><span data-stu-id="83dfc-136">Verbatim Strings</span></span>

<span data-ttu-id="83dfc-137">Si va precedido por el símbolo de la tecla , el literal es una cadena literal.</span><span class="sxs-lookup"><span data-stu-id="83dfc-137">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="83dfc-138">Esto significa que se omiten las secuencias de escape, excepto que dos caracteres de comillas se interpretan como un carácter de comillas.</span><span class="sxs-lookup"><span data-stu-id="83dfc-138">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

## <a name="triple-quoted-strings"></a><span data-ttu-id="83dfc-139">Cuerdas triples citadas</span><span class="sxs-lookup"><span data-stu-id="83dfc-139">Triple Quoted Strings</span></span>

<span data-ttu-id="83dfc-140">Además, una cadena puede estar entre comillas triples.</span><span class="sxs-lookup"><span data-stu-id="83dfc-140">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="83dfc-141">En este caso, se omiten todas las secuencias de escape, incluidos los caracteres de comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="83dfc-141">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="83dfc-142">Para especificar una cadena que contenga una cadena entre comillas incrustada, puede usar una cadena literal o una cadena de comillas triples.</span><span class="sxs-lookup"><span data-stu-id="83dfc-142">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="83dfc-143">Si utiliza una cadena literal, debe especificar dos caracteres de comillas para indicar un carácter de comillas simples.</span><span class="sxs-lookup"><span data-stu-id="83dfc-143">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="83dfc-144">Si utiliza una cadena de comillas triples, puede usar los caracteres de comillas simples sin que se analicen como el final de la cadena.</span><span class="sxs-lookup"><span data-stu-id="83dfc-144">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="83dfc-145">Esta técnica puede ser útil cuando se trabaja con XML u otras estructuras que incluyen comillas incrustadas.</span><span class="sxs-lookup"><span data-stu-id="83dfc-145">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="83dfc-146">En el código, se aceptan cadenas que tienen saltos de línea y los saltos de línea se interpretan literalmente como líneas nuevas, a menos que un carácter de barra diagonal inversa sea el último carácter antes del salto de línea.</span><span class="sxs-lookup"><span data-stu-id="83dfc-146">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="83dfc-147">El espacio en blanco inicial en la siguiente línea se omite cuando se utiliza el carácter de barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="83dfc-147">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="83dfc-148">El código siguiente genera `str1` una `"abc\ndef"` cadena que `str2` tiene `"abcdef"`valor y una cadena que tiene valor .</span><span class="sxs-lookup"><span data-stu-id="83dfc-148">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a><span data-ttu-id="83dfc-149">Indización y segmentación de cadenas</span><span class="sxs-lookup"><span data-stu-id="83dfc-149">String Indexing and Slicing</span></span>

<span data-ttu-id="83dfc-150">Puede tener acceso a caracteres individuales en una cadena mediante la sintaxis de tipo matriz, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="83dfc-150">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="83dfc-151">El resultado es `b`</span><span class="sxs-lookup"><span data-stu-id="83dfc-151">The output is `b`.</span></span>

<span data-ttu-id="83dfc-152">O bien, puede extraer subcadenas mediante la sintaxis de sector de matriz, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="83dfc-152">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="83dfc-153">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="83dfc-153">The output is as follows.</span></span>

```console
abc
def
```

<span data-ttu-id="83dfc-154">Puede representar cadenas ASCII mediante matrices de `byte[]`bytes sin signo, escriba .</span><span class="sxs-lookup"><span data-stu-id="83dfc-154">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="83dfc-155">Agregue el `B` sufijo a un literal de cadena para indicar que es una cadena ASCII.</span><span class="sxs-lookup"><span data-stu-id="83dfc-155">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="83dfc-156">Los literales de cadena ASCII utilizados con matrices de bytes admiten las mismas secuencias de escape que las cadenas Unicode, excepto las secuencias de escape Unicode.</span><span class="sxs-lookup"><span data-stu-id="83dfc-156">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="83dfc-157">Operadores de cuerdas</span><span class="sxs-lookup"><span data-stu-id="83dfc-157">String Operators</span></span>

<span data-ttu-id="83dfc-158">El `+` operador se puede usar para concatenar cadenas, manteniendo la compatibilidad con las características de control de cadenas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="83dfc-158">The `+` operator can be used to concatenate strings, maintaining compatibility with the .NET Framework string handling features.</span></span> <span data-ttu-id="83dfc-159">En el ejemplo siguiente se muestra la concatenación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="83dfc-159">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="83dfc-160">Clase String</span><span class="sxs-lookup"><span data-stu-id="83dfc-160">String Class</span></span>

<span data-ttu-id="83dfc-161">Debido a que el tipo de cadena `System.String` en F `System.String` es en realidad un tipo de .NET Framework, todos los miembros están disponibles.</span><span class="sxs-lookup"><span data-stu-id="83dfc-161">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="83dfc-162">Esto incluye `+` el operador, que se utiliza `Length` para concatenar cadenas, la propiedad y la `Chars` propiedad, que devuelve la cadena como una matriz de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="83dfc-162">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="83dfc-163">Para obtener más información `System.String`acerca de las cadenas, consulte .</span><span class="sxs-lookup"><span data-stu-id="83dfc-163">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="83dfc-164">Mediante el `Chars` uso `System.String`de la propiedad de , puede tener acceso a los caracteres individuales de una cadena especificando un índice, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="83dfc-164">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="83dfc-165">Módulo de cadena</span><span class="sxs-lookup"><span data-stu-id="83dfc-165">String Module</span></span>

<span data-ttu-id="83dfc-166">La funcionalidad adicional para el `String` control de `FSharp.Core` cadenas se incluye en el módulo del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="83dfc-166">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="83dfc-167">Para obtener más información, vea [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="83dfc-167">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="83dfc-168">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83dfc-168">See also</span></span>

- [<span data-ttu-id="83dfc-169">Referencia del lenguaje f</span><span class="sxs-lookup"><span data-stu-id="83dfc-169">F# Language Reference</span></span>](index.md)
