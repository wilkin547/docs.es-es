---
title: LINQ y cadenas (C#)
description: LINQ puede consultar y transformar cadenas y colecciones de cadenas. Las consultas LINQ se pueden combinar con funciones de cadena de C# y expresiones regulares.
ms.date: 07/20/2015
ms.assetid: dbe2d657-b3f3-487e-b645-21fb2d71cd7b
ms.openlocfilehash: 0500d821335659fa29dd4809513f38dac0a8b193
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556725"
---
# <a name="linq-and-strings-c"></a><span data-ttu-id="7645b-104">LINQ y cadenas (C#)</span><span class="sxs-lookup"><span data-stu-id="7645b-104">LINQ and strings (C#)</span></span>

<span data-ttu-id="7645b-105">Se puede usar LINQ para consultar y transformar cadenas y colecciones de cadenas.</span><span class="sxs-lookup"><span data-stu-id="7645b-105">LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="7645b-106">Puede resultar especialmente útil con datos semiestructurados de archivos de texto.</span><span class="sxs-lookup"><span data-stu-id="7645b-106">It can be especially useful with semi-structured data in text files.</span></span> <span data-ttu-id="7645b-107">Las consultas LINQ se pueden combinar con funciones de cadena tradicionales y expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="7645b-107">LINQ queries can be combined with traditional string functions and regular expressions.</span></span> <span data-ttu-id="7645b-108">Por ejemplo, puede usar el método <xref:System.String.Split%2A?displayProperty=nameWithType> o <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> para crear una matriz de cadenas que después puede consultar o modificar mediante LINQ.</span><span class="sxs-lookup"><span data-stu-id="7645b-108">For example, you can use the <xref:System.String.Split%2A?displayProperty=nameWithType> or <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method to create an array of strings that you can then query or modify by using LINQ.</span></span> <span data-ttu-id="7645b-109">Puede usar el método <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> en la cláusula `where` de una consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="7645b-109">You can use the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> method in the `where` clause of a LINQ query.</span></span> <span data-ttu-id="7645b-110">Y puede usar LINQ para consultar o modificar los resultados <xref:System.Text.RegularExpressions.MatchCollection> que se han devuelto mediante una expresión regular.</span><span class="sxs-lookup"><span data-stu-id="7645b-110">And you can use LINQ to query or modify the <xref:System.Text.RegularExpressions.MatchCollection> results returned by a regular expression.</span></span>

<span data-ttu-id="7645b-111">También puede usar las técnicas descritas en esta sección para transformar datos de texto semiestructurados en XML.</span><span class="sxs-lookup"><span data-stu-id="7645b-111">You can also use the techniques described in this section to transform semi-structured text data to XML.</span></span> <span data-ttu-id="7645b-112">Para más información, consulte [Procedimiento para generar XML a partir de archivos CSV (C#)](../../../../standard/linq/generate-xml-csv-files.md).</span><span class="sxs-lookup"><span data-stu-id="7645b-112">For more information, see [How to generate XML from CSV files](../../../../standard/linq/generate-xml-csv-files.md).</span></span>

<span data-ttu-id="7645b-113">Los ejemplos de esta sección se dividen en dos categorías:</span><span class="sxs-lookup"><span data-stu-id="7645b-113">The examples in this section fall into two categories:</span></span>

## <a name="querying-a-block-of-text"></a><span data-ttu-id="7645b-114">Consulta de un bloque de texto</span><span class="sxs-lookup"><span data-stu-id="7645b-114">Querying a block of text</span></span>

<span data-ttu-id="7645b-115">Puede consultar, analizar y modificar bloques de texto dividiéndolos en una matriz consultable de cadenas más pequeñas mediante el método <xref:System.String.Split%2A?displayProperty=nameWithType> o el método <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7645b-115">You can query, analyze, and modify text blocks by splitting them into a queryable array of smaller strings by using the <xref:System.String.Split%2A?displayProperty=nameWithType> method or the <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7645b-116">Puede dividir el texto de origen en palabras, frases, párrafos, páginas o cualquier otro criterio y luego realizar divisiones adicionales si son necesarias en la consulta.</span><span class="sxs-lookup"><span data-stu-id="7645b-116">You can split the source text into words, sentences, paragraphs, pages, or any other criteria, and then perform additional splits if they are required in your query.</span></span>

- [<span data-ttu-id="7645b-117">Procedimiento para realizar un recuento de las repeticiones de una palabra en una cadena (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7645b-117">How to count occurrences of a word in a string (LINQ) (C#)</span></span>](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
  <span data-ttu-id="7645b-118">Muestra cómo usar LINQ para consultas simples en texto.</span><span class="sxs-lookup"><span data-stu-id="7645b-118">Shows how to use LINQ for simple querying over text.</span></span>

- [<span data-ttu-id="7645b-119">Procedimiento para buscar frases que contengan un conjunto especificado de palabras (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7645b-119">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>](how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)

  <span data-ttu-id="7645b-120">Muestra cómo dividir archivos de texto en límites arbitrarios y cómo realizar consultas en cada parte.</span><span class="sxs-lookup"><span data-stu-id="7645b-120">Shows how to split text files on arbitrary boundaries and how to perform queries against each part.</span></span>

- [<span data-ttu-id="7645b-121">Procedimiento para buscar caracteres en una cadena (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7645b-121">How to query for characters in a string (LINQ) (C#)</span></span>](how-to-query-for-characters-in-a-string-linq.md)

  <span data-ttu-id="7645b-122">Muestra que una cadena es un tipo que se puede consultar.</span><span class="sxs-lookup"><span data-stu-id="7645b-122">Demonstrates that a string is a queryable type.</span></span>

- [<span data-ttu-id="7645b-123">Procedimiento para combinar consultas LINQ con expresiones regulares (C#)</span><span class="sxs-lookup"><span data-stu-id="7645b-123">How to combine LINQ queries with regular expressions (C#)</span></span>](how-to-combine-linq-queries-with-regular-expressions.md)

  <span data-ttu-id="7645b-124">Muestra cómo usar expresiones regulares en consultas LINQ para la coincidencia de patrones compleja en resultados de consulta filtrados.</span><span class="sxs-lookup"><span data-stu-id="7645b-124">Shows how to use regular expressions in LINQ queries for complex pattern matching on filtered query results.</span></span>

## <a name="querying-semi-structured-data-in-text-format"></a><span data-ttu-id="7645b-125">Consulta de datos semiestructurados en formato de texto</span><span class="sxs-lookup"><span data-stu-id="7645b-125">Querying semi-structured data in text format</span></span>

<span data-ttu-id="7645b-126">Muchos tipos diferentes de archivos de texto se componen de una serie de líneas, a menudo con un formato similar, como archivos delimitados por comas o líneas de longitud fija.</span><span class="sxs-lookup"><span data-stu-id="7645b-126">Many different types of text files consist of a series of lines, often with similar formatting, such as tab- or comma-delimited files or fixed-length lines.</span></span> <span data-ttu-id="7645b-127">Después de leer uno de estos archivos de texto en la memoria, puede usar LINQ para consultar o modificar las líneas.</span><span class="sxs-lookup"><span data-stu-id="7645b-127">After you read such a text file into memory, you can use LINQ to query and/or modify the lines.</span></span> <span data-ttu-id="7645b-128">Las consultas LINQ también simplifican la tarea de combinar datos de varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="7645b-128">LINQ queries also simplify the task of combining data from multiple sources.</span></span>

- [<span data-ttu-id="7645b-129">Procedimiento para buscar la diferencia de conjuntos entre dos listas (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7645b-129">How to find the set difference between two lists (LINQ) (C#)</span></span>](how-to-find-the-set-difference-between-two-lists-linq.md)

  <span data-ttu-id="7645b-130">Muestra cómo encontrar todas las cadenas que se encuentran en una lista pero no en la otra.</span><span class="sxs-lookup"><span data-stu-id="7645b-130">Shows how to find all the strings that are present in one list but not the other.</span></span>

- [<span data-ttu-id="7645b-131">Procedimiento para ordenar o filtrar datos de texto por palabra o campo (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7645b-131">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)

  <span data-ttu-id="7645b-132">Muestra cómo ordenar líneas de texto según cualquier palabra o campo.</span><span class="sxs-lookup"><span data-stu-id="7645b-132">Shows how to sort text lines based on any word or field.</span></span>

- [<span data-ttu-id="7645b-133">Procedimiento para reordenar los campos de un archivo delimitado (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7645b-133">How to reorder the fields of a delimited file (LINQ) (C#)</span></span>](how-to-reorder-the-fields-of-a-delimited-file-linq.md)

  <span data-ttu-id="7645b-134">Muestra cómo cambiar el orden de los campos en una línea en un archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="7645b-134">Shows how to reorder fields in a line in a .csv file.</span></span>

- [<span data-ttu-id="7645b-135">Procedimiento para combinar y comparar colecciones de cadenas (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7645b-135">How to combine and compare string collections (LINQ) (C#)</span></span>](how-to-combine-and-compare-string-collections-linq.md)

  <span data-ttu-id="7645b-136">Muestra cómo combinar listas de cadenas de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="7645b-136">Shows how to combine string lists in various ways.</span></span>

- [<span data-ttu-id="7645b-137">Procedimiento para rellenar colecciones de objetos de varios orígenes (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7645b-137">How to populate object collections from multiple sources (LINQ) (C#)</span></span>](how-to-populate-object-collections-from-multiple-sources-linq.md)

  <span data-ttu-id="7645b-138">Muestra cómo crear colecciones de objetos mediante varios archivos de texto como orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="7645b-138">Shows how to create object collections by using multiple text files as data sources.</span></span>

- [<span data-ttu-id="7645b-139">Procedimiento para combinar contenido de archivos no similares (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7645b-139">How to join content from dissimilar files (LINQ) (C#)</span></span>](how-to-join-content-from-dissimilar-files-linq.md)
  
  <span data-ttu-id="7645b-140">Muestra cómo combinar cadenas de dos listas en una sola mediante una clave coincidente.</span><span class="sxs-lookup"><span data-stu-id="7645b-140">Shows how to combine strings in two lists into a single string by using a matching key.</span></span>

- [<span data-ttu-id="7645b-141">Procedimiento para dividir un archivo en muchos mediante grupos (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7645b-141">How to split a file into many files by using groups (LINQ) (C#)</span></span>](how-to-split-a-file-into-many-files-by-using-groups-linq.md)
  
  <span data-ttu-id="7645b-142">Muestra cómo crear nuevos archivos mediante un solo archivo como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7645b-142">Shows how to create new files by using a single file as a data source.</span></span>

- [<span data-ttu-id="7645b-143">Procedimiento para calcular valores de columna en un archivo de texto CSV (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7645b-143">How to compute column values in a CSV text file (LINQ) (C#)</span></span>](how-to-compute-column-values-in-a-csv-text-file-linq.md)
  
  <span data-ttu-id="7645b-144">Muestra cómo realizar cálculos matemáticos en datos de texto en archivos .csv.</span><span class="sxs-lookup"><span data-stu-id="7645b-144">Shows how to perform mathematical computations on text data in .csv files.</span></span>

## <a name="see-also"></a><span data-ttu-id="7645b-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="7645b-145">See also</span></span>

- [<span data-ttu-id="7645b-146">Language Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7645b-146">Language-Integrated Query (LINQ) (C#)</span></span>](index.md)
- [<span data-ttu-id="7645b-147">Procedimiento para generar XML a partir de archivos CSV</span><span class="sxs-lookup"><span data-stu-id="7645b-147">How to generate XML from CSV files</span></span>](../../../../standard/linq/generate-xml-csv-files.md)
