---
title: Procedimiento para buscar caracteres en una cadena (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: 727a1be7-dbec-4ab8-b414-bc2d56feb6ff
ms.openlocfilehash: d85e488a38a6167505732103b4c540cade6ea9bc
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345678"
---
# <a name="how-to-query-for-characters-in-a-string-linq-c"></a><span data-ttu-id="2630e-102">Procedimiento para buscar caracteres en una cadena (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="2630e-102">How to query for characters in a string (LINQ) (C#)</span></span>
<span data-ttu-id="2630e-103">Como la clase <xref:System.String> implementa la interfaz <xref:System.Collections.Generic.IEnumerable%601> genérica, cualquier cadena puede consultarse como una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2630e-103">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="2630e-104">Pero esto no es un uso habitual de LINQ.</span><span class="sxs-lookup"><span data-stu-id="2630e-104">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="2630e-105">Para operaciones de coincidencia de patrones complejas, use la clase <xref:System.Text.RegularExpressions.Regex>.</span><span class="sxs-lookup"><span data-stu-id="2630e-105">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2630e-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2630e-106">Example</span></span>  
 <span data-ttu-id="2630e-107">En el ejemplo siguiente se consulta una cadena para determinar el número de dígitos numéricos que contiene.</span><span class="sxs-lookup"><span data-stu-id="2630e-107">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="2630e-108">Tenga en cuenta que la consulta se "reutiliza" después de que se ejecute la primera vez.</span><span class="sxs-lookup"><span data-stu-id="2630e-108">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="2630e-109">Esto es posible porque la propia consulta no almacena ningún resultado real.</span><span class="sxs-lookup"><span data-stu-id="2630e-109">This is possible because the query itself does not store any actual results.</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="2630e-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="2630e-110">Compiling the Code</span></span>  
 <span data-ttu-id="2630e-111">Cree un proyecto de aplicación de consola de C# con directivas `using` para los espacios de nombres System.Linq y System.IO.</span><span class="sxs-lookup"><span data-stu-id="2630e-111">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2630e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="2630e-112">See also</span></span>

- [<span data-ttu-id="2630e-113">LINQ y cadenas (C#)</span><span class="sxs-lookup"><span data-stu-id="2630e-113">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="2630e-114">Procedimiento para combinar consultas LINQ con expresiones regulares (C#)</span><span class="sxs-lookup"><span data-stu-id="2630e-114">How to combine LINQ queries with regular expressions (C#)</span></span>](./how-to-combine-linq-queries-with-regular-expressions.md)
