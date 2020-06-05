---
title: Procedimiento para buscar frases que contengan un conjunto especificado de palabras (LINQ)
ms.date: 07/20/2015
ms.assetid: a5ae8ced-61fe-4c10-bb8a-95630e50f603
ms.openlocfilehash: ce88bf001346f90eb9b08ca1ff14afc7dcb04fa0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397965"
---
# <a name="how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq-visual-basic"></a>Cómo: Buscar frases que contengan un conjunto especificado de palabras (LINQ) (Visual Basic)

En este ejemplo se muestra cómo buscar frases en un archivo de texto que contengan coincidencias con cada uno de los conjuntos de palabras especificados. Aunque la matriz de términos de búsqueda está codificada de forma rígida en este ejemplo, también se podría rellenar dinámicamente en tiempo de ejecución. En este ejemplo, la consulta devuelve las frases que contienen las palabras "Historically", "data" e "integrated".

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

La consulta primero divide el texto en frases y, luego, divide las frases en una matriz de cadenas que contienen cada palabra. Para cada una de estas matrices, el método <xref:System.Linq.Enumerable.Distinct%2A> quita todas las palabras duplicadas y, después, la consulta realiza una operación <xref:System.Linq.Enumerable.Intersect%2A> en la matriz de palabras y en la matriz `wordsToMatch`. Si el recuento de la intersección es igual que el recuento de la matriz `wordsToMatch`, se han encontrado todas las palabras y se devuelve la frase original.

En la llamada a <xref:System.String.Split%2A>, los signos de puntuación se usan como separadores para quitar las frases de la cadena. Si no lo hiciera podría tener, por ejemplo, una cadena "Historically", lo que no coincidiría con el "Historically" de la matriz `wordsToMatch`. Podría tener que usar separadores adicionales, en función de los tipos de puntuación del texto de origen.

## <a name="compile-the-code"></a>Compilar el código

Cree un proyecto de aplicación de consola de Visual Basic, con una `Imports` instrucción para el espacio de nombres System. Linq.

## <a name="see-also"></a>Consulte también

- [LINQ y cadenas (Visual Basic)](linq-and-strings.md)
