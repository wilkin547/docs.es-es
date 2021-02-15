---
description: 'Más información sobre: LINQ y cadenas (Visual Basic)'
title: LINQ y cadenas
ms.date: 07/20/2015
ms.assetid: 75ddb201-d97a-4f98-8cdf-4ad51714529a
ms.openlocfilehash: 16e1a2c3d8cee30643743400ad21dfc4ff15c14d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100469791"
---
# <a name="linq-and-strings-visual-basic"></a><span data-ttu-id="f99de-103">LINQ y cadenas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f99de-103">LINQ and Strings (Visual Basic)</span></span>

<span data-ttu-id="f99de-104">Se puede usar LINQ para consultar y transformar cadenas y colecciones de cadenas.</span><span class="sxs-lookup"><span data-stu-id="f99de-104">LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="f99de-105">Puede resultar especialmente útil con datos semiestructurados de archivos de texto.</span><span class="sxs-lookup"><span data-stu-id="f99de-105">It can be especially useful with semi-structured data in text files.</span></span> <span data-ttu-id="f99de-106">Las consultas LINQ se pueden combinar con funciones de cadena tradicionales y expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="f99de-106">LINQ queries can be combined with traditional string functions and regular expressions.</span></span> <span data-ttu-id="f99de-107">Por ejemplo, puede usar el método <xref:System.String.Split%2A> o <xref:System.Text.RegularExpressions.Regex.Split%2A> para crear una matriz de cadenas que después puede consultar o modificar mediante LINQ.</span><span class="sxs-lookup"><span data-stu-id="f99de-107">For example, you can use the <xref:System.String.Split%2A> or <xref:System.Text.RegularExpressions.Regex.Split%2A> method to create an array of strings that you can then query or modify by using LINQ.</span></span> <span data-ttu-id="f99de-108">Puede usar el método <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> en la cláusula `where` de una consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="f99de-108">You can use the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> method in the `where` clause of a LINQ query.</span></span> <span data-ttu-id="f99de-109">Y puede usar LINQ para consultar o modificar los resultados <xref:System.Text.RegularExpressions.MatchCollection> que se han devuelto mediante una expresión regular.</span><span class="sxs-lookup"><span data-stu-id="f99de-109">And you can use LINQ to query or modify the <xref:System.Text.RegularExpressions.MatchCollection> results returned by a regular expression.</span></span>  
  
 <span data-ttu-id="f99de-110">También puede usar las técnicas descritas en esta sección para transformar datos de texto semiestructurados en XML.</span><span class="sxs-lookup"><span data-stu-id="f99de-110">You can also use the techniques described in this section to transform semi-structured text data to XML.</span></span> <span data-ttu-id="f99de-111">Para obtener más información, vea [Cómo: generar XML a partir de archivos CSV](../../../../standard/linq/generate-xml-csv-files.md).</span><span class="sxs-lookup"><span data-stu-id="f99de-111">For more information, see [How to: Generate XML from CSV Files](../../../../standard/linq/generate-xml-csv-files.md).</span></span>  
  
 <span data-ttu-id="f99de-112">Los ejemplos de esta sección se dividen en dos categorías:</span><span class="sxs-lookup"><span data-stu-id="f99de-112">The examples in this section fall into two categories:</span></span>  
  
