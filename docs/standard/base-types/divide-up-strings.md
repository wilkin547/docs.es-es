---
title: Separación de cadenas en subcadenas
description: Obtenga información sobre las distintas técnicas para extraer partes de una cadena, como String.Split, expresiones regulares y String.Substring.
ms.date: 10/30/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET], breaking up
ms.openlocfilehash: b753476b7d8e5808fdcacc6f28bd1de5f8b232bb
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829654"
---
# <a name="extract-substrings-from-a-string"></a><span data-ttu-id="8dd9f-103">Extracción de subcadenas de una cadena</span><span class="sxs-lookup"><span data-stu-id="8dd9f-103">Extract substrings from a string</span></span>

<span data-ttu-id="8dd9f-104">En este artículo se tratan algunas técnicas diferentes para extraer partes de una cadena.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-104">This article covers some different techniques for extracting parts of a string.</span></span>

- <span data-ttu-id="8dd9f-105">Use el [método Split](#stringsplit-method) cuando las subcadenas que desee están separadas por un carácter de delimitador conocido (o caracteres).</span><span class="sxs-lookup"><span data-stu-id="8dd9f-105">Use the [Split method](#stringsplit-method) when the substrings you want are separated by a known delimiting character (or characters).</span></span>
- <span data-ttu-id="8dd9f-106">Las [expresiones regulares](#regular-expressions) son útiles cuando la cadena se ajusta a un patrón fijo.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-106">[Regular expressions](#regular-expressions) are useful when the string conforms to a fixed pattern.</span></span>
- <span data-ttu-id="8dd9f-107">Use los [métodos IndexOf y Substring](#stringindexof-and-stringsubstring-methods) cuando no desee extraer *todas* las subcadenas de una cadena.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-107">Use the [IndexOf and Substring methods](#stringindexof-and-stringsubstring-methods) in conjunction when you don't want to extract *all* of the substrings in a string.</span></span>

## <a name="stringsplit-method"></a><span data-ttu-id="8dd9f-108">Método String.Split</span><span class="sxs-lookup"><span data-stu-id="8dd9f-108">String.Split method</span></span>

<span data-ttu-id="8dd9f-109"><xref:System.String.Split%2A?displayProperty=nameWithType> proporciona una serie de sobrecargas para ayudarle a dividir una cadena en un grupo de subcadenas en función de uno o más caracteres delimitadores que especifique.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-109"><xref:System.String.Split%2A?displayProperty=nameWithType> provides a handful of overloads to help you break up a string into a group of substrings based on one or more delimiting characters that you specify.</span></span> <span data-ttu-id="8dd9f-110">Puede elegir limitar el número total de subcadenas en el resultado final, recortar los caracteres de espacio en blanco de las subcadenas o excluir las subcadenas vacías.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-110">You can choose to limit the total number of substrings in the final result, trim white-space characters from substrings, or exclude empty substrings.</span></span>

<span data-ttu-id="8dd9f-111">En los siguientes ejemplos se muestran tres sobrecargas diferentes de `String.Split()`.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-111">The following examples show three different overloads of `String.Split()`.</span></span> <span data-ttu-id="8dd9f-112">En el primer ejemplo se llama a la sobrecarga <xref:System.String.Split(System.Char[])> sin pasar ningún carácter separador.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-112">The first example calls the <xref:System.String.Split(System.Char[])> overload without passing any separator characters.</span></span> <span data-ttu-id="8dd9f-113">Cuando no se especifica ningún carácter delimitador, `String.Split()` usa delimitadores predeterminados, que son caracteres de espacio en blanco, para dividir la cadena.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-113">When you don't specify any delimiting characters, `String.Split()` uses default delimiters, which are white-space characters, to split up the string.</span></span>

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#1)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="1":::

<span data-ttu-id="8dd9f-114">Como puede ver, los caracteres de punto (`.`) se incluyen en dos de las subcadenas.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-114">As you can see, the period characters (`.`) are included in two of the substrings.</span></span> <span data-ttu-id="8dd9f-115">Si desea excluir los caracteres de punto, puede agregar el carácter de punto como un carácter delimitador adicional.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-115">If you want to exclude the period characters, you can add the period character as an additional delimiting character.</span></span> <span data-ttu-id="8dd9f-116">En el ejemplo siguiente se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-116">The next example shows how to do this.</span></span>

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#2)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="2":::

<span data-ttu-id="8dd9f-117">Los puntos desaparecen de las subcadenas, pero ahora se han incluido dos subcadenas vacías adicionales.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-117">The periods are gone from the substrings, but now two extra empty substrings have been included.</span></span> <span data-ttu-id="8dd9f-118">Esta subcadena vacía representa la subcadena entre la palabra y el punto que la sigue.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-118">These empty substring represent the substring between the word and the period that follows it.</span></span> <span data-ttu-id="8dd9f-119">Para omitir las subcadenas vacías de la matriz resultante, puede llamar a la sobrecarga <xref:System.String.Split(System.Char[],System.StringSplitOptions)> y especificar <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> para el parámetro `options`.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-119">To omit empty substrings from the resulting array, you can call the <xref:System.String.Split(System.Char[],System.StringSplitOptions)> overload and specify <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> for the `options` parameter.</span></span>

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#3)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="3":::

## <a name="regular-expressions"></a><span data-ttu-id="8dd9f-120">Expresiones regulares</span><span class="sxs-lookup"><span data-stu-id="8dd9f-120">Regular expressions</span></span>

<span data-ttu-id="8dd9f-121">Si la cadena se ajusta a un patrón fijo, puede usar una expresión regular para extraer y controlar sus elementos.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-121">If your string conforms to a fixed pattern, you can use a regular expression to extract and handle its elements.</span></span> <span data-ttu-id="8dd9f-122">Por ejemplo, si las cadenas adoptan el formato "*número* *operando* *número*", puede utilizar una [expresión regular](regular-expressions.md) para extraer y administrar los elementos de la cadena.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-122">For example, if strings take the form "*number* *operand* *number*", you can use a [regular expression](regular-expressions.md) to extract and handle the string's elements.</span></span> <span data-ttu-id="8dd9f-123">Este es un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8dd9f-123">Here's an example:</span></span>

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="1" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="1":::

<span data-ttu-id="8dd9f-124">El patrón de expresión regular `(\d+)\s+([-+*/])\s+(\d+)` se define como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="8dd9f-124">The regular expression pattern `(\d+)\s+([-+*/])\s+(\d+)` is defined like this:</span></span>

|<span data-ttu-id="8dd9f-125">Patrón</span><span class="sxs-lookup"><span data-stu-id="8dd9f-125">Pattern</span></span>|<span data-ttu-id="8dd9f-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="8dd9f-126">Description</span></span>|
|-------------|-----------------|
|`(\d+)`|<span data-ttu-id="8dd9f-127">Buscar coincidencias con uno o más dígitos decimales.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-127">Match one or more decimal digits.</span></span> <span data-ttu-id="8dd9f-128">Este es el primer grupo de captura.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-128">This is the first capturing group.</span></span>|
|`\s+`|<span data-ttu-id="8dd9f-129">Coincide con uno o varios caracteres de espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-129">Match one or more white-space characters.</span></span>|
|`([-+*/])`|<span data-ttu-id="8dd9f-130">Coincide con un signo de operador aritmético (+, -, \*, o /).</span><span class="sxs-lookup"><span data-stu-id="8dd9f-130">Match an arithmetic operator sign (+, -, \*, or /).</span></span> <span data-ttu-id="8dd9f-131">Este es el segundo grupo de captura.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-131">This is the second capturing group.</span></span>|
|`\s+`|<span data-ttu-id="8dd9f-132">Coincide con uno o varios caracteres de espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-132">Match one or more white-space characters.</span></span>|
|`(\d+)`|<span data-ttu-id="8dd9f-133">Buscar coincidencias con uno o más dígitos decimales.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-133">Match one or more decimal digits.</span></span> <span data-ttu-id="8dd9f-134">Éste es el tercer grupo de captura.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-134">This is the third capturing group.</span></span>|

<span data-ttu-id="8dd9f-135">También puede usar una expresión regular para extraer subcadenas de una cadena basada en un patrón en lugar de un conjunto fijo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-135">You can also use a regular expression to extract substrings from a string based on a pattern rather than a fixed set of characters.</span></span> <span data-ttu-id="8dd9f-136">Este es un escenario común cuando se produce cualquiera de estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="8dd9f-136">This is a common scenario when either of these conditions occurs:</span></span>

- <span data-ttu-id="8dd9f-137">Uno o varios caracteres delimitadores no *siempre* sirven como delimitador en la instancia de <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-137">One or more of the delimiter characters does not *always* serve as a delimiter in the <xref:System.String> instance.</span></span>

- <span data-ttu-id="8dd9f-138">La secuencia y el número de caracteres delimitadores son variables o desconocidos.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-138">The sequence and number of delimiter characters is variable or unknown.</span></span>

<span data-ttu-id="8dd9f-139">Por ejemplo, el método <xref:System.String.Split%2A> no se puede usar para dividir la cadena siguiente, porque el número de caracteres `\n` (nueva línea) es variable y no siempre sirven como delimitadores.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-139">For example, the <xref:System.String.Split%2A> method cannot be used to split the following string, because the number of `\n` (newline) characters is variable, and they don't always serve as delimiters.</span></span>

```text
[This is captured\ntext.]\n\n[\n[This is more captured text.]\n]
\n[Some more captured text:\n   Option1\n   Option2][Terse text.]
```

<span data-ttu-id="8dd9f-140">Una expresión regular puede dividir fácilmente esta cadena, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-140">A regular expression can split this string easily, as the following example shows.</span></span>

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="2" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="2":::

<span data-ttu-id="8dd9f-141">El patrón de expresión regular `\[([^\[\]]+)\]` se define como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="8dd9f-141">The regular expression pattern `\[([^\[\]]+)\]` is defined like this:</span></span>

|<span data-ttu-id="8dd9f-142">Patrón</span><span class="sxs-lookup"><span data-stu-id="8dd9f-142">Pattern</span></span>|<span data-ttu-id="8dd9f-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="8dd9f-143">Description</span></span>|
|-------------|-----------------|
|`\[`|<span data-ttu-id="8dd9f-144">Coincide con un corchete de apertura.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-144">Match an opening bracket.</span></span>|
|`([^\[\]]+)`|<span data-ttu-id="8dd9f-145">Coincide con cualquier carácter que no sea un corchete de apertura o de cierre una o varias veces.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-145">Match any character that is not an opening or a closing bracket one or more times.</span></span> <span data-ttu-id="8dd9f-146">Este es el primer grupo de captura.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-146">This is the first capturing group.</span></span>|
|`\]`|<span data-ttu-id="8dd9f-147">Coincide con un corchete de cierre.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-147">Match a closing bracket.</span></span>|

<span data-ttu-id="8dd9f-148">El método <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> es casi idéntico a <xref:System.String.Split%2A?displayProperty=nameWithType>, salvo que divide una cadena basándose en un patrón de expresión regular en lugar de un juego de caracteres fijo.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-148">The <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method is almost identical to <xref:System.String.Split%2A?displayProperty=nameWithType>, except that it splits a string based on a regular expression pattern instead of a fixed character set.</span></span> <span data-ttu-id="8dd9f-149">Por ejemplo, en el ejemplo siguiente se usa el método <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> para dividir una cadena que contiene subcadenas delimitadas por varias combinaciones de guiones y otros caracteres.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-149">For example, the following example uses the <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method to split a string that contains substrings delimited by various combinations of hyphens and other characters.</span></span>

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="3" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="3":::

<span data-ttu-id="8dd9f-150">El patrón de expresión regular `\s-\s?[+*]?\s?-\s` se define como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="8dd9f-150">The regular expression pattern `\s-\s?[+*]?\s?-\s` is defined like this:</span></span>

|<span data-ttu-id="8dd9f-151">Patrón</span><span class="sxs-lookup"><span data-stu-id="8dd9f-151">Pattern</span></span>|<span data-ttu-id="8dd9f-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="8dd9f-152">Description</span></span>|
|-------------|-----------------|
|`\s-`|<span data-ttu-id="8dd9f-153">Coincide con un carácter de espacio en blanco seguido de un guion.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-153">Match a white-space character followed by a hyphen.</span></span>|
|`\s?`|<span data-ttu-id="8dd9f-154">Busca coincidencias con cero o un carácter de espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-154">Match zero or one white-space character.</span></span>|
|`[+*]?`|<span data-ttu-id="8dd9f-155">Coincide con cero o una aparición del carácter + o \*.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-155">Match zero or one occurrence of either the + or \* character.</span></span>|
|`\s?`|<span data-ttu-id="8dd9f-156">Busca coincidencias con cero o un carácter de espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-156">Match zero or one white-space character.</span></span>|
|`-\s`|<span data-ttu-id="8dd9f-157">Coincide con un guion seguido de un carácter de espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-157">Match a hyphen followed by a white-space character.</span></span>|

## <a name="stringindexof-and-stringsubstring-methods"></a><span data-ttu-id="8dd9f-158">Métodos String.IndexOf y String.Substring</span><span class="sxs-lookup"><span data-stu-id="8dd9f-158">String.IndexOf and String.Substring methods</span></span>

<span data-ttu-id="8dd9f-159">Si no está interesado en todas las subcadenas de una cadena, puede que prefiera trabajar con uno de los métodos de comparación de cadenas que devuelve el índice en el que comienza la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-159">If you aren't interested in all of the substrings in a string, you might prefer to work with one of the string comparison methods that returns the index at which the match begins.</span></span> <span data-ttu-id="8dd9f-160">Después, puede llamar al método <xref:System.String.Substring%2A> para extraer la subcadena que desee.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-160">You can then call the <xref:System.String.Substring%2A> method to extract the substring that you want.</span></span> <span data-ttu-id="8dd9f-161">Entre los métodos de comparación de cadenas están los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8dd9f-161">The string comparison methods include:</span></span>

- <span data-ttu-id="8dd9f-162"><xref:System.String.IndexOf%2A>, que devuelve el índice basado en cero de la primera aparición de un carácter o cadena en una instancia de cadena.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-162"><xref:System.String.IndexOf%2A>, which returns the zero-based index of the first occurrence of a character or string in a string instance.</span></span>

- <span data-ttu-id="8dd9f-163"><xref:System.String.IndexOfAny%2A>, que devuelve el índice basado en cero de la instancia de cadena actual de la primera aparición de cualquier carácter de una matriz de caracteres.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-163"><xref:System.String.IndexOfAny%2A>, which returns the zero-based index in the current string instance of the first occurrence of any character in a character array.</span></span>

- <span data-ttu-id="8dd9f-164"><xref:System.String.LastIndexOf%2A>, que devuelve el índice basado en cero de la última aparición de un carácter o cadena en una instancia de cadena.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-164"><xref:System.String.LastIndexOf%2A>, which returns the zero-based index of the last occurrence of a character or string in a string instance.</span></span>

- <span data-ttu-id="8dd9f-165"><xref:System.String.LastIndexOfAny%2A>, que devuelve un índice basado en cero en la instancia de la cadena actual de la última aparición de cualquier carácter de una matriz de caracteres.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-165"><xref:System.String.LastIndexOfAny%2A>, which returns a zero-based index in the current string instance of the last occurrence of any character in a character array.</span></span>

<span data-ttu-id="8dd9f-166">En el ejemplo siguiente se utiliza el método <xref:System.String.IndexOf%2A> para encontrar los puntos de una cadena.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-166">The following example uses the <xref:System.String.IndexOf%2A> method to find the periods in a string.</span></span> <span data-ttu-id="8dd9f-167">A continuación, usa el método <xref:System.String.Substring%2A> para devolver oraciones completas.</span><span class="sxs-lookup"><span data-stu-id="8dd9f-167">It then uses the <xref:System.String.Substring%2A> method to return full sentences.</span></span>

:::code language="csharp" source="snippets/parse-strings/csharp/indexof.cs" id="1" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/indexof.vb" id="1":::

## <a name="see-also"></a><span data-ttu-id="8dd9f-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="8dd9f-168">See also</span></span>

- [<span data-ttu-id="8dd9f-169">Operaciones básicas de cadenas en .NET</span><span class="sxs-lookup"><span data-stu-id="8dd9f-169">Basic string operations in .NET</span></span>](basic-string-operations.md)
- [<span data-ttu-id="8dd9f-170">Expresiones regulares de .NET</span><span class="sxs-lookup"><span data-stu-id="8dd9f-170">.NET regular expressions</span></span>](regular-expressions.md)
- [<span data-ttu-id="8dd9f-171">Procedimiento para analizar cadenas mediante String.Split en C#</span><span class="sxs-lookup"><span data-stu-id="8dd9f-171">How to parse strings using String.Split in C#</span></span>](../../csharp/how-to/parse-strings-using-split.md)
