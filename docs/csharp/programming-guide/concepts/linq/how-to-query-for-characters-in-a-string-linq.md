---
title: Procedimiento para buscar caracteres en una cadena (LINQ) (C#)
description: En LINQ puede consultar una cadena como una secuencia de caracteres. En este ejemplo de C# se consulta una cadena para determinar el número de dígitos numéricos que contiene.
ms.date: 07/20/2015
ms.assetid: 727a1be7-dbec-4ab8-b414-bc2d56feb6ff
ms.openlocfilehash: 3512be7c30843fcd8e881eab59761706a84a3ac8
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104554"
---
# <a name="how-to-query-for-characters-in-a-string-linq-c"></a><span data-ttu-id="32d88-104">Procedimiento para buscar caracteres en una cadena (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="32d88-104">How to query for characters in a string (LINQ) (C#)</span></span>
<span data-ttu-id="32d88-105">Como la clase <xref:System.String> implementa la interfaz <xref:System.Collections.Generic.IEnumerable%601> genérica, cualquier cadena puede consultarse como una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="32d88-105">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="32d88-106">Pero esto no es un uso habitual de LINQ.</span><span class="sxs-lookup"><span data-stu-id="32d88-106">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="32d88-107">Para operaciones de coincidencia de patrones complejas, use la clase <xref:System.Text.RegularExpressions.Regex>.</span><span class="sxs-lookup"><span data-stu-id="32d88-107">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32d88-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="32d88-108">Example</span></span>  
 <span data-ttu-id="32d88-109">En el ejemplo siguiente se consulta una cadena para determinar el número de dígitos numéricos que contiene.</span><span class="sxs-lookup"><span data-stu-id="32d88-109">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="32d88-110">Tenga en cuenta que la consulta se "reutiliza" después de que se ejecute la primera vez.</span><span class="sxs-lookup"><span data-stu-id="32d88-110">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="32d88-111">Esto es posible porque la propia consulta no almacena ningún resultado real.</span><span class="sxs-lookup"><span data-stu-id="32d88-111">This is possible because the query itself does not store any actual results.</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="32d88-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="32d88-112">Compiling the Code</span></span>  
 <span data-ttu-id="32d88-113">Cree un proyecto de aplicación de consola de C# con directivas `using` para los espacios de nombres System.Linq y System.IO.</span><span class="sxs-lookup"><span data-stu-id="32d88-113">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32d88-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="32d88-114">See also</span></span>

- [<span data-ttu-id="32d88-115">LINQ y cadenas (C#)</span><span class="sxs-lookup"><span data-stu-id="32d88-115">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="32d88-116">Procedimiento para combinar consultas LINQ con expresiones regulares (C#)</span><span class="sxs-lookup"><span data-stu-id="32d88-116">How to combine LINQ queries with regular expressions (C#)</span></span>](./how-to-combine-linq-queries-with-regular-expressions.md)
