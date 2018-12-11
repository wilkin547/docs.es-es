---
title: Cadenas (F#)
description: Obtenga información sobre cómo el F# tipo 'string' representa texto inmutable como una secuencia de caracteres Unicode.
ms.date: 05/16/2016
ms.openlocfilehash: 158e30224fe50c2324e40d550b75e6abaf843597
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127685"
---
# <a name="strings"></a><span data-ttu-id="f39ef-103">Cadenas</span><span class="sxs-lookup"><span data-stu-id="f39ef-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="f39ef-104">Los vínculos de la referencia de API de este artículo le llevarán a MSDN.</span><span class="sxs-lookup"><span data-stu-id="f39ef-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="f39ef-105">La referencia de API de docs.microsoft.com no está completa.</span><span class="sxs-lookup"><span data-stu-id="f39ef-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="f39ef-106">El `string` tipo representa texto inmutable como una secuencia de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="f39ef-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="f39ef-107">`string` es un alias de `System.String` en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f39ef-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="f39ef-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f39ef-108">Remarks</span></span>

<span data-ttu-id="f39ef-109">Literales de cadena se delimitan mediante el carácter de comillas dobles (").</span><span class="sxs-lookup"><span data-stu-id="f39ef-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="f39ef-110">El carácter de barra diagonal inversa ( \\ ) se usa para codificar caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="f39ef-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="f39ef-111">La barra diagonal inversa y el carácter siguiente juntos se conocen como un *secuencia de escape*.</span><span class="sxs-lookup"><span data-stu-id="f39ef-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="f39ef-112">Admitidas de secuencias de escape F# literales de cadena se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f39ef-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="f39ef-113">Carácter</span><span class="sxs-lookup"><span data-stu-id="f39ef-113">Character</span></span>|<span data-ttu-id="f39ef-114">Secuencia de escape</span><span class="sxs-lookup"><span data-stu-id="f39ef-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="f39ef-115">Retroceso</span><span class="sxs-lookup"><span data-stu-id="f39ef-115">Backspace</span></span>|`\b`|
|<span data-ttu-id="f39ef-116">Nueva línea</span><span class="sxs-lookup"><span data-stu-id="f39ef-116">Newline</span></span>|`\n`|
|<span data-ttu-id="f39ef-117">Retorno de carro</span><span class="sxs-lookup"><span data-stu-id="f39ef-117">Carriage return</span></span>|`\r`|
|<span data-ttu-id="f39ef-118">Tab</span><span class="sxs-lookup"><span data-stu-id="f39ef-118">Tab</span></span>|`\t`|
|<span data-ttu-id="f39ef-119">Barra diagonal inversa</span><span class="sxs-lookup"><span data-stu-id="f39ef-119">Backslash</span></span>|`\\`|
|<span data-ttu-id="f39ef-120">Comillas</span><span class="sxs-lookup"><span data-stu-id="f39ef-120">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="f39ef-121">Apóstrofo</span><span class="sxs-lookup"><span data-stu-id="f39ef-121">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="f39ef-122">Carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="f39ef-122">Unicode character</span></span>|<span data-ttu-id="f39ef-123">`\uXXXX` o `\UXXXX` (donde `X` indica un dígito hexadecimal)</span><span class="sxs-lookup"><span data-stu-id="f39ef-123">`\uXXXX` or `\UXXXX` (where `X` indicates a hexadecimal digit)</span></span>|

<span data-ttu-id="f39ef-124">Si va precedido por el símbolo @, el literal es una cadena textual.</span><span class="sxs-lookup"><span data-stu-id="f39ef-124">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="f39ef-125">Esto significa que se omiten las secuencias de escape, excepto en que dos caracteres de comilla se interpretan como caracteres de una comilla simple.</span><span class="sxs-lookup"><span data-stu-id="f39ef-125">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="f39ef-126">Además, una cadena puede estar delimitada por comillas triples.</span><span class="sxs-lookup"><span data-stu-id="f39ef-126">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="f39ef-127">En este caso, se omiten todas las secuencias de escape, incluidos los caracteres de comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="f39ef-127">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="f39ef-128">Para especificar una cadena que contiene incrustado cadena entre comillas, se puede usar una cadena textual o una cadena entre comillas el triple.</span><span class="sxs-lookup"><span data-stu-id="f39ef-128">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="f39ef-129">Si usa una cadena textual, debe especificar dos caracteres de comillas para indicar un carácter de comilla simple.</span><span class="sxs-lookup"><span data-stu-id="f39ef-129">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="f39ef-130">Si usa una cadena entre comillas el triple, puede utilizar los caracteres de comillas simples sin ellos que se va a analizar como el final de la cadena.</span><span class="sxs-lookup"><span data-stu-id="f39ef-130">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="f39ef-131">Esta técnica puede ser útil al trabajar con XML u otras estructuras que incluyen las comillas incrustadas.</span><span class="sxs-lookup"><span data-stu-id="f39ef-131">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="f39ef-132">En el código, se aceptan cadenas que tienen los saltos de línea y los saltos de línea se interpretan literalmente como líneas nuevas, a menos que un carácter de barra diagonal inversa es el último carácter antes del salto de línea.</span><span class="sxs-lookup"><span data-stu-id="f39ef-132">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="f39ef-133">Espacio en blanco inicial en la línea siguiente se omite cuando se usa el carácter de barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="f39ef-133">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="f39ef-134">El siguiente código genera una cadena `str1` que tiene el valor `"abc\ndef"` y una cadena `str2` que tiene el valor `"abcdef"`.</span><span class="sxs-lookup"><span data-stu-id="f39ef-134">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="f39ef-135">Puede tener acceso a caracteres individuales de una cadena con sintaxis de matriz, como sigue.</span><span class="sxs-lookup"><span data-stu-id="f39ef-135">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="f39ef-136">El resultado es `b`</span><span class="sxs-lookup"><span data-stu-id="f39ef-136">The output is `b`.</span></span>

<span data-ttu-id="f39ef-137">O bien, puede extraer subcadenas mediante la sintaxis de segmento de matriz, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f39ef-137">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="f39ef-138">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="f39ef-138">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="f39ef-139">Puede representar cadenas ASCII por las matrices de bytes sin signo, tipo `byte[]`.</span><span class="sxs-lookup"><span data-stu-id="f39ef-139">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="f39ef-140">Agregue el sufijo `B` a un literal de cadena para indicar que es una cadena ASCII.</span><span class="sxs-lookup"><span data-stu-id="f39ef-140">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="f39ef-141">Literales de cadena ASCII utilizados con matrices de bytes compatible con las mismas secuencias de escape como cadenas Unicode, excepto para las secuencias de escape Unicode.</span><span class="sxs-lookup"><span data-stu-id="f39ef-141">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="f39ef-142">Operadores de cadena</span><span class="sxs-lookup"><span data-stu-id="f39ef-142">String Operators</span></span>

<span data-ttu-id="f39ef-143">Hay dos maneras para concatenar cadenas: mediante el uso de la `+` operador o mediante el `^` operador.</span><span class="sxs-lookup"><span data-stu-id="f39ef-143">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="f39ef-144">El `+` operador mantiene la compatibilidad con las características de tratamiento de cadenas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f39ef-144">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="f39ef-145">El ejemplo siguiente muestra la concatenación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="f39ef-145">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="f39ef-146">Clase de cadena</span><span class="sxs-lookup"><span data-stu-id="f39ef-146">String Class</span></span>

<span data-ttu-id="f39ef-147">Dado que la cadena de tipo en F# es realmente una versión de .NET Framework `System.String` escribir todo el `System.String` miembros están disponibles.</span><span class="sxs-lookup"><span data-stu-id="f39ef-147">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="f39ef-148">Esto incluye la `+` operador, que se utiliza para concatenar cadenas, la `Length` propiedad y el `Chars` propiedad, que devuelve la cadena como una matriz de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="f39ef-148">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="f39ef-149">Para obtener más información acerca de las cadenas, vea `System.String`.</span><span class="sxs-lookup"><span data-stu-id="f39ef-149">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="f39ef-150">Mediante el uso de la `Chars` propiedad de `System.String`, puede tener acceso a los caracteres individuales de una cadena mediante la especificación de un índice, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f39ef-150">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="f39ef-151">Módulo de la cadena</span><span class="sxs-lookup"><span data-stu-id="f39ef-151">String Module</span></span>

<span data-ttu-id="f39ef-152">Funcionalidad adicional para el control de la cadena se incluye en el `String` módulo en el `FSharp.Core` espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="f39ef-152">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="f39ef-153">Para obtener más información, consulte [Core.String módulo](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="f39ef-153">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="f39ef-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="f39ef-154">See also</span></span>

- [<span data-ttu-id="f39ef-155">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="f39ef-155">F# Language Reference</span></span>](index.md)
