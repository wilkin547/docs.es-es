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
# <a name="linq-and-strings-c"></a>LINQ y cadenas (C#)

Se puede usar LINQ para consultar y transformar cadenas y colecciones de cadenas. Puede resultar especialmente útil con datos semiestructurados de archivos de texto. Las consultas LINQ se pueden combinar con funciones de cadena tradicionales y expresiones regulares. Por ejemplo, puede usar el método <xref:System.String.Split%2A?displayProperty=nameWithType> o <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> para crear una matriz de cadenas que después puede consultar o modificar mediante LINQ. Puede usar el método <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> en la cláusula `where` de una consulta LINQ. Y puede usar LINQ para consultar o modificar los resultados <xref:System.Text.RegularExpressions.MatchCollection> que se han devuelto mediante una expresión regular.

También puede usar las técnicas descritas en esta sección para transformar datos de texto semiestructurados en XML. Para más información, consulte [Procedimiento para generar XML a partir de archivos CSV (C#)](../../../../standard/linq/generate-xml-csv-files.md).

Los ejemplos de esta sección se dividen en dos categorías:

## <a name="querying-a-block-of-text"></a>Consulta de un bloque de texto

Puede consultar, analizar y modificar bloques de texto dividiéndolos en una matriz consultable de cadenas más pequeñas mediante el método <xref:System.String.Split%2A?displayProperty=nameWithType> o el método <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType>. Puede dividir el texto de origen en palabras, frases, párrafos, páginas o cualquier otro criterio y luego realizar divisiones adicionales si son necesarias en la consulta.

- [Procedimiento para realizar un recuento de las repeticiones de una palabra en una cadena (LINQ) (C#)](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
  Muestra cómo usar LINQ para consultas simples en texto.

- [Procedimiento para buscar frases que contengan un conjunto especificado de palabras (LINQ) (C#)](how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)

  Muestra cómo dividir archivos de texto en límites arbitrarios y cómo realizar consultas en cada parte.

- [Procedimiento para buscar caracteres en una cadena (LINQ) (C#)](how-to-query-for-characters-in-a-string-linq.md)

  Muestra que una cadena es un tipo que se puede consultar.

- [Procedimiento para combinar consultas LINQ con expresiones regulares (C#)](how-to-combine-linq-queries-with-regular-expressions.md)

  Muestra cómo usar expresiones regulares en consultas LINQ para la coincidencia de patrones compleja en resultados de consulta filtrados.

## <a name="querying-semi-structured-data-in-text-format"></a>Consulta de datos semiestructurados en formato de texto

Muchos tipos diferentes de archivos de texto se componen de una serie de líneas, a menudo con un formato similar, como archivos delimitados por comas o líneas de longitud fija. Después de leer uno de estos archivos de texto en la memoria, puede usar LINQ para consultar o modificar las líneas. Las consultas LINQ también simplifican la tarea de combinar datos de varios orígenes.

- [Procedimiento para buscar la diferencia de conjuntos entre dos listas (LINQ) (C#)](how-to-find-the-set-difference-between-two-lists-linq.md)

  Muestra cómo encontrar todas las cadenas que se encuentran en una lista pero no en la otra.

- [Procedimiento para ordenar o filtrar datos de texto por palabra o campo (LINQ) (C#)](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)

  Muestra cómo ordenar líneas de texto según cualquier palabra o campo.

- [Procedimiento para reordenar los campos de un archivo delimitado (LINQ) (C#)](how-to-reorder-the-fields-of-a-delimited-file-linq.md)

  Muestra cómo cambiar el orden de los campos en una línea en un archivo .csv.

- [Procedimiento para combinar y comparar colecciones de cadenas (LINQ) (C#)](how-to-combine-and-compare-string-collections-linq.md)

  Muestra cómo combinar listas de cadenas de varias maneras.

- [Procedimiento para rellenar colecciones de objetos de varios orígenes (LINQ) (C#)](how-to-populate-object-collections-from-multiple-sources-linq.md)

  Muestra cómo crear colecciones de objetos mediante varios archivos de texto como orígenes de datos.

- [Procedimiento para combinar contenido de archivos no similares (LINQ) (C#)](how-to-join-content-from-dissimilar-files-linq.md)
  
  Muestra cómo combinar cadenas de dos listas en una sola mediante una clave coincidente.

- [Procedimiento para dividir un archivo en muchos mediante grupos (LINQ) (C#)](how-to-split-a-file-into-many-files-by-using-groups-linq.md)
  
  Muestra cómo crear nuevos archivos mediante un solo archivo como origen de datos.

- [Procedimiento para calcular valores de columna en un archivo de texto CSV (LINQ) (C#)](how-to-compute-column-values-in-a-csv-text-file-linq.md)
  
  Muestra cómo realizar cálculos matemáticos en datos de texto en archivos .csv.

## <a name="see-also"></a>Vea también

- [Language Integrated Query (LINQ) (C#)](index.md)
- [Procedimiento para generar XML a partir de archivos CSV](../../../../standard/linq/generate-xml-csv-files.md)
