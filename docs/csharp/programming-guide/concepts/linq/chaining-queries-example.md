---
title: Ejemplo de encadenamiento de consultas (C#)
description: En este ejemplo se muestra qué sucede cuando se encadenan dos consultas que usan ejecución aplazada y evaluación diferida en C#.
ms.date: 07/20/2015
ms.assetid: abbca162-d95e-43af-b92c-e46e6aa2540e
ms.openlocfilehash: 0cfcfe1c8f537778fd1ef909277d95d83991af51
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105538"
---
# <a name="chaining-queries-example-c"></a><span data-ttu-id="a5767-103">Ejemplo de encadenamiento de consultas (C#)</span><span class="sxs-lookup"><span data-stu-id="a5767-103">Chaining Queries Example (C#)</span></span>
<span data-ttu-id="a5767-104">Este ejemplo se basa en el ejemplo anterior y muestra qué sucede cuando se encadenan dos consultas que usan ejecución aplazada y evaluación diferida.</span><span class="sxs-lookup"><span data-stu-id="a5767-104">This example builds on the previous example and shows what happens when you chain together two queries that both use deferred execution and lazy evaluation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5767-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5767-105">Example</span></span>  
 <span data-ttu-id="a5767-106">En este ejemplo se presenta otro método de extensión, `AppendString`, que anexa una cadena especificada a cada cadena de la recopilación de origen y después crea las nuevas cadenas.</span><span class="sxs-lookup"><span data-stu-id="a5767-106">In this example, another extension method is introduced, `AppendString`, which appends a specified string onto every string in the source collection, and then yields the new strings.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source >{0}<", str);  
            yield return str.ToUpper();  
        }  
    }  
  
    public static IEnumerable<string>  
      AppendString(this IEnumerable<string> source, string stringToAppend)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("AppendString: source >{0}<", str);  
            yield return str + stringToAppend;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        IEnumerable<string> q1 =  
            from s in stringArray.ConvertCollectionToUpperCase()  
            select s;  
  
        IEnumerable<string> q2 =  
            from s in q1.AppendString("!!!")  
            select s;  
  
        foreach (string str in q2)  
        {  
            Console.WriteLine("Main: str >{0}<", str);  
            Console.WriteLine();  
        }  
    }  
}  
```  
  
 <span data-ttu-id="a5767-107">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="a5767-107">This example produces the following output:</span></span>  
  
```output  
ToUpper: source >abc<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 <span data-ttu-id="a5767-108">En este ejemplo puede ver que cada método de extensión funciona de uno en uno para cada elemento de la recopilación de origen.</span><span class="sxs-lookup"><span data-stu-id="a5767-108">In this example, you can see that each extension method operates one at a time for each item in the source collection.</span></span>  
  
 <span data-ttu-id="a5767-109">Lo que debe quedar claro de este ejemplo es que aunque hemos encadenado juntas consultas que producen recopilaciones, no se han materializado recopilaciones intermedias.</span><span class="sxs-lookup"><span data-stu-id="a5767-109">What should be clear from this example is that even though we have chained together queries that yield collections, no intermediate collections are materialized.</span></span> <span data-ttu-id="a5767-110">En su lugar, cada elemento se pasa de un método diferido al siguiente.</span><span class="sxs-lookup"><span data-stu-id="a5767-110">Instead, each item is passed from one lazy method to the next.</span></span> <span data-ttu-id="a5767-111">Esto tiene como resultado una superficie de memoria mucho menor que el enfoque que primero tomaría una matriz de cadenas y después crearía una segunda matriz de cadenas que se han convertido a mayúsculas y finalmente crearía una tercera matriz de cadenas en la que cada cadena tiene puntos de exclamación anexados.</span><span class="sxs-lookup"><span data-stu-id="a5767-111">This results in a much smaller memory footprint than an approach that would first take one array of strings, then create a second array of strings that have been converted to uppercase, and finally create a third array of strings where each string has the exclamation points appended to it.</span></span>  
  
 <span data-ttu-id="a5767-112">El siguiente tema de este tutorial ilustra la materialización intermedia:</span><span class="sxs-lookup"><span data-stu-id="a5767-112">The next topic in this tutorial illustrates intermediate materialization:</span></span>  
  
- [<span data-ttu-id="a5767-113">Materialización intermedia (C#)</span><span class="sxs-lookup"><span data-stu-id="a5767-113">Intermediate Materialization (C#)</span></span>](./intermediate-materialization.md)  
  
## <a name="see-also"></a><span data-ttu-id="a5767-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a5767-114">See also</span></span>

- [<span data-ttu-id="a5767-115">Tutorial: Encadenar cadenas juntas (C#)</span><span class="sxs-lookup"><span data-stu-id="a5767-115">Tutorial: Chaining Queries Together (C#)</span></span>](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
