---
title: "Cómo: buscar frases que contengan un conjunto especificado de palabras (LINQ) (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: a5ae8ced-61fe-4c10-bb8a-95630e50f603
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 31561d586c9c05f502002efdfc455acb55159fed
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq-visual-basic"></a>Cómo: Buscar frases que contengan un conjunto especificado de palabras (LINQ) (Visual Basic)
En este ejemplo se muestra cómo buscar las frases de un archivo de texto que contienen a coincidencias para cada uno de un conjunto especificado de palabras. Aunque la matriz de términos de búsqueda está codificado de forma rígida en este ejemplo, se podrían también rellenar dinámicamente en tiempo de ejecución. En este ejemplo, la consulta devuelve las frases que contienen las palabras "Históricamente", "datos" y "integrados".  
  
## <a name="example"></a>Ejemplo  
  
```vb  
Class FindSentences  
  
    Shared Sub Main()  
        Dim text As String = "Historically, the world of data and the world of objects " &   
        "have not been well integrated. Programmers work in C# or Visual Basic " &   
        "and also in SQL or XQuery. On the one side are concepts such as classes, " &   
        "objects, fields, inheritance, and .NET Framework APIs. On the other side " &   
        "are tables, columns, rows, nodes, and separate languages for dealing with " &   
        "them. Data types often require translation between the two worlds; there are " &   
        "different standard functions. Because the object world has no notion of query, a " &   
        "query can only be represented as a string without compile-time type checking or " &   
        "IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to " &   
        "objects in memory is often tedious and error-prone."  
  
        ' Split the text block into an array of sentences.  
        Dim sentences As String() = text.Split(New Char() {".", "?", "!"})  
  
        ' Define the search terms. This list could also be dynamically populated at runtime  
        Dim wordsToMatch As String() = {"Historically", "data", "integrated"}  
  
        ' Find sentences that contain all the terms in the wordsToMatch array  
        ' Note that the number of terms to match is not specified at compile time  
        Dim sentenceQuery = From sentence In sentences   
                            Let w = sentence.Split(New Char() {" ", ",", ".", ";", ":"},   
                                                   StringSplitOptions.RemoveEmptyEntries)   
                            Where w.Distinct().Intersect(wordsToMatch).Count = wordsToMatch.Count()   
                            Select sentence  
  
        ' Execute the query  
        For Each str As String In sentenceQuery  
            Console.WriteLine(str)  
        Next  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
  
End Class  
' Output:  
' Historically, the world of data and the world of objects have not been well integrated  
```  
  
 La consulta funciona primero divide el texto en frases y después divide las frases en una matriz de cadenas que contienen cada palabra. Para cada una de estas matrices, el <xref:System.Linq.Enumerable.Distinct%2A>método elimina todas las palabras duplicadas y, a continuación, la consulta realiza una <xref:System.Linq.Enumerable.Intersect%2A>operación en la matriz de palabras y el `wordsToMatch` matriz.</xref:System.Linq.Enumerable.Intersect%2A> </xref:System.Linq.Enumerable.Distinct%2A> Si el recuento de la intersección es igual que el recuento de los `wordsToMatch` matriz, se encontraron todas las palabras y se devuelve la frase original.  
  
 En la llamada a <xref:System.String.Split%2A>, los signos de puntuación se utilizan como separadores para quitarlos de la cadena.</xref:System.String.Split%2A> Si no, por ejemplo, podría tener una cadena "Históricamente", que no coincidiría con "Históricamente" en la `wordsToMatch` matriz. Tendrá que utilizar separadores adicionales, dependiendo de los tipos de puntuación en el texto de origen.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Crear un proyecto destinado a .NET Framework versión 3.5 o posterior con una referencia a System.Core.dll y una `Imports` instrucción del espacio de nombres System.Linq.  
  
## <a name="see-also"></a>Vea también  
 [LINQ y cadenas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
