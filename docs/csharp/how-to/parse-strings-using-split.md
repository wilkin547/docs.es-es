---
title: Procedimiento para analizar cadenas mediante String.Split (Guía de C#)
description: String.Split devuelve una matriz de cadenas dividida entre un conjunto de delimitadores. Es una manera sencilla de analizar cadenas.
ms.date: 01/03/2018
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
ms.custom: mvc
ms.openlocfilehash: cf8307517213b54041b272843232eb595660b2e9
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389505"
---
# <a name="how-to-parse-strings-using-stringsplit-in-c"></a><span data-ttu-id="3f538-104">Procedimiento para analizar cadenas mediante String.Split en C\#</span><span class="sxs-lookup"><span data-stu-id="3f538-104">How to parse strings using String.Split in C\#</span></span>

<span data-ttu-id="3f538-105">El método <xref:System.String.Split%2A?displayProperty=nameWithType> crea una matriz de subcadenas mediante la división de la cadena de entrada en función de uno o varios delimitadores.</span><span class="sxs-lookup"><span data-stu-id="3f538-105">The <xref:System.String.Split%2A?displayProperty=nameWithType> method creates an array of substrings by splitting the input string based on one or more delimiters.</span></span> <span data-ttu-id="3f538-106">Suele ser la manera más fácil de separar una cadena en límites de palabras.</span><span class="sxs-lookup"><span data-stu-id="3f538-106">It is often the easiest way to separate a string on word boundaries.</span></span> <span data-ttu-id="3f538-107">También sirve para dividir las cadenas en otras cadenas o caracteres específicos.</span><span class="sxs-lookup"><span data-stu-id="3f538-107">It is also used to split strings on other specific characters or strings.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="3f538-108">Este código divide una frase común en una matriz de cadenas para cada palabra.</span><span class="sxs-lookup"><span data-stu-id="3f538-108">The following code splits a common phrase into an array of strings for each word.</span></span>

[!code-csharp-interactive[split strings on word boundaries](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#1)]

<span data-ttu-id="3f538-109">Todas las instancias de un carácter separador generan un valor en la matriz devuelta.</span><span class="sxs-lookup"><span data-stu-id="3f538-109">Every instance of a separator character produces a value in the returned array.</span></span> <span data-ttu-id="3f538-110">Los caracteres separadores consecutivos generan la cadena vacía como un valor en la matriz devuelta.</span><span class="sxs-lookup"><span data-stu-id="3f538-110">Consecutive separator characters produce the empty string as a value in the returned array.</span></span> <span data-ttu-id="3f538-111">Puede ver cómo se crea una cadena vacía en el ejemplo siguiente, en el que se usa el carácter de espacio como separador.</span><span class="sxs-lookup"><span data-stu-id="3f538-111">You can see how an empty string is created in the following example, which uses the space character as a separator.</span></span>

[!code-csharp-interactive[split strings with repeated separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#2)]

<span data-ttu-id="3f538-112">Este comportamiento facilita formatos como los de los archivos de valores separados por comas (CSV) que representan datos tabulares.</span><span class="sxs-lookup"><span data-stu-id="3f538-112">This behavior makes it easier for formats like comma-separated values (CSV) files representing tabular data.</span></span> <span data-ttu-id="3f538-113">Las comas consecutivas representan una columna en blanco.</span><span class="sxs-lookup"><span data-stu-id="3f538-113">Consecutive commas represent a blank column.</span></span>

<span data-ttu-id="3f538-114">Puede pasar un parámetro <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> opcional para excluir cualquier cadena vacía en la matriz devuelta.</span><span class="sxs-lookup"><span data-stu-id="3f538-114">You can pass an optional <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> parameter to exclude any empty strings in the returned array.</span></span> <span data-ttu-id="3f538-115">Para un procesamiento más complicado de la colección devuelta, puede usar [LINQ](../programming-guide/concepts/linq/index.md) para manipular la secuencia de resultados.</span><span class="sxs-lookup"><span data-stu-id="3f538-115">For more complicated processing of the returned collection, you can use [LINQ](../programming-guide/concepts/linq/index.md) to manipulate the result sequence.</span></span>

<span data-ttu-id="3f538-116"><xref:System.String.Split%2A?displayProperty=nameWithType> puede usar varios caracteres separadores.</span><span class="sxs-lookup"><span data-stu-id="3f538-116"><xref:System.String.Split%2A?displayProperty=nameWithType> can use multiple separator characters.</span></span>
<span data-ttu-id="3f538-117">En este ejemplo se usan espacios, comas, puntos, dos puntos y tabulaciones; están incluidos todos en una matriz que contiene estos caracteres de separación y que se pasa a <xref:System.String.Split%2A>.</span><span class="sxs-lookup"><span data-stu-id="3f538-117">The following example uses spaces, commas, periods, colons, and tabs, all passed in an array containing these separating characters, to <xref:System.String.Split%2A>.</span></span>
<span data-ttu-id="3f538-118">En el bucle al final del código se muestra cada una de las palabras de la matriz devuelta.</span><span class="sxs-lookup"><span data-stu-id="3f538-118">The loop at the bottom of the code displays each of the words in the returned array.</span></span>  

[!code-csharp-interactive[split strings using multiple separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#3)]

<span data-ttu-id="3f538-119">Las instancias consecutivas de cualquier separador generan la cadena vacía en la matriz de salida:</span><span class="sxs-lookup"><span data-stu-id="3f538-119">Consecutive instances of any separator produce the empty string in the output array:</span></span>

[!code-csharp-interactive[split strings using multiple consecutive separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#4)]

<span data-ttu-id="3f538-120"><xref:System.String.Split%2A?displayProperty=nameWithType> puede tomar una matriz de cadenas (secuencias de caracteres que actúan como separadores para analizar la cadena de destino, en lugar de caracteres individuales).</span><span class="sxs-lookup"><span data-stu-id="3f538-120"><xref:System.String.Split%2A?displayProperty=nameWithType> can take an array of strings (character sequences that act as separators for parsing the target string, instead of single characters).</span></span>  
  
[!code-csharp-interactive[split strings using strings as separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#5)]

<span data-ttu-id="3f538-121">Eche un vistazo al código de nuestro [repositorio de GitHub](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings) y pruebe estos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="3f538-121">You can try these samples by looking at the code in our [GitHub repository](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings).</span></span> <span data-ttu-id="3f538-122">O bien, puede descargar los ejemplos [como un archivo ZIP](../../../samples/snippets/csharp/how-to/strings.zip).</span><span class="sxs-lookup"><span data-stu-id="3f538-122">Or you can download the samples [as a zip file](../../../samples/snippets/csharp/how-to/strings.zip).</span></span>

## <a name="see-also"></a><span data-ttu-id="3f538-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f538-123">See also</span></span>

- [<span data-ttu-id="3f538-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3f538-124">C# Programming Guide</span></span>](../programming-guide/index.md)
- [<span data-ttu-id="3f538-125">Cadenas</span><span class="sxs-lookup"><span data-stu-id="3f538-125">Strings</span></span>](../programming-guide/strings/index.md)
- [<span data-ttu-id="3f538-126">Expresiones regulares de .NET</span><span class="sxs-lookup"><span data-stu-id="3f538-126">.NET Regular Expressions</span></span>](../../standard/base-types/regular-expressions.md)
