---
title: LINQ y cadenas (C#)
ms.date: 07/20/2015
ms.assetid: dbe2d657-b3f3-487e-b645-21fb2d71cd7b
ms.openlocfilehash: a297aec0a33893c643be337c356e304cdcd375ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33328336"
---
# <a name="linq-and-strings-c"></a>LINQ y cadenas (C#)
Se puede usar LINQ para consultar y transformar cadenas y colecciones de cadenas. Puede resultar especialmente útil con datos semiestructurados de archivos de texto. Las consultas LINQ se pueden combinar con funciones de cadena tradicionales y expresiones regulares. Por ejemplo, puede usar el método <xref:System.String.Split%2A> o <xref:System.Text.RegularExpressions.Regex.Split%2A> para crear una matriz de cadenas que después puede consultar o modificar mediante LINQ. Puede usar el método <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> en la cláusula `where` de una consulta LINQ. Y puede usar LINQ para consultar o modificar los resultados <xref:System.Text.RegularExpressions.MatchCollection> que se han devuelto mediante una expresión regular.  
  
 También puede usar las técnicas descritas en esta sección para transformar datos de texto semiestructurados en XML. Para más información, vea [Cómo generar un XML a partir de archivos CSV](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd).  
  
 Los ejemplos de esta sección se dividen en dos categorías:  
  
## <a name="querying-a-block-of-text"></a>Consulta de un bloque de texto  
 Puede consultar, analizar y modificar bloques de texto dividiéndolos en una matriz consultable de cadenas más pequeñas mediante el método <xref:System.String.Split%2A> o el método <xref:System.Text.RegularExpressions.Regex.Split%2A>. Puede dividir el texto de origen en palabras, frases, párrafos, páginas o cualquier otro criterio y luego realizar divisiones adicionales si son necesarias en la consulta.  
  
 [Realizar un recuento de las repeticiones de una palabra en una cadena (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
 Muestra cómo usar LINQ para consultas simples en texto.  
  
 [Cómo: Buscar frases que contengan un conjunto especificado de palabras (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)  
 Muestra cómo dividir archivos de texto en límites arbitrarios y cómo realizar consultas en cada parte.  
  
 [Cómo: Buscar caracteres en una cadena (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-characters-in-a-string-linq.md)  
 Muestra que una cadena es un tipo que se puede consultar.  
  
 [Cómo: Combinar consultas LINQ con expresiones regulares (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)  
 Muestra cómo usar expresiones regulares en consultas LINQ para la coincidencia de patrones compleja en resultados de consulta filtrados.  
  
## <a name="querying-semi-structured-data-in-text-format"></a>Consulta de datos semiestructurados en formato de texto  
 Muchos tipos diferentes de archivos de texto se componen de una serie de líneas, a menudo con un formato similar, como archivos delimitados por comas o líneas de longitud fija. Después de leer uno de estos archivos de texto en la memoria, puede usar LINQ para consultar o modificar las líneas. Las consultas LINQ también simplifican la tarea de combinar datos de varios orígenes.  
  
 [Cómo: Buscar la diferencia de conjuntos entre dos listas (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)  
 Muestra cómo encontrar todas las cadenas que se encuentran en una lista pero no en la otra.  
  
 [Cómo ordenar o filtrar datos de texto por palabra o campo (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)  
 Muestra cómo ordenar líneas de texto según cualquier palabra o campo.  
  
 [Cómo: Reordenar los campos de un archivo delimitado (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-reorder-the-fields-of-a-delimited-file-linq.md)  
 Muestra cómo cambiar el orden de los campos en una línea en un archivo .csv.  
  
 [Cómo: Combinar y comparar colecciones de cadenas (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)  
 Muestra cómo combinar listas de cadenas de varias maneras.  
  
 [Cómo: Rellenar colecciones de objetos de varios orígenes (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)  
 Muestra cómo crear colecciones de objetos mediante varios archivos de texto como orígenes de datos.  
  
 [Cómo: Combinar contenido de archivos no similares (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)  
 Muestra cómo combinar cadenas de dos listas en una sola mediante una clave coincidente.  
  
 [Dividir un archivo en varios mediante el uso de grupos (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)  
 Muestra cómo crear nuevos archivos mediante un solo archivo como origen de datos.  
  
 [Cómo: Calcular valores de columna en un archivo de texto CSV (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 Muestra cómo realizar cálculos matemáticos en datos de texto en archivos .csv.  
  
## <a name="see-also"></a>Vea también  
 [Language-Integrated Query (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/index.md)  
 [Generar XML a partir de archivos CSV](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd)
