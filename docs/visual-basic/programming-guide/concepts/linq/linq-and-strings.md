---
title: LINQ y cadenas (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 75ddb201-d97a-4f98-8cdf-4ad51714529a
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a79d1427331070da9c545fdd3175115fe187e879
ms.lasthandoff: 03/13/2017

---
# <a name="linq-and-strings-visual-basic"></a>LINQ y cadenas (Visual Basic)
LINQ permite consultar y transformar cadenas y colecciones de cadenas. Puede ser especialmente útil con datos semiestructurados en archivos de texto. Las consultas LINQ se pueden combinar con funciones de cadena tradicional y expresiones regulares. Por ejemplo, puede usar el <xref:System.String.Split%2A>o <xref:System.Text.RegularExpressions.Regex.Split%2A>método para crear una matriz de cadenas que se pueden consultar o modificar mediante LINQ.</xref:System.Text.RegularExpressions.Regex.Split%2A> </xref:System.String.Split%2A> Puede usar el <xref:System.Text.RegularExpressions.Regex.IsMatch%2A>método en el `where` cláusula de una consulta LINQ.</xref:System.Text.RegularExpressions.Regex.IsMatch%2A> Y puede utilizar LINQ para consultar o modificar el <xref:System.Text.RegularExpressions.MatchCollection>resultados devueltos por una expresión regular.</xref:System.Text.RegularExpressions.MatchCollection>  
  
 También puede utilizar las técnicas descritas en esta sección para transformar datos de texto semiestructurados en XML. Para obtener más información, consulte [Cómo: generar XML desde archivos CSV](how-to-generate-xml-from-csv-files.md).  
  
 Los ejemplos de esta sección se dividen en dos categorías:  
  
## <a name="querying-a-block-of-text"></a>Consultar un bloque de texto  
 Puede consultar, analizar y modificar bloques de texto dividiéndolos en una matriz de cadenas más pequeñas mediante el uso de la <xref:System.String.Split%2A>método o <xref:System.Text.RegularExpressions.Regex.Split%2A>método.</xref:System.Text.RegularExpressions.Regex.Split%2A> </xref:System.String.Split%2A> Puede dividir el texto de origen en palabras, frases, párrafos, páginas o cualquier otro criterio y, a continuación, realizar las divisiones adicionales si son necesarios en la consulta.  
  
 [Cómo: contar las apariciones de una palabra en una cadena (LINQ) (Visual Basic)](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
 Muestra cómo usar LINQ para consultar simple sobre el texto.  
  
 [Cómo: buscar frases que contengan un conjunto especificado de palabras (LINQ) (Visual Basic)](how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)

 Muestra cómo dividir los archivos de texto según límites arbitrarios y cómo realizar consultas en cada parte.  
  
 [Cómo: buscar caracteres en una cadena (LINQ) (Visual Basic)](how-to-query-for-characters-in-a-string-linq.md)  
 Muestra que una cadena es un tipo consultable.  
  
 [Cómo: combinar consultas LINQ con expresiones regulares (Visual Basic)](how-to-combine-linq-queries-with-regular-expressions.md)  
 Muestra cómo utilizar expresiones regulares en consultas LINQ para complejas de coincidencia en los resultados de la consulta filtrada.  
  
## <a name="querying-semi-structured-data-in-text-format"></a>Consultar datos semiestructurados en formato de texto  
 Muchos tipos diferentes de archivos de texto se componen de una serie de líneas, a menudo con un formato similar, como delimitado por comas o archivos o líneas de longitud fija. Después de leer este archivo de texto en la memoria, puede usar LINQ para consultar o modificar las líneas. Las consultas LINQ también simplifican la tarea de combinar datos de varios orígenes.  
  
 [Cómo: buscar la diferencia de conjuntos entre dos listas (LINQ) (Visual Basic)](how-to-find-the-set-difference-between-two-lists-linq.md)  
 Muestra cómo encontrar todas las cadenas que se encuentran en una lista, pero no el otro.  
  
 [Cómo: ordenar o filtrar los datos de texto por palabra o campo (LINQ) (Visual Basic)](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)  
 Muestra cómo ordenar las líneas de texto en cualquier palabra o campo.  
  
 [Cómo: reordenar los campos de un archivo delimitado (LINQ) (Visual Basic)](how-to-reorder-the-fields-of-a-delimited-file.md)  
 Muestra cómo cambiar el orden de los campos de una línea en un archivo .csv.  
  
 [Cómo: combinar y comparar colecciones de cadenas (LINQ) (Visual Basic)](how-to-combine-and-compare-string-collections-linq.md)  
 Muestra cómo combinar listas de cadenas de varias maneras.  
  
 [Cómo: rellenar colecciones de objetos de varios orígenes (LINQ) (Visual Basic)](how-to-populate-object-collections-from-multiple-sources-linq.md)  
 Muestra cómo crear colecciones de objetos mediante el uso de varios archivos de texto como orígenes de datos.  
  
 [Cómo: combinar contenido de archivos no similares (LINQ) (Visual Basic)](how-to-join-content-from-dissimilar-files-linq.md)  
 Muestra cómo combinar cadenas de dos listas en una sola cadena utilizando una clave coincidente.  
  
 [Cómo: dividir un archivo en varios archivos mediante el uso de grupos (LINQ) (Visual Basic)](how-to-split-a-file-into-many-files-by-using-groups-linq.md)  
 Muestra cómo crear nuevos archivos mediante el uso de un solo archivo como origen de datos.  
  
 [Cómo: calcular valores de columna en un archivo de texto CSV (LINQ) (Visual Basic)](how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 Muestra cómo realizar cálculos matemáticos en datos de texto en archivos .csv.  
  
## <a name="see-also"></a>Vea también  
 [Language-Integrated Query (LINQ) (Visual Basic)](index.md)   
 [Generar XML a partir de archivos CSV](how-to-generate-xml-from-csv-files.md)

