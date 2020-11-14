---
title: División de cadenas mediante String.Split (Guía de C#)
description: El método Split devuelve una matriz de cadenas divididas por un conjunto de delimitadores. Es una manera sencilla de extraer subcadenas de una cadena.
ms.date: 01/03/2018
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
ms.custom: mvc
ms.openlocfilehash: 5361a3c60905edd19b180c5ddb14064a85f64337
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400505"
---
# <a name="how-to-separate-strings-using-stringsplit-in-c"></a><span data-ttu-id="f1084-104">Procedimiento para separar cadenas mediante String.Split en C\#</span><span class="sxs-lookup"><span data-stu-id="f1084-104">How to separate strings using String.Split in C\#</span></span>

<span data-ttu-id="f1084-105">El método <xref:System.String.Split%2A?displayProperty=nameWithType> crea una matriz de subcadenas mediante la división de la cadena de entrada en función de uno o varios delimitadores.</span><span class="sxs-lookup"><span data-stu-id="f1084-105">The <xref:System.String.Split%2A?displayProperty=nameWithType> method creates an array of substrings by splitting the input string based on one or more delimiters.</span></span> <span data-ttu-id="f1084-106">A menudo, este método es la manera más fácil de separar una cadena en límites de palabras.</span><span class="sxs-lookup"><span data-stu-id="f1084-106">This method is often the easiest way to separate a string on word boundaries.</span></span> <span data-ttu-id="f1084-107">También sirve para dividir las cadenas en otras cadenas o caracteres específicos.</span><span class="sxs-lookup"><span data-stu-id="f1084-107">It's also used to split strings on other specific characters or strings.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="f1084-108">Este código divide una frase común en una matriz de cadenas para cada palabra.</span><span class="sxs-lookup"><span data-stu-id="f1084-108">The following code splits a common phrase into an array of strings for each word.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet1":::

<span data-ttu-id="f1084-109">Todas las instancias de un carácter separador generan un valor en la matriz devuelta.</span><span class="sxs-lookup"><span data-stu-id="f1084-109">Every instance of a separator character produces a value in the returned array.</span></span> <span data-ttu-id="f1084-110">Los caracteres separadores consecutivos generan la cadena vacía como un valor en la matriz devuelta.</span><span class="sxs-lookup"><span data-stu-id="f1084-110">Consecutive separator characters produce the empty string as a value in the returned array.</span></span> <span data-ttu-id="f1084-111">Puede ver cómo se crea una cadena vacía en el ejemplo siguiente, en el que se usa el carácter de espacio como separador.</span><span class="sxs-lookup"><span data-stu-id="f1084-111">You can see how an empty string is created in the following example, which uses the space character as a separator.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet2":::

<span data-ttu-id="f1084-112">Este comportamiento facilita formatos como los de los archivos de valores separados por comas (CSV) que representan datos tabulares.</span><span class="sxs-lookup"><span data-stu-id="f1084-112">This behavior makes it easier for formats like comma-separated values (CSV) files representing tabular data.</span></span> <span data-ttu-id="f1084-113">Las comas consecutivas representan una columna en blanco.</span><span class="sxs-lookup"><span data-stu-id="f1084-113">Consecutive commas represent a blank column.</span></span>

<span data-ttu-id="f1084-114">Puede pasar un parámetro <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> opcional para excluir cualquier cadena vacía en la matriz devuelta.</span><span class="sxs-lookup"><span data-stu-id="f1084-114">You can pass an optional <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> parameter to exclude any empty strings in the returned array.</span></span> <span data-ttu-id="f1084-115">Para un procesamiento más complicado de la colección devuelta, puede usar [LINQ](../programming-guide/concepts/linq/index.md) para manipular la secuencia de resultados.</span><span class="sxs-lookup"><span data-stu-id="f1084-115">For more complicated processing of the returned collection, you can use [LINQ](../programming-guide/concepts/linq/index.md) to manipulate the result sequence.</span></span>

<span data-ttu-id="f1084-116"><xref:System.String.Split%2A?displayProperty=nameWithType> puede usar varios caracteres separadores.</span><span class="sxs-lookup"><span data-stu-id="f1084-116"><xref:System.String.Split%2A?displayProperty=nameWithType> can use multiple separator characters.</span></span>
<span data-ttu-id="f1084-117">En este ejemplo se usan espacios, comas, puntos, dos puntos y tabulaciones como caracteres de separación, que se pasan a <xref:System.String.Split%2A> en una matriz.</span><span class="sxs-lookup"><span data-stu-id="f1084-117">The following example uses spaces, commas, periods, colons, and tabs as separating characters, which are passed to <xref:System.String.Split%2A> in an array .</span></span>
<span data-ttu-id="f1084-118">En el bucle al final del código se muestra cada una de las palabras de la matriz devuelta.</span><span class="sxs-lookup"><span data-stu-id="f1084-118">The loop at the bottom of the code displays each of the words in the returned array.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet3":::

<span data-ttu-id="f1084-119">Las instancias consecutivas de cualquier separador generan la cadena vacía en la matriz de salida:</span><span class="sxs-lookup"><span data-stu-id="f1084-119">Consecutive instances of any separator produce the empty string in the output array:</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet4":::

<span data-ttu-id="f1084-120"><xref:System.String.Split%2A?displayProperty=nameWithType> puede tomar una matriz de cadenas (secuencias de caracteres que actúan como separadores para analizar la cadena de destino, en lugar de caracteres individuales).</span><span class="sxs-lookup"><span data-stu-id="f1084-120"><xref:System.String.Split%2A?displayProperty=nameWithType> can take an array of strings (character sequences that act as separators for parsing the target string, instead of single characters).</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet5":::

## <a name="see-also"></a><span data-ttu-id="f1084-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1084-121">See also</span></span>

- [<span data-ttu-id="f1084-122">Extracción de elementos de una cadena</span><span class="sxs-lookup"><span data-stu-id="f1084-122">Extract elements from a string</span></span>](../../standard/base-types/divide-up-strings.md)
- [<span data-ttu-id="f1084-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f1084-123">C# programming guide</span></span>](../programming-guide/index.md)
- [<span data-ttu-id="f1084-124">Cadenas</span><span class="sxs-lookup"><span data-stu-id="f1084-124">Strings</span></span>](../programming-guide/strings/index.md)
- [<span data-ttu-id="f1084-125">Expresiones regulares de .NET</span><span class="sxs-lookup"><span data-stu-id="f1084-125">.NET regular expressions</span></span>](../../standard/base-types/regular-expressions.md)
