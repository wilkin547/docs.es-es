---
title: Encadenar operadores de consulta estándar juntos (C#)
description: En este ejemplo se muestra cómo los operadores de consulta estándar también se pueden encadenar en C#. La consulta no materializa resultados intermedios.
ms.date: 07/20/2015
ms.assetid: 66f2b0a9-2c23-4735-988e-bbc9dfb55c7b
ms.openlocfilehash: 41a7e4c7910c783d07181fe16254b0cac6902794
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104066"
---
# <a name="chaining-standard-query-operators-together-c"></a><span data-ttu-id="f020e-104">Encadenar operadores de consulta estándar juntos (C#)</span><span class="sxs-lookup"><span data-stu-id="f020e-104">Chaining Standard Query Operators Together (C#)</span></span>
<span data-ttu-id="f020e-105">Este es el tema final de [Tutorial: Encadenar cadenas juntas (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f020e-105">This is the final topic in the [Tutorial: Chaining Queries Together (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md) tutorial.</span></span>  
  
 <span data-ttu-id="f020e-106">Los operadores de consulta estándar también se pueden encadenar juntos.</span><span class="sxs-lookup"><span data-stu-id="f020e-106">The standard query operators can also be chained together.</span></span> <span data-ttu-id="f020e-107">Por ejemplo, puede interponer el operador <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> y también funciona de forma diferida.</span><span class="sxs-lookup"><span data-stu-id="f020e-107">For example, you can interject the <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> operator, and it also operates in a lazy fashion.</span></span> <span data-ttu-id="f020e-108">No materializa resultados intermedios.</span><span class="sxs-lookup"><span data-stu-id="f020e-108">No intermediate results are materialized by it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f020e-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f020e-109">Example</span></span>  
 <span data-ttu-id="f020e-110">En este ejemplo, se llama al método <xref:System.Linq.Enumerable.Where%2A> antes de llamar a `ConvertCollectionToUpperCase`.</span><span class="sxs-lookup"><span data-stu-id="f020e-110">In this example, the <xref:System.Linq.Enumerable.Where%2A> method is called before calling `ConvertCollectionToUpperCase`.</span></span> <span data-ttu-id="f020e-111">El método <xref:System.Linq.Enumerable.Where%2A> funciona casi exactamente de la misma manera que los métodos diferidos utilizados en los ejemplos anteriores de este tutorial, `ConvertCollectionToUpperCase` y `AppendString`.</span><span class="sxs-lookup"><span data-stu-id="f020e-111">The <xref:System.Linq.Enumerable.Where%2A> method operates in almost exactly the same way as the lazy methods used in previous examples in this tutorial, `ConvertCollectionToUpperCase` and `AppendString`.</span></span>  
  
 <span data-ttu-id="f020e-112">Una diferencia es que en este caso, el método <xref:System.Linq.Enumerable.Where%2A> recorre en iteración su recopilación de origen, determina que el primer elemento no pasa el predicado y después obtiene el siguiente elemento, que lo pasa.</span><span class="sxs-lookup"><span data-stu-id="f020e-112">One difference is that in this case, the <xref:System.Linq.Enumerable.Where%2A> method iterates through its source collection, determines that the first item does not pass the predicate, and then gets the next item, which does pass.</span></span> <span data-ttu-id="f020e-113">A continuación produce el segundo elemento.</span><span class="sxs-lookup"><span data-stu-id="f020e-113">It then yields the second item.</span></span>  
  
 <span data-ttu-id="f020e-114">Pero la idea básica es la misma: las colecciones intermedias no se materializan a menos que deban hacerlo.</span><span class="sxs-lookup"><span data-stu-id="f020e-114">However, the basic idea is the same: Intermediate collections are not materialized unless they have to be.</span></span>  
  
 <span data-ttu-id="f020e-115">Cuando se utilizan expresiones de consulta, se convierten en llamadas a operadores de consulta estándar y se aplican los mismos principios.</span><span class="sxs-lookup"><span data-stu-id="f020e-115">When query expressions are used, they are converted to calls to the standard query operators, and the same principles apply.</span></span>  
  
 <span data-ttu-id="f020e-116">Todos los ejemplos de esta sección que consultan documentos XML abierto de Office utilizan el mismo principio.</span><span class="sxs-lookup"><span data-stu-id="f020e-116">All of the examples in this section that are querying Office Open XML documents use the same principle.</span></span> <span data-ttu-id="f020e-117">La ejecución aplazada y la evaluación diferida son algunos de los conceptos fundamentales que debe comprender para utilizar LINQ (y LINQ to XML) de forma efectiva.</span><span class="sxs-lookup"><span data-stu-id="f020e-117">Deferred execution and lazy evaluation are some of the fundamental concepts that you must understand  to use LINQ (and LINQ to XML) effectively.</span></span>  
  
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
  
 <span data-ttu-id="f020e-118">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="f020e-118">This example produces the following output:</span></span>  
  
```output  
ToUpper: source >abc<  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