## <a name="querying-a-block-of-text"></a><span data-ttu-id="f99de-113">Consulta de un bloque de texto</span><span class="sxs-lookup"><span data-stu-id="f99de-113">Querying a Block of Text</span></span>  

 <span data-ttu-id="f99de-114">Puede consultar, analizar y modificar bloques de texto dividiéndolos en una matriz consultable de cadenas más pequeñas mediante el método <xref:System.String.Split%2A> o el método <xref:System.Text.RegularExpressions.Regex.Split%2A>.</span><span class="sxs-lookup"><span data-stu-id="f99de-114">You can query, analyze, and modify text blocks by splitting them into a queryable array of smaller strings by using the <xref:System.String.Split%2A> method or the <xref:System.Text.RegularExpressions.Regex.Split%2A> method.</span></span> <span data-ttu-id="f99de-115">Puede dividir el texto de origen en palabras, frases, párrafos, páginas o cualquier otro criterio y luego realizar divisiones adicionales si son necesarias en la consulta.</span><span class="sxs-lookup"><span data-stu-id="f99de-115">You can split the source text into words, sentences, paragraphs, pages, or any other criteria, and then perform additional splits if they are required in your query.</span></span>  
  
 [<span data-ttu-id="f99de-116">Cómo: contar las repeticiones de una palabra en una cadena (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f99de-116">How to: Count Occurrences of a Word in a String (LINQ) (Visual Basic)</span></span>](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
 <span data-ttu-id="f99de-117">Muestra cómo usar LINQ para consultas simples en texto.</span><span class="sxs-lookup"><span data-stu-id="f99de-117">Shows how to use LINQ for simple querying over text.</span></span>  
  
 [<span data-ttu-id="f99de-118">Cómo: Buscar frases que contengan un conjunto especificado de palabras (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f99de-118">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)

 <span data-ttu-id="f99de-119">Muestra cómo dividir archivos de texto en límites arbitrarios y cómo realizar consultas en cada parte.</span><span class="sxs-lookup"><span data-stu-id="f99de-119">Shows how to split text files on arbitrary boundaries and how to perform queries against each part.</span></span>  
  
 [<span data-ttu-id="f99de-120">Cómo: buscar caracteres en una cadena (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f99de-120">How to: Query for Characters in a String (LINQ) (Visual Basic)</span></span>](how-to-query-for-characters-in-a-string-linq.md)  
 <span data-ttu-id="f99de-121">Muestra que una cadena es un tipo que se puede consultar.</span><span class="sxs-lookup"><span data-stu-id="f99de-121">Demonstrates that a string is a queryable type.</span></span>  
  
 [<span data-ttu-id="f99de-122">Cómo combinar consultas LINQ con expresiones regulares (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f99de-122">How to combine LINQ queries with regular expressions (Visual Basic)</span></span>](how-to-combine-linq-queries-with-regular-expressions.md)  
 <span data-ttu-id="f99de-123">Muestra cómo usar expresiones regulares en consultas LINQ para la coincidencia de patrones compleja en resultados de consulta filtrados.</span><span class="sxs-lookup"><span data-stu-id="f99de-123">Shows how to use regular expressions in LINQ queries for complex pattern matching on filtered query results.</span></span>  
  
## <a name="querying-semi-structured-data-in-text-format"></a><span data-ttu-id="f99de-124">Consulta de datos semiestructurados en formato de texto</span><span class="sxs-lookup"><span data-stu-id="f99de-124">Querying Semi-Structured Data in Text Format</span></span>  

 <span data-ttu-id="f99de-125">Muchos tipos diferentes de archivos de texto se componen de una serie de líneas, a menudo con un formato similar, como archivos delimitados por comas o líneas de longitud fija.</span><span class="sxs-lookup"><span data-stu-id="f99de-125">Many different types of text files consist of a series of lines, often with similar formatting, such as tab- or comma-delimited files or fixed-length lines.</span></span> <span data-ttu-id="f99de-126">Después de leer uno de estos archivos de texto en la memoria, puede usar LINQ para consultar o modificar las líneas.</span><span class="sxs-lookup"><span data-stu-id="f99de-126">After you read such a text file into memory, you can use LINQ to query and/or modify the lines.</span></span> <span data-ttu-id="f99de-127">Las consultas LINQ también simplifican la tarea de combinar datos de varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="f99de-127">LINQ queries also simplify the task of combining data from multiple sources.</span></span>  
  
 [<span data-ttu-id="f99de-128">Cómo: buscar la diferencia de conjuntos entre dos listas (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f99de-128">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>](how-to-find-the-set-difference-between-two-lists-linq.md)  
 <span data-ttu-id="f99de-129">Muestra cómo encontrar todas las cadenas que se encuentran en una lista pero no en la otra.</span><span class="sxs-lookup"><span data-stu-id="f99de-129">Shows how to find all the strings that are present in one list but not the other.</span></span>  
  
 [<span data-ttu-id="f99de-130">Cómo ordenar o filtrar datos de texto por palabra o campo (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f99de-130">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)  
 <span data-ttu-id="f99de-131">Muestra cómo ordenar líneas de texto según cualquier palabra o campo.</span><span class="sxs-lookup"><span data-stu-id="f99de-131">Shows how to sort text lines based on any word or field.</span></span>  
  
 [<span data-ttu-id="f99de-132">Cómo: reordenar los campos de un archivo delimitado (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f99de-132">How to: Reorder the Fields of a Delimited File (LINQ) (Visual Basic)</span></span>](how-to-reorder-the-fields-of-a-delimited-file.md)  
 <span data-ttu-id="f99de-133">Muestra cómo cambiar el orden de los campos en una línea en un archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="f99de-133">Shows how to reorder fields in a line in a .csv file.</span></span>  
  
 [<span data-ttu-id="f99de-134">Cómo: combinar y comparar colecciones de cadenas (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f99de-134">How to: Combine and Compare String Collections (LINQ) (Visual Basic)</span></span>](how-to-combine-and-compare-string-collections-linq.md)  
 <span data-ttu-id="f99de-135">Muestra cómo combinar listas de cadenas de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="f99de-135">Shows how to combine string lists in various ways.</span></span>  
  
 [<span data-ttu-id="f99de-136">Cómo: rellenar colecciones de objetos de varios orígenes (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f99de-136">How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)</span></span>](how-to-populate-object-collections-from-multiple-sources-linq.md)  
 <span data-ttu-id="f99de-137">Muestra cómo crear colecciones de objetos mediante varios archivos de texto como orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="f99de-137">Shows how to create object collections by using multiple text files as data sources.</span></span>  
  
 [<span data-ttu-id="f99de-138">Cómo: combinar contenido de archivos no similares (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f99de-138">How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)</span></span>](how-to-join-content-from-dissimilar-files-linq.md)  
 <span data-ttu-id="f99de-139">Muestra cómo combinar cadenas de dos listas en una sola mediante una clave coincidente.</span><span class="sxs-lookup"><span data-stu-id="f99de-139">Shows how to combine strings in two lists into a single string by using a matching key.</span></span>  
  
 [<span data-ttu-id="f99de-140">Cómo: dividir un archivo en varios archivos mediante el uso de grupos (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f99de-140">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span></span>](how-to-split-a-file-into-many-files-by-using-groups-linq.md)  
 <span data-ttu-id="f99de-141">Muestra cómo crear nuevos archivos mediante un solo archivo como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f99de-141">Shows how to create new files by using a single file as a data source.</span></span>  
  
 [<span data-ttu-id="f99de-142">Cómo: calcular valores de columna en un archivo de texto CSV (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f99de-142">How to: Compute Column Values in a CSV Text File (LINQ) (Visual Basic)</span></span>](how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 <span data-ttu-id="f99de-143">Muestra cómo realizar cálculos matemáticos en datos de texto en archivos .csv.</span><span class="sxs-lookup"><span data-stu-id="f99de-143">Shows how to perform mathematical computations on text data in .csv files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f99de-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="f99de-144">See also</span></span>

- [<span data-ttu-id="f99de-145">Language-Integrated Query (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f99de-145">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="f99de-146">Cómo: generar XML a partir de archivos CSV</span><span class="sxs-lookup"><span data-stu-id="f99de-146">How to: Generate XML from CSV Files</span></span>](../../../../standard/linq/generate-xml-csv-files.md)
