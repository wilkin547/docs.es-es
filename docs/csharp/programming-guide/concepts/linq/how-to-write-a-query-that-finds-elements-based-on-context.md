---
title: Procedimiento para escribir una consulta que busca elementos en función del contexto (C#)
description: Aprenda a escribir una consulta que busque elementos en función del contexto. Vea ejemplos de código y examine recursos adicionales.
ms.date: 07/20/2015
ms.assetid: 3ff79ef0-fc8b-42fe-8cc0-10dc32b06b4e
ms.openlocfilehash: 64f09a41c2c1d01b0be8f776461f9be9df9ecb5f
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303197"
---
# <a name="how-to-write-a-query-that-finds-elements-based-on-context-c"></a><span data-ttu-id="a7e59-104">Procedimiento para escribir una consulta que busca elementos en función del contexto (C#)</span><span class="sxs-lookup"><span data-stu-id="a7e59-104">How to write a query that finds elements based on context (C#)</span></span>
<span data-ttu-id="a7e59-105">Es posible que alguna vez tenga que escribir una consulta que seleccione elementos basándose en su contexto.</span><span class="sxs-lookup"><span data-stu-id="a7e59-105">Sometimes you might have to write a query that selects elements based on their context.</span></span> <span data-ttu-id="a7e59-106">Quizás desea filtrar basándose en elementos de mismo nivel precedentes o siguientes.</span><span class="sxs-lookup"><span data-stu-id="a7e59-106">You might want to filter based on preceding or following sibling elements.</span></span> <span data-ttu-id="a7e59-107">Quizás desea filtrar basándose e elementos secundarios o elementos antecesores.</span><span class="sxs-lookup"><span data-stu-id="a7e59-107">You might want to filter based on child or ancestor elements.</span></span>  
  
 <span data-ttu-id="a7e59-108">Puede hacerlo escribiendo una consulta y utilizando los resultados de la consulta en la cláusula `where`.</span><span class="sxs-lookup"><span data-stu-id="a7e59-108">You can do this by writing a query and using the results of the query in the `where` clause.</span></span> <span data-ttu-id="a7e59-109">Si primero tiene que realizar una prueba con valores NULL y después probar el valor, resulta más cómodo realizar la consulta en una cláusula `let` y después utilizar los resultados en la cláusula `where`.</span><span class="sxs-lookup"><span data-stu-id="a7e59-109">If you have to first test against null, and then test the value, it is more convenient to do the query in a `let` clause, and then use the results in the `where` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7e59-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7e59-110">Example</span></span>  
 <span data-ttu-id="a7e59-111">El siguiente ejemplo selecciona todos los elementos `p` que van seguidos inmediatamente por un elemento `ul`.</span><span class="sxs-lookup"><span data-stu-id="a7e59-111">The following example selects all `p` elements that are immediately followed by a `ul` element.</span></span>  
  
```csharp  
XElement doc = XElement.Parse(@"<Root>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants("p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name.LocalName == "ul"  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 <span data-ttu-id="a7e59-112">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="a7e59-112">This code produces the following output:</span></span>  
  
```output  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="example"></a><span data-ttu-id="a7e59-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7e59-113">Example</span></span>  
 <span data-ttu-id="a7e59-114">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="a7e59-114">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="a7e59-115">Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a7e59-115">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XElement doc = XElement.Parse(@"<Root xmlns='http://www.adatum.com'>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
XNamespace ad = "http://www.adatum.com";  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants(ad + "p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name == ad.GetName("ul")  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 <span data-ttu-id="a7e59-116">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="a7e59-116">This code produces the following output:</span></span>  
  
```output  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7e59-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a7e59-117">See also</span></span>

- <xref:System.Xml.Linq.XElement.Parse%2A>
- <xref:System.Xml.Linq.XContainer.Descendants%2A>
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>
- <xref:System.Linq.Enumerable.FirstOrDefault%2A>
