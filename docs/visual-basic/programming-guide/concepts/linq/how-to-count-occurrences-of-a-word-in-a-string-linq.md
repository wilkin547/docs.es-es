---
title: 'Cómo: Realizar un recuento de las repeticiones de una palabra en una cadena (LINQ)'
ms.date: 07/20/2015
ms.assetid: bc367e46-f7cc-45f9-936f-754e661b7bb9
ms.openlocfilehash: 07742e7e99291e056e4c91a31b2e588e36a6e177
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348185"
---
# <a name="how-to-count-occurrences-of-a-word-in-a-string-linq-visual-basic"></a>Cómo: contar las repeticiones de una palabra en una cadena (LINQ) (Visual Basic)

En este ejemplo se muestra cómo usar una consulta LINQ para contar las apariciones de una palabra determinada en una cadena. Observe que para realizar el recuento, primero se llama al método <xref:System.String.Split%2A> para crear una matriz de palabras. Existe un costo de rendimiento en el método <xref:System.String.Split%2A>. Si la única operación de la cadena es para contar las palabras, debe considerar la posibilidad de usar en su lugar los métodos <xref:System.Text.RegularExpressions.Regex.Matches%2A> o <xref:System.String.IndexOf%2A>. Pero si el rendimiento no es un problema crítico, o si ya ha dividido la frase para realizar otros tipos de consultas, tiene sentido usar LINQ para además contar las palabras o frases.

## <a name="example"></a>Ejemplo

```vb
Class CountWords

    Shared Sub Main()

        Dim text As String = "Historically, the world of data and the world of objects" &
                  " have not been well integrated. Programmers work in C# or Visual Basic" &
                  " and also in SQL or XQuery. On the one side are concepts such as classes," &
                  " objects, fields, inheritance, and .NET Framework APIs. On the other side" &
                  " are tables, columns, rows, nodes, and separate languages for dealing with" &
                  " them. Data types often require translation between the two worlds; there are" &
                  " different standard functions. Because the object world has no notion of query, a" &
                  " query can only be represented as a string without compile-time type checking or" &
                  " IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to" &
                  " objects in memory is often tedious and error-prone."

        Dim searchTerm As String = "data"

        ' Convert the string into an array of words.
        Dim dataSource As String() = text.Split(New Char() {" ", ",", ".", ";", ":"},
                                                 StringSplitOptions.RemoveEmptyEntries)

        ' Create and execute the query. It executes immediately
        ' because a singleton value is produced.
        ' Use ToLower to match "data" and "Data"
        Dim matchQuery = From word In dataSource
                      Where word.ToLowerInvariant() = searchTerm.ToLowerInvariant()
                      Select word

        ' Count the matches.
        Dim count As Integer = matchQuery.Count()
        Console.WriteLine(count & " occurrence(s) of the search term """ &
                          searchTerm & """ were found.")

        ' Keep console window open in debug mode.
        Console.WriteLine("Press any key to exit.")
        Console.ReadKey()
    End Sub
End Class
' Output:
' 3 occurrence(s) of the search term "data" were found.
```

## <a name="compile-the-code"></a>Compilar el código

Cree un proyecto de aplicación de consola de Visual Basic, con una instrucción de `Imports` para el espacio de nombres System. Linq.

## <a name="see-also"></a>Vea también

- [LINQ y cadenas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
