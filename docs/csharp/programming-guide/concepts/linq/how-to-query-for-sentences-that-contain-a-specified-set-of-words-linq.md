---
title: Procedimiento para buscar frases que contengan un conjunto especificado de palabras (LINQ) (C#)
description: Aprenda a usar LINQ en C# para buscar frases de un archivo de texto que contengan coincidencias con cada una de las palabras de un conjunto, que podría rellenarse en tiempo de ejecución.
ms.date: 07/20/2015
ms.assetid: 0724b429-4b87-4d26-a7b1-409358f3fc20
ms.openlocfilehash: c334c7948f19fb857709ff04a83e1dae56fc69da
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104532"
---
# <a name="how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq-c"></a>Procedimiento para buscar frases que contengan un conjunto especificado de palabras (LINQ) (C#)
En este ejemplo se muestra cómo buscar frases en un archivo de texto que contengan coincidencias con cada uno de los conjuntos de palabras especificados. Aunque la matriz de términos de búsqueda está codificada de forma rígida en este ejemplo, también se podría rellenar dinámicamente en tiempo de ejecución. En este ejemplo, la consulta devuelve las frases que contienen las palabras "Historically", "data" e "integrated".  
  
## <a name="example"></a>Ejemplo  
  
```csharp  
class FindSentences  
{  
    static void Main()  
    {  
        string text = @"Historically, the world of data and the world of objects " +  
        @"have not been well integrated. Programmers work in C# or Visual Basic " +  
        @"and also in SQL or XQuery. On the one side are concepts such as classes, " +  
        @"objects, fields, inheritance, and .NET Framework APIs. On the other side " +  
        @"are tables, columns, rows, nodes, and separate languages for dealing with " +  
        @"them. Data types often require translation between the two worlds; there are " +  
        @"different standard functions. Because the object world has no notion of query, a " +  
        @"query can only be represented as a string without compile-time type checking or " +  
        @"IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to " +  
        @"objects in memory is often tedious and error-prone.";  
  
        // Split the text block into an array of sentences.  
        string[] sentences = text.Split(new char[] { '.', '?', '!' });  
  
        // Define the search terms. This list could also be dynamically populated at runtime.  
        string[] wordsToMatch = { "Historically", "data", "integrated" };  
  
        // Find sentences that contain all the terms in the wordsToMatch array.  
        // Note that the number of terms to match is not specified at compile time.  
        var sentenceQuery = from sentence in sentences  
                            let w = sentence.Split(new char[] { '.', '?', '!', ' ', ';', ':', ',' },  
                                                    StringSplitOptions.RemoveEmptyEntries)  
                            where w.Distinct().Intersect(wordsToMatch).Count() == wordsToMatch.Count()  
                            select sentence;  
  
        // Execute the query. Note that you can explicitly type  
        // the iteration variable here even though sentenceQuery  
        // was implicitly typed.
        foreach (string str in sentenceQuery)  
        {  
            Console.WriteLine(str);  
        }  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
Historically, the world of data and the world of objects have not been well integrated  
*/  
```  
  
 La consulta primero divide el texto en frases y, luego, divide las frases en una matriz de cadenas que contienen cada palabra. Para cada una de estas matrices, el método <xref:System.Linq.Enumerable.Distinct%2A> quita todas las palabras duplicadas y, después, la consulta realiza una operación <xref:System.Linq.Enumerable.Intersect%2A> en la matriz de palabras y en la matriz `wordsToMatch`. Si el recuento de la intersección es igual que el recuento de la matriz `wordsToMatch`, se han encontrado todas las palabras y se devuelve la frase original.  
  
 En la llamada a <xref:System.String.Split%2A>, los signos de puntuación se usan como separadores para quitar las frases de la cadena. Si no lo hiciera podría tener, por ejemplo, una cadena "Historically", lo que no coincidiría con el "Historically" de la matriz `wordsToMatch`. Podría tener que usar separadores adicionales, en función de los tipos de puntuación del texto de origen.  
  
## <a name="compiling-the-code"></a>Compilar el código  
Cree un proyecto de aplicación de consola de C# con directivas `using` para los espacios de nombres System.Linq y System.IO.

## <a name="see-also"></a>Consulte también

- [LINQ y cadenas (C#)](./linq-and-strings.md)
