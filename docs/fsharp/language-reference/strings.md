---
title: Cadenas (F#)
description: "Obtenga información acerca de cómo el tipo 'string' F # representa texto inmutable como una secuencia de caracteres Unicode."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: bf3c15db43c6419222dc3e5b32ac8947a53982f0
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="strings"></a><span data-ttu-id="3ebe2-103">Cadenas</span><span class="sxs-lookup"><span data-stu-id="3ebe2-103">Strings</span></span>

> [!NOTE]
<span data-ttu-id="3ebe2-104">Los vínculos de la referencia de API de este artículo le llevarán a MSDN.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="3ebe2-105">La referencia de API de docs.microsoft.com no está completa.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="3ebe2-106">El `string` tipo representa texto inmutable como una secuencia de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="3ebe2-107">`string` es un alias de `System.String` en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="3ebe2-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3ebe2-108">Remarks</span></span>
<span data-ttu-id="3ebe2-109">Literales de cadena se delimitan mediante el carácter de comillas dobles (").</span><span class="sxs-lookup"><span data-stu-id="3ebe2-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="3ebe2-110">El carácter de barra diagonal inversa (\) se usa para codificar caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-110">The backslash character (\) is used to encode certain special characters.</span></span> <span data-ttu-id="3ebe2-111">La barra diagonal inversa y el carácter siguiente juntos se conocen como un *secuencia de escape*.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="3ebe2-112">Admitidos en F # en la tabla siguiente se muestran literales de cadena de secuencias de escape.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="3ebe2-113">Carácter</span><span class="sxs-lookup"><span data-stu-id="3ebe2-113">Character</span></span>|<span data-ttu-id="3ebe2-114">Secuencia de escape</span><span class="sxs-lookup"><span data-stu-id="3ebe2-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="3ebe2-115">Retroceso</span><span class="sxs-lookup"><span data-stu-id="3ebe2-115">Backspace</span></span>|<span data-ttu-id="3ebe2-116">\b</span><span class="sxs-lookup"><span data-stu-id="3ebe2-116">\b</span></span>|
|<span data-ttu-id="3ebe2-117">Nueva línea</span><span class="sxs-lookup"><span data-stu-id="3ebe2-117">Newline</span></span>|<span data-ttu-id="3ebe2-118">\n</span><span class="sxs-lookup"><span data-stu-id="3ebe2-118">\n</span></span>|
|<span data-ttu-id="3ebe2-119">Retorno de carro</span><span class="sxs-lookup"><span data-stu-id="3ebe2-119">Carriage return</span></span>|<span data-ttu-id="3ebe2-120">\r</span><span class="sxs-lookup"><span data-stu-id="3ebe2-120">\r</span></span>|
|<span data-ttu-id="3ebe2-121">Tab</span><span class="sxs-lookup"><span data-stu-id="3ebe2-121">Tab</span></span>|<span data-ttu-id="3ebe2-122">\t</span><span class="sxs-lookup"><span data-stu-id="3ebe2-122">\t</span></span>|
|<span data-ttu-id="3ebe2-123">Barra diagonal inversa</span><span class="sxs-lookup"><span data-stu-id="3ebe2-123">Backslash</span></span>|\\|
|<span data-ttu-id="3ebe2-124">Comillas</span><span class="sxs-lookup"><span data-stu-id="3ebe2-124">Quotation mark</span></span>|\"|
|<span data-ttu-id="3ebe2-125">Apóstrofo</span><span class="sxs-lookup"><span data-stu-id="3ebe2-125">Apostrophe</span></span>|\'|
|<span data-ttu-id="3ebe2-126">Carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="3ebe2-126">Unicode character</span></span>|<span data-ttu-id="3ebe2-127">\u*XXXX* o \U*XXXXXXXX* (donde *X* indica un dígito hexadecimal)</span><span class="sxs-lookup"><span data-stu-id="3ebe2-127">\u*XXXX* or \U*XXXXXXXX* (where *X* indicates a hexadecimal digit)</span></span>|

<span data-ttu-id="3ebe2-128">Si va precedida por el símbolo @, el literal es una cadena textual.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-128">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="3ebe2-129">Esto significa que se omiten las secuencias de escape, excepto en que dos caracteres de comillas se interpretan como caracteres de una comilla simple.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-129">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="3ebe2-130">Además, una cadena puede incluir entre comillas triples.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-130">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="3ebe2-131">En este caso, se omiten todas las secuencias de escape, incluidos los caracteres de comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-131">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="3ebe2-132">Para especificar una cadena que contiene un cadena entre comillas, puede usar una cadena textual o una cadena entre comillas el triple.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-132">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="3ebe2-133">Si usa una cadena textual, debe especificar dos caracteres de comillas para indicar un carácter de comilla simple.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-133">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="3ebe2-134">Si utiliza una cadena entre comillas el triple, puede utilizar los caracteres de comilla simple sin ellos que se va a analizar como el final de la cadena.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-134">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="3ebe2-135">Esta técnica puede ser útil cuando se trabaja con XML y otras estructuras que incluyen las comillas incrustadas.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-135">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="3ebe2-136">En el código, se aceptan cadenas que tienen saltos de línea y los saltos de línea se interpretan literalmente como líneas nuevas, a menos que un carácter de barra diagonal inversa es el último carácter delante del salto de línea.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-136">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="3ebe2-137">Espacio en blanco inicial en la línea siguiente se omite cuando se utiliza el carácter de barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-137">Leading whitespace on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="3ebe2-138">El código siguiente genera una cadena de `str1` que tiene el valor `"abc\n     def"` y una cadena `str2` que tiene el valor `"abcdef"`.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-138">The following code produces a string `str1` that has value `"abc\n     def"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="3ebe2-139">Puede tener acceso a caracteres individuales de una cadena utilizando la sintaxis de matriz, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-139">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="3ebe2-140">El resultado es `b`</span><span class="sxs-lookup"><span data-stu-id="3ebe2-140">The output is `b`.</span></span>

<span data-ttu-id="3ebe2-141">O bien, se pueden extraer subcadenas mediante la sintaxis de segmento de matriz, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-141">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="3ebe2-142">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-142">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="3ebe2-143">Puede representar cadenas ASCII mediante matrices de bytes sin signo, tipo `byte[]`.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-143">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="3ebe2-144">Agregue el sufijo `B` a un literal de cadena para indicar que es una cadena ASCII.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-144">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="3ebe2-145">Literales de cadena ASCII utilizados con matrices de bytes admiten las mismas secuencias de escape como cadenas de Unicode, excepto para las secuencias de escape Unicode.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-145">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]
    
## <a name="string-operators"></a><span data-ttu-id="3ebe2-146">Operadores de cadena</span><span class="sxs-lookup"><span data-stu-id="3ebe2-146">String Operators</span></span>
<span data-ttu-id="3ebe2-147">Hay dos maneras para concatenar cadenas: mediante el uso de la `+` operador o mediante el `^` operador.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-147">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="3ebe2-148">El `+` operador mantiene la compatibilidad con las características de administración de cadenas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-148">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="3ebe2-149">En el ejemplo siguiente se muestra la concatenación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-149">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]
    
## <a name="string-class"></a><span data-ttu-id="3ebe2-150">Clase de cadena</span><span class="sxs-lookup"><span data-stu-id="3ebe2-150">String Class</span></span>
<span data-ttu-id="3ebe2-151">Porque el tipo de cadena en F # es realmente un .NET Framework `System.String` escriba todos los `System.String` miembros están disponibles.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-151">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="3ebe2-152">Esto incluye la `+` operador, que se utiliza para concatenar cadenas, el `Length` propiedad y el `Chars` propiedad, que devuelve la cadena como una matriz de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-152">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="3ebe2-153">Para obtener más información acerca de las cadenas, vea `System.String`.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-153">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="3ebe2-154">Mediante el uso de la `Chars` propiedad de `System.String`, puede tener acceso a los caracteres individuales de una cadena especificando un índice, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-154">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]
    
## <a name="string-module"></a><span data-ttu-id="3ebe2-155">Módulo de cadena</span><span class="sxs-lookup"><span data-stu-id="3ebe2-155">String Module</span></span>
<span data-ttu-id="3ebe2-156">Funcionalidad adicional para el control de la cadena se incluye en el `String` módulo en el `FSharp.Core` espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3ebe2-156">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="3ebe2-157">Para obtener más información, consulte [Core.String módulo](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="3ebe2-157">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="3ebe2-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ebe2-158">See Also</span></span>
[<span data-ttu-id="3ebe2-159">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="3ebe2-159">F# Language Reference</span></span>](index.md)
