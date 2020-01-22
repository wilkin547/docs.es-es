---
title: Materialización intermedia (C#)
ms.date: 07/20/2015
ms.assetid: 7922d38f-5044-41cf-8e17-7173d6553a5e
ms.openlocfilehash: af1eb7df7da02d8e72fc102cda4ee5f329dc7974
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253164"
---
# <a name="intermediate-materialization-c"></a><span data-ttu-id="96fe6-102">Materialización intermedia (C#)</span><span class="sxs-lookup"><span data-stu-id="96fe6-102">Intermediate Materialization (C#)</span></span>
<span data-ttu-id="96fe6-103">Si no tiene cuidado, en algunas situaciones puede alterar drásticamente el perfil de memoria y rendimiento de su aplicación causando una materialización prematura de las recopilaciones de sus consultas.</span><span class="sxs-lookup"><span data-stu-id="96fe6-103">If you are not careful, in some situations you can drastically alter the memory and performance profile of your application by causing premature materialization of collections in your queries.</span></span> <span data-ttu-id="96fe6-104">Algunos operadores de consulta estándar provocan la materialización de su recopilación de origen antes de producir un elemento único.</span><span class="sxs-lookup"><span data-stu-id="96fe6-104">Some standard query operators cause materialization of their source collection before yielding a single element.</span></span> <span data-ttu-id="96fe6-105">Por ejemplo, <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> primero recorre en iteración toda la recopilación de origen, después ordena todos los elementos y finalmente produce el primer elemento.</span><span class="sxs-lookup"><span data-stu-id="96fe6-105">For example, <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> first iterates through its entire source collection, then sorts all items, and then finally yields the first item.</span></span> <span data-ttu-id="96fe6-106">Esto significa que resulta caro obtener el primer elemento de una recopilación ordenada; cada elemento posterior no es caro.</span><span class="sxs-lookup"><span data-stu-id="96fe6-106">This means that it is expensive to get the first item of an ordered collection; each item thereafter is not expensive.</span></span> <span data-ttu-id="96fe6-107">Esto tiene sentido: sería imposible que el operador de consulta hiciera lo contrario.</span><span class="sxs-lookup"><span data-stu-id="96fe6-107">This makes sense: It would be impossible for that query operator to do otherwise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96fe6-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="96fe6-108">Example</span></span>  
 <span data-ttu-id="96fe6-109">Este ejemplo altera el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="96fe6-109">This example alters the previous example.</span></span> <span data-ttu-id="96fe6-110">El método `AppendString` llama a <xref:System.Linq.Enumerable.ToList%2A> antes de recorrer en iteración el origen.</span><span class="sxs-lookup"><span data-stu-id="96fe6-110">The `AppendString` method calls <xref:System.Linq.Enumerable.ToList%2A> before iterating through the source.</span></span> <span data-ttu-id="96fe6-111">Esto provoca la materialización.</span><span class="sxs-lookup"><span data-stu-id="96fe6-111">This causes materialization.</span></span>  
  
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
        // the following statement materializes the source collection in a List<T>  
        // before iterating through it  
        foreach (string str in source.ToList())  
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
  
 <span data-ttu-id="96fe6-112">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="96fe6-112">This example produces the following output:</span></span>  
  
```output  
ToUpper: source >abc<  
ToUpper: source >def<  
ToUpper: source >ghi<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 <span data-ttu-id="96fe6-113">En este ejemplo puede ver que la llamada a <xref:System.Linq.Enumerable.ToList%2A> hace que `AppendString` enumere todo su origen antes de producir el primer elemento.</span><span class="sxs-lookup"><span data-stu-id="96fe6-113">In this example, you can see that the call to <xref:System.Linq.Enumerable.ToList%2A> causes `AppendString` to enumerate its entire source before yielding the first item.</span></span> <span data-ttu-id="96fe6-114">Si el origen fuera una matriz grande, alteraría significativamente el perfil de memoria de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="96fe6-114">If the source were a large array, this would significantly alter the memory profile of the application.</span></span>  
  
 <span data-ttu-id="96fe6-115">Los operadores de consulta estándar también se pueden encadenar juntos.</span><span class="sxs-lookup"><span data-stu-id="96fe6-115">Standard query operators can also be chained together.</span></span> <span data-ttu-id="96fe6-116">Esto se ilustra en el tema final de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="96fe6-116">The final topic in this tutorial illustrates this.</span></span>  
  
- [<span data-ttu-id="96fe6-117">Encadenar operadores de consulta estándar juntos (C#)</span><span class="sxs-lookup"><span data-stu-id="96fe6-117">Chaining Standard Query Operators Together (C#)</span></span>](./chaining-standard-query-operators-together.md)  
  
## <a name="see-also"></a><span data-ttu-id="96fe6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="96fe6-118">See also</span></span>

- [<span data-ttu-id="96fe6-119">Tutorial: Encadenar cadenas juntas (C#)</span><span class="sxs-lookup"><span data-stu-id="96fe6-119">Tutorial: Chaining Queries Together (C#)</span></span>](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
