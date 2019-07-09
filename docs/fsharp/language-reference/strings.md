---
title: Cadenas
description: Obtenga información sobre cómo el F# tipo 'string' representa texto inmutable como una secuencia de caracteres Unicode.
ms.date: 07/05/2019
ms.openlocfilehash: ec895723cc6d21a701a27b5d70d053bb681ce2b3
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "67660596"
---
# <a name="strings"></a><span data-ttu-id="e7809-103">Cadenas</span><span class="sxs-lookup"><span data-stu-id="e7809-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="e7809-104">Los vínculos de la referencia de API de este artículo le llevarán a MSDN.</span><span class="sxs-lookup"><span data-stu-id="e7809-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="e7809-105">La referencia de API de docs.microsoft.com no está completa.</span><span class="sxs-lookup"><span data-stu-id="e7809-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="e7809-106">El `string` tipo representa texto inmutable como una secuencia de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="e7809-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="e7809-107">`string` es un alias de `System.String` en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e7809-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="e7809-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e7809-108">Remarks</span></span>

<span data-ttu-id="e7809-109">Literales de cadena se delimitan mediante el carácter de comillas dobles (").</span><span class="sxs-lookup"><span data-stu-id="e7809-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="e7809-110">El carácter de barra diagonal inversa ( \\ ) se usa para codificar caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="e7809-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="e7809-111">La barra diagonal inversa y el carácter siguiente juntos se conocen como un *secuencia de escape*.</span><span class="sxs-lookup"><span data-stu-id="e7809-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="e7809-112">Admitidas de secuencias de escape F# literales de cadena se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e7809-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="e7809-113">Carácter</span><span class="sxs-lookup"><span data-stu-id="e7809-113">Character</span></span>|<span data-ttu-id="e7809-114">Secuencia de escape</span><span class="sxs-lookup"><span data-stu-id="e7809-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="e7809-115">Alerta</span><span class="sxs-lookup"><span data-stu-id="e7809-115">Alert</span></span>|`\a`|
|<span data-ttu-id="e7809-116">Retroceso</span><span class="sxs-lookup"><span data-stu-id="e7809-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="e7809-117">Avance de página</span><span class="sxs-lookup"><span data-stu-id="e7809-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="e7809-118">Nueva línea</span><span class="sxs-lookup"><span data-stu-id="e7809-118">Newline</span></span>|`\n`|
|<span data-ttu-id="e7809-119">Retorno de carro</span><span class="sxs-lookup"><span data-stu-id="e7809-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="e7809-120">Tab</span><span class="sxs-lookup"><span data-stu-id="e7809-120">Tab</span></span>|`\t`|
|<span data-ttu-id="e7809-121">Tabulación vertical</span><span class="sxs-lookup"><span data-stu-id="e7809-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="e7809-122">Barra diagonal inversa</span><span class="sxs-lookup"><span data-stu-id="e7809-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="e7809-123">Comillas</span><span class="sxs-lookup"><span data-stu-id="e7809-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="e7809-124">Apóstrofo</span><span class="sxs-lookup"><span data-stu-id="e7809-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="e7809-125">Carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="e7809-125">Unicode character</span></span>|<span data-ttu-id="e7809-126">`\DDD` (donde `D` indica un valor decimal dígitos; intervalo 000 - 255; por ejemplo, `\231` = "ç")</span><span class="sxs-lookup"><span data-stu-id="e7809-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="e7809-127">Carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="e7809-127">Unicode character</span></span>|<span data-ttu-id="e7809-128">`\xHH` (donde `H` indica un dígito hexadecimal; intervalo de 00 - FF; por ejemplo, `\xE7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="e7809-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="e7809-129">Carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="e7809-129">Unicode character</span></span>|<span data-ttu-id="e7809-130">`\uHHHH` (UTF-16) (donde `H` indica un dígito hexadecimal; el rango de 0000 - FFFF;  Por ejemplo, `\u00E7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="e7809-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="e7809-131">Carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="e7809-131">Unicode character</span></span>|<span data-ttu-id="e7809-132">`\U00HHHHHH` (UTF-32) (donde `H` indica un dígito hexadecimal; intervalo 000000 - 10FFFF;  Por ejemplo, `\U0001F47D` = "👽")</span><span class="sxs-lookup"><span data-stu-id="e7809-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="e7809-133">El `\DDD` secuencia de escape es la notación decimal, octal no notación como en la mayoría de los otra lenguajes.</span><span class="sxs-lookup"><span data-stu-id="e7809-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="e7809-134">Por lo tanto, los dígitos `8` y `9` son válidas y una secuencia de `\032` representa un espacio (u+0020), mientras que ese mismo punto de código en notación octal sería `\040`.</span><span class="sxs-lookup"><span data-stu-id="e7809-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="e7809-135">Está restringido a un intervalo de 0 - 255 (0xFF), el `\DDD` y `\x` secuencias de escape son efectivamente el [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) carácter conjunto, ya que coincide con los primeros 256 puntos de código Unicode.</span><span class="sxs-lookup"><span data-stu-id="e7809-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

<span data-ttu-id="e7809-136">Si va precedido por el símbolo @, el literal es una cadena textual.</span><span class="sxs-lookup"><span data-stu-id="e7809-136">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="e7809-137">Esto significa que se omiten las secuencias de escape, excepto en que dos caracteres de comilla se interpretan como caracteres de una comilla simple.</span><span class="sxs-lookup"><span data-stu-id="e7809-137">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="e7809-138">Además, una cadena puede estar delimitada por comillas triples.</span><span class="sxs-lookup"><span data-stu-id="e7809-138">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="e7809-139">En este caso, se omiten todas las secuencias de escape, incluidos los caracteres de comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="e7809-139">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="e7809-140">Para especificar una cadena que contiene incrustado cadena entre comillas, se puede usar una cadena textual o una cadena entre comillas el triple.</span><span class="sxs-lookup"><span data-stu-id="e7809-140">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="e7809-141">Si usa una cadena textual, debe especificar dos caracteres de comillas para indicar un carácter de comilla simple.</span><span class="sxs-lookup"><span data-stu-id="e7809-141">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="e7809-142">Si usa una cadena entre comillas el triple, puede utilizar los caracteres de comillas simples sin ellos que se va a analizar como el final de la cadena.</span><span class="sxs-lookup"><span data-stu-id="e7809-142">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="e7809-143">Esta técnica puede ser útil al trabajar con XML u otras estructuras que incluyen las comillas incrustadas.</span><span class="sxs-lookup"><span data-stu-id="e7809-143">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="e7809-144">En el código, se aceptan cadenas que tienen los saltos de línea y los saltos de línea se interpretan literalmente como líneas nuevas, a menos que un carácter de barra diagonal inversa es el último carácter antes del salto de línea.</span><span class="sxs-lookup"><span data-stu-id="e7809-144">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="e7809-145">Espacio en blanco inicial en la línea siguiente se omite cuando se usa el carácter de barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="e7809-145">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="e7809-146">El siguiente código genera una cadena `str1` que tiene el valor `"abc\ndef"` y una cadena `str2` que tiene el valor `"abcdef"`.</span><span class="sxs-lookup"><span data-stu-id="e7809-146">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="e7809-147">Puede tener acceso a caracteres individuales de una cadena con sintaxis de matriz, como sigue.</span><span class="sxs-lookup"><span data-stu-id="e7809-147">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="e7809-148">El resultado es `b`</span><span class="sxs-lookup"><span data-stu-id="e7809-148">The output is `b`.</span></span>

<span data-ttu-id="e7809-149">O bien, puede extraer subcadenas mediante la sintaxis de segmento de matriz, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e7809-149">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="e7809-150">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="e7809-150">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="e7809-151">Puede representar cadenas ASCII por las matrices de bytes sin signo, tipo `byte[]`.</span><span class="sxs-lookup"><span data-stu-id="e7809-151">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="e7809-152">Agregue el sufijo `B` a un literal de cadena para indicar que es una cadena ASCII.</span><span class="sxs-lookup"><span data-stu-id="e7809-152">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="e7809-153">Literales de cadena ASCII utilizados con matrices de bytes compatible con las mismas secuencias de escape como cadenas Unicode, excepto para las secuencias de escape Unicode.</span><span class="sxs-lookup"><span data-stu-id="e7809-153">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="e7809-154">Operadores de cadena</span><span class="sxs-lookup"><span data-stu-id="e7809-154">String Operators</span></span>

<span data-ttu-id="e7809-155">Hay dos maneras para concatenar cadenas: mediante el uso de la `+` operador o mediante el `^` operador.</span><span class="sxs-lookup"><span data-stu-id="e7809-155">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="e7809-156">El `+` operador mantiene la compatibilidad con las características de tratamiento de cadenas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e7809-156">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="e7809-157">El ejemplo siguiente muestra la concatenación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="e7809-157">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="e7809-158">Clase de cadena</span><span class="sxs-lookup"><span data-stu-id="e7809-158">String Class</span></span>

<span data-ttu-id="e7809-159">Dado que la cadena de tipo en F# es realmente una versión de .NET Framework `System.String` escribir todo el `System.String` miembros están disponibles.</span><span class="sxs-lookup"><span data-stu-id="e7809-159">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="e7809-160">Esto incluye la `+` operador, que se utiliza para concatenar cadenas, la `Length` propiedad y el `Chars` propiedad, que devuelve la cadena como una matriz de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="e7809-160">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="e7809-161">Para obtener más información acerca de las cadenas, vea `System.String`.</span><span class="sxs-lookup"><span data-stu-id="e7809-161">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="e7809-162">Mediante el uso de la `Chars` propiedad de `System.String`, puede tener acceso a los caracteres individuales de una cadena mediante la especificación de un índice, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e7809-162">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="e7809-163">Módulo de la cadena</span><span class="sxs-lookup"><span data-stu-id="e7809-163">String Module</span></span>

<span data-ttu-id="e7809-164">Funcionalidad adicional para el control de la cadena se incluye en el `String` módulo en el `FSharp.Core` espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e7809-164">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="e7809-165">Para obtener más información, consulte [Core.String módulo](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="e7809-165">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="e7809-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7809-166">See also</span></span>

- [<span data-ttu-id="e7809-167">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="e7809-167">F# Language Reference</span></span>](index.md)
