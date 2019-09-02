---
title: Encadenar operadores de consulta estándar juntos (C#)
ms.date: 07/20/2015
ms.assetid: 66f2b0a9-2c23-4735-988e-bbc9dfb55c7b
ms.openlocfilehash: 37df654b2bfdcc135460e5ded2ceec1eca33b35a
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204211"
---
# <a name="chaining-standard-query-operators-together-c"></a><span data-ttu-id="9932e-102">Encadenar operadores de consulta estándar juntos (C#)</span><span class="sxs-lookup"><span data-stu-id="9932e-102">Chaining Standard Query Operators Together (C#)</span></span>
<span data-ttu-id="9932e-103">Este es el tema final de [Tutorial: Encadenar cadenas juntas (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9932e-103">This is the final topic in the [Tutorial: Chaining Queries Together (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md) tutorial.</span></span>  
  
 <span data-ttu-id="9932e-104">Los operadores de consulta estándar también se pueden encadenar juntos.</span><span class="sxs-lookup"><span data-stu-id="9932e-104">The standard query operators can also be chained together.</span></span> <span data-ttu-id="9932e-105">Por ejemplo, puede interponer el operador <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> y también funciona de forma diferida.</span><span class="sxs-lookup"><span data-stu-id="9932e-105">For example, you can interject the <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> operator, and it also operates in a lazy fashion.</span></span> <span data-ttu-id="9932e-106">No materializa resultados intermedios.</span><span class="sxs-lookup"><span data-stu-id="9932e-106">No intermediate results are materialized by it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9932e-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9932e-107">Example</span></span>  
 <span data-ttu-id="9932e-108">En este ejemplo, se llama al método <xref:System.Linq.Enumerable.Where%2A> antes de llamar a `ConvertCollectionToUpperCase`.</span><span class="sxs-lookup"><span data-stu-id="9932e-108">In this example, the <xref:System.Linq.Enumerable.Where%2A> method is called before calling `ConvertCollectionToUpperCase`.</span></span> <span data-ttu-id="9932e-109">El método <xref:System.Linq.Enumerable.Where%2A> funciona casi exactamente de la misma manera que los métodos diferidos utilizados en los ejemplos anteriores de este tutorial, `ConvertCollectionToUpperCase` y `AppendString`.</span><span class="sxs-lookup"><span data-stu-id="9932e-109">The <xref:System.Linq.Enumerable.Where%2A> method operates in almost exactly the same way as the lazy methods used in previous examples in this tutorial, `ConvertCollectionToUpperCase` and `AppendString`.</span></span>  
  
 <span data-ttu-id="9932e-110">Una diferencia es que en este caso, el método <xref:System.Linq.Enumerable.Where%2A> recorre en iteración su recopilación de origen, determina que el primer elemento no pasa el predicado y después obtiene el siguiente elemento, que lo pasa.</span><span class="sxs-lookup"><span data-stu-id="9932e-110">One difference is that in this case, the <xref:System.Linq.Enumerable.Where%2A> method iterates through its source collection, determines that the first item does not pass the predicate, and then gets the next item, which does pass.</span></span> <span data-ttu-id="9932e-111">A continuación produce el segundo elemento.</span><span class="sxs-lookup"><span data-stu-id="9932e-111">It then yields the second item.</span></span>  
  
 <span data-ttu-id="9932e-112">Pero la idea básica es la misma: las colecciones intermedias no se materializan a menos que deban hacerlo.</span><span class="sxs-lookup"><span data-stu-id="9932e-112">However, the basic idea is the same: Intermediate collections are not materialized unless they have to be.</span></span>  
  
 <span data-ttu-id="9932e-113">Cuando se utilizan expresiones de consulta, se convierten en llamadas a operadores de consulta estándar y se aplican los mismos principios.</span><span class="sxs-lookup"><span data-stu-id="9932e-113">When query expressions are used, they are converted to calls to the standard query operators, and the same principles apply.</span></span>  
  
 <span data-ttu-id="9932e-114">Todos los ejemplos de esta sección que consultan documentos XML abierto de Office utilizan el mismo principio.</span><span class="sxs-lookup"><span data-stu-id="9932e-114">All of the examples in this section that are querying Office Open XML documents use the same principle.</span></span> <span data-ttu-id="9932e-115">La ejecución aplazada y la evaluación diferida son algunos de los conceptos fundamentales que debe comprender para utilizar LINQ (y LINQ to XML) de forma efectiva.</span><span class="sxs-lookup"><span data-stu-id="9932e-115">Deferred execution and lazy evaluation are some of the fundamental concepts that you must understand  to use LINQ (and LINQ to XML) effectively.</span></span>  
  
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
            where s.CompareTo("D") >= 0  
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
  
 <span data-ttu-id="9932e-116">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="9932e-116">This example produces the following output:</span></span>  
  
```output  
ToUpper: source >abc<  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
