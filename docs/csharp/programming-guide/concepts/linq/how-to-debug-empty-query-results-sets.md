---
title: Procedimiento para depurar conjuntos de resultados de consulta vacíos (C#)
ms.date: 07/20/2015
ms.assetid: b569f0dc-425e-45a6-acbf-770fb761c981
ms.openlocfilehash: 2716f7c525ac6bee8d2fb374e4ecc4c975d852a0
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141294"
---
# <a name="how-to-debug-empty-query-results-sets-c"></a><span data-ttu-id="ccf7d-102">Procedimiento para depurar conjuntos de resultados de consulta vacíos (C#)</span><span class="sxs-lookup"><span data-stu-id="ccf7d-102">How to debug empty query results sets (C#)</span></span>
<span data-ttu-id="ccf7d-103">Uno de los problemas más habituales al consultar árboles XML es que si el árbol XML tiene un espacio de nombres predeterminado, el desarrollador a veces escribe la consulta como si el código XML no estuviera en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="ccf7d-103">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="ccf7d-104">El primer conjunto de ejemplos de este tema muestra una forma habitual de cargar XML en un espacio de nombres predeterminado con una consulta incorrecta.</span><span class="sxs-lookup"><span data-stu-id="ccf7d-104">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, and is queried improperly.</span></span>  
  
 <span data-ttu-id="ccf7d-105">El segundo conjunto de ejemplos muestra las correcciones necesarias para que pueda consultar el código XML en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="ccf7d-105">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
 <span data-ttu-id="ccf7d-106">Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="ccf7d-106">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ccf7d-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ccf7d-107">Example</span></span>  
 <span data-ttu-id="ccf7d-108">Este ejemplo muestra la creación de XML en un espacio de nombres, y una consulta que devuelve un conjunto de resultados vacío.</span><span class="sxs-lookup"><span data-stu-id="ccf7d-108">This example shows creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements("Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
 <span data-ttu-id="ccf7d-109">Este ejemplo genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="ccf7d-109">This example produces the following result:</span></span>  
  
```output  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="ccf7d-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ccf7d-110">Example</span></span>  
 <span data-ttu-id="ccf7d-111">Este ejemplo muestra la creación de XML en un espacio de nombres, y una consulta que se codifica correctamente.</span><span class="sxs-lookup"><span data-stu-id="ccf7d-111">This example shows creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="ccf7d-112">La solución consiste en declarar e inicializar un objeto <xref:System.Xml.Linq.XNamespace>, y usarlo cuando se especifiquen objetos <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="ccf7d-112">The solution is to declare and initialize an <xref:System.Xml.Linq.XNamespace> object, and to use it when specifying <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="ccf7d-113">En este caso, el argumento para el método <xref:System.Xml.Linq.XContainer.Elements%2A> es un objeto <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="ccf7d-113">In this case, the argument to the <xref:System.Xml.Linq.XContainer.Elements%2A> method is an <xref:System.Xml.Linq.XName> object.</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
 <span data-ttu-id="ccf7d-114">Este ejemplo genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="ccf7d-114">This example produces the following result:</span></span>  
  
```output  
Result set follows:  
1  
2  
3  
End of result set  
```  
