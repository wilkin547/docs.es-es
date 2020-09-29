---
title: Procedimiento para buscar caracteres en una cadena (LINQ) (C#)
description: En LINQ puede consultar una cadena como una secuencia de caracteres. En este ejemplo de C# se consulta una cadena para determinar el número de dígitos numéricos que contiene.
ms.date: 07/20/2015
ms.assetid: 727a1be7-dbec-4ab8-b414-bc2d56feb6ff
ms.openlocfilehash: 73288924d057e720a744b853998a52437b9db481
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153942"
---
# <a name="how-to-query-for-characters-in-a-string-linq-c"></a><span data-ttu-id="57c2b-104">Procedimiento para buscar caracteres en una cadena (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="57c2b-104">How to query for characters in a string (LINQ) (C#)</span></span>

<span data-ttu-id="57c2b-105">Como la clase <xref:System.String> implementa la interfaz <xref:System.Collections.Generic.IEnumerable%601> genérica, cualquier cadena puede consultarse como una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="57c2b-105">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="57c2b-106">Pero esto no es un uso habitual de LINQ.</span><span class="sxs-lookup"><span data-stu-id="57c2b-106">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="57c2b-107">Para operaciones de coincidencia de patrones complejas, use la clase <xref:System.Text.RegularExpressions.Regex>.</span><span class="sxs-lookup"><span data-stu-id="57c2b-107">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57c2b-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57c2b-108">Example</span></span>  

 <span data-ttu-id="57c2b-109">En el ejemplo siguiente se consulta una cadena para determinar el número de dígitos numéricos que contiene.</span><span class="sxs-lookup"><span data-stu-id="57c2b-109">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="57c2b-110">Tenga en cuenta que la consulta se "reutiliza" después de que se ejecute la primera vez.</span><span class="sxs-lookup"><span data-stu-id="57c2b-110">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="57c2b-111">Esto es posible porque la propia consulta no almacena ningún resultado real.</span><span class="sxs-lookup"><span data-stu-id="57c2b-111">This is possible because the query itself does not store any actual results.</span></span>  
  
```csharp  
class QueryAString  
{  
    static void Main()  
    {  
        string aString = "ABCDE99F-J74-12-89A";  
  
        // Select only those characters that are numbers  
        IEnumerable<char> stringQuery =  
          from ch in aString  
          where Char.IsDigit(ch)  
          select ch;  
  
        // Execute the query  
        foreach (char c in stringQuery)  
            Console.Write(c + " ");  
  
        // Call the Count method on the existing query.  
        int count = stringQuery.Count();  
        Console.WriteLine("Count = {0}", count);  
  
        // Select all characters before the first '-'  
        IEnumerable<char> stringQuery2 = aString.TakeWhile(c => c != '-');  
  
        // Execute the second query  
        foreach (char c in stringQuery2)  
            Console.Write(c);  
  
        Console.WriteLine(System.Environment.NewLine + "Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
  Output: 9 9 7 4 1 2 8 9  
  Count = 8  
  ABCDE99F  
*/  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="57c2b-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="57c2b-112">Compiling the Code</span></span>  

 <span data-ttu-id="57c2b-113">Cree un proyecto de aplicación de consola de C# con directivas `using` para los espacios de nombres System.Linq y System.IO.</span><span class="sxs-lookup"><span data-stu-id="57c2b-113">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57c2b-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57c2b-114">See also</span></span>

- [<span data-ttu-id="57c2b-115">LINQ y cadenas (C#)</span><span class="sxs-lookup"><span data-stu-id="57c2b-115">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="57c2b-116">Procedimiento para combinar consultas LINQ con expresiones regulares (C#)</span><span class="sxs-lookup"><span data-stu-id="57c2b-116">How to combine LINQ queries with regular expressions (C#)</span></span>](./how-to-combine-linq-queries-with-regular-expressions.md)
