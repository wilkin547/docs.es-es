---
title: Procedimiento para buscar frases que contengan un conjunto especificado de palabras (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: 0724b429-4b87-4d26-a7b1-409358f3fc20
ms.openlocfilehash: efb0eb60a9695c19e16b507d29ef6994e904cff9
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347691"
---
# <a name="how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq-c"></a><span data-ttu-id="9f1db-102">Procedimiento para buscar frases que contengan un conjunto especificado de palabras (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="9f1db-102">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>
<span data-ttu-id="9f1db-103">En este ejemplo se muestra cómo buscar frases en un archivo de texto que contengan coincidencias con cada uno de los conjuntos de palabras especificados.</span><span class="sxs-lookup"><span data-stu-id="9f1db-103">This example shows how to find sentences in a text file that contain matches for each of a specified set of words.</span></span> <span data-ttu-id="9f1db-104">Aunque la matriz de términos de búsqueda está codificada de forma rígida en este ejemplo, también se podría rellenar dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9f1db-104">Although the array of search terms is hard-coded in this example, it could also be populated dynamically at runtime.</span></span> <span data-ttu-id="9f1db-105">En este ejemplo, la consulta devuelve las frases que contienen las palabras "Historically", "data" e "integrated".</span><span class="sxs-lookup"><span data-stu-id="9f1db-105">In this example, the query returns the sentences that contain the words "Historically," "data," and "integrated."</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f1db-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9f1db-106">Example</span></span>  
  
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
  
 <span data-ttu-id="9f1db-107">La consulta primero divide el texto en frases y, luego, divide las frases en una matriz de cadenas que contienen cada palabra.</span><span class="sxs-lookup"><span data-stu-id="9f1db-107">The query works by first splitting the text into sentences, and then splitting the sentences into an array of strings that hold each word.</span></span> <span data-ttu-id="9f1db-108">Para cada una de estas matrices, el método <xref:System.Linq.Enumerable.Distinct%2A> quita todas las palabras duplicadas y, después, la consulta realiza una operación <xref:System.Linq.Enumerable.Intersect%2A> en la matriz de palabras y en la matriz `wordsToMatch`.</span><span class="sxs-lookup"><span data-stu-id="9f1db-108">For each of these arrays, the <xref:System.Linq.Enumerable.Distinct%2A> method removes all duplicate words, and then the query performs an <xref:System.Linq.Enumerable.Intersect%2A> operation on the word array and the `wordsToMatch` array.</span></span> <span data-ttu-id="9f1db-109">Si el recuento de la intersección es igual que el recuento de la matriz `wordsToMatch`, se han encontrado todas las palabras y se devuelve la frase original.</span><span class="sxs-lookup"><span data-stu-id="9f1db-109">If the count of the intersection is the same as the count of the `wordsToMatch` array, all words were found in the words and the original sentence is returned.</span></span>  
  
 <span data-ttu-id="9f1db-110">En la llamada a <xref:System.String.Split%2A>, los signos de puntuación se usan como separadores para quitar las frases de la cadena.</span><span class="sxs-lookup"><span data-stu-id="9f1db-110">In the call to <xref:System.String.Split%2A>, the punctuation marks are used as separators in order to remove them from the string.</span></span> <span data-ttu-id="9f1db-111">Si no lo hiciera podría tener, por ejemplo, una cadena "Historically", lo que no coincidiría con el "Historically" de la matriz `wordsToMatch`.</span><span class="sxs-lookup"><span data-stu-id="9f1db-111">If you did not do this, for example you could have a string "Historically," that would not match "Historically" in the `wordsToMatch` array.</span></span> <span data-ttu-id="9f1db-112">Podría tener que usar separadores adicionales, en función de los tipos de puntuación del texto de origen.</span><span class="sxs-lookup"><span data-stu-id="9f1db-112">You may have to use additional separators, depending on the types of punctuation found in the source text.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9f1db-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9f1db-113">Compiling the Code</span></span>  
<span data-ttu-id="9f1db-114">Cree un proyecto de aplicación de consola de C# con directivas `using` para los espacios de nombres System.Linq y System.IO.</span><span class="sxs-lookup"><span data-stu-id="9f1db-114">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f1db-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f1db-115">See also</span></span>

- [<span data-ttu-id="9f1db-116">LINQ y cadenas (C#)</span><span class="sxs-lookup"><span data-stu-id="9f1db-116">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
