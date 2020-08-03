---
title: Ejemplo de ejecución diferida (C#)
description: Vea cómo la ejecución aplazada y la evaluación diferida afectan a la ejecución de las consultas de LINQ to XML en C#.
ms.date: 07/20/2015
ms.assetid: 50f4fbac-81fe-4f26-aedf-506e21419b19
ms.openlocfilehash: 65ba4cc150f2fc9d8f44aee352987ea0eeaab0a5
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103954"
---
# <a name="deferred-execution-example-c"></a><span data-ttu-id="039ab-103">Ejemplo de ejecución diferida (C#)</span><span class="sxs-lookup"><span data-stu-id="039ab-103">Deferred Execution Example (C#)</span></span>
<span data-ttu-id="039ab-104">En este tema se muestra cómo la ejecución aplazada y la evaluación diferid afectan a la ejecución de las consultas de LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="039ab-104">This topic shows how deferred execution and lazy evaluation affect the execution of your LINQ to XML queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="039ab-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="039ab-105">Example</span></span>  
 <span data-ttu-id="039ab-106">El siguiente ejemplo muestra el orden de ejecución cuando se usa un método de extensión que utiliza la ejecución aplazada.</span><span class="sxs-lookup"><span data-stu-id="039ab-106">The following example shows the order of execution when using an extension method that uses deferred execution.</span></span> <span data-ttu-id="039ab-107">El ejemplo declara una matriz de tres cadenas.</span><span class="sxs-lookup"><span data-stu-id="039ab-107">The example declares an array of three strings.</span></span> <span data-ttu-id="039ab-108">A continuación recorre en iteración la recopilación devuelta por `ConvertCollectionToUpperCase`.</span><span class="sxs-lookup"><span data-stu-id="039ab-108">It then iterates through the collection returned by `ConvertCollectionToUpperCase`.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source {0}", str);  
            yield return str.ToUpper();  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        var q = from str in stringArray.ConvertCollectionToUpperCase()  
                select str;  
  
        foreach (string str in q)  
            Console.WriteLine("Main: str {0}", str);  
    }  
}  
```  
  
 <span data-ttu-id="039ab-109">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="039ab-109">This example produces the following output:</span></span>  
  
```output  
ToUpper: source abc  
Main: str ABC  
ToUpper: source def  
Main: str DEF  
ToUpper: source ghi  
Main: str GHI  
```  
  
 <span data-ttu-id="039ab-110">Tenga en cuenta que durante el recorrido en iteración de la recopilación devuelta por `ConvertCollectionToUpperCase`, cada elemento se recupera de la matriz de cadenas de origen y se convierte a mayúsculas antes de que se recupere el siguiente elemento de la matriz de cadenas de origen.</span><span class="sxs-lookup"><span data-stu-id="039ab-110">Notice that when iterating through the collection returned by `ConvertCollectionToUpperCase`, each item is retrieved from the source string array and converted to uppercase before the next item is retrieved from the source string array.</span></span>  
  
 <span data-ttu-id="039ab-111">Puede ver que no se convierte a mayúsculas toda la matriz de cadenas antes de que se procese cada elemento en el bucle `foreach` de `Main`.</span><span class="sxs-lookup"><span data-stu-id="039ab-111">You can see that the entire array of strings is not converted to uppercase before each item in the returned collection is processed in the `foreach` loop in `Main`.</span></span>  
  
 <span data-ttu-id="039ab-112">En el siguiente tema de este tutorial se ilustra el encadenado de cadenas juntas:</span><span class="sxs-lookup"><span data-stu-id="039ab-112">The next topic in this tutorial illustrates chaining queries together:</span></span>  
  
- [<span data-ttu-id="039ab-113">Ejemplo de encadenamiento de consultas (C#)</span><span class="sxs-lookup"><span data-stu-id="039ab-113">Chaining Queries Example (C#)</span></span>](./chaining-queries-example.md)  
  
## <a name="see-also"></a><span data-ttu-id="039ab-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="039ab-114">See also</span></span>

- [<span data-ttu-id="039ab-115">Tutorial: Encadenar cadenas juntas (C#)</span><span class="sxs-lookup"><span data-stu-id="039ab-115">Tutorial: Chaining Queries Together (C#)</span></span>](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
