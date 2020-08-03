---
title: Procedimiento para buscar el nodo del mismo nivel inmediatamente anterior (XPath-LINQ to XML) (C#)
description: En este ejemplo de C# se compara cómo XPath y LINQ to XML buscan el elemento relacionado que precede inmediatamente a un nodo.
ms.date: 07/20/2015
ms.assetid: 74c06201-0b1b-4b5e-b3ac-0092980614e6
ms.openlocfilehash: eaee7f1205ce0d0b2a9c2c41d96ba532573a1384
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105207"
---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-c"></a><span data-ttu-id="6b485-103">Procedimiento para buscar el nodo del mismo nivel inmediatamente anterior (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="6b485-103">How to find the immediate preceding sibling (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="6b485-104">Es posible que en alguna ocasión desee buscar el elemento del mismo nivel inmediatamente anterior a un nodo.</span><span class="sxs-lookup"><span data-stu-id="6b485-104">Sometimes you want to find the immediate preceding sibling to a node.</span></span> <span data-ttu-id="6b485-105">Debido a las diferencias de semántica de los predicados posicionales para los ejes de los elementos del mismo nivel anteriores de XPath en comparación con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], ésta es una de las comparaciones más interesantes.</span><span class="sxs-lookup"><span data-stu-id="6b485-105">Due to the difference in the semantics of positional predicates for the preceding sibling axes in XPath as opposed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], this is one of the more interesting comparisons.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b485-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b485-106">Example</span></span>  
 <span data-ttu-id="6b485-107">En este ejemplo, la consulta [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] usa el operador <xref:System.Linq.Enumerable.Last%2A> para buscar el último nodo de la recopilación devuelto por <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</span><span class="sxs-lookup"><span data-stu-id="6b485-107">In this example, the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query uses the <xref:System.Linq.Enumerable.Last%2A> operator to find the last node in the collection returned by <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</span></span> <span data-ttu-id="6b485-108">Por el contrario, la expresión XPath usa un predicado con un valor de 1 para buscar el elemento inmediatamente anterior.</span><span class="sxs-lookup"><span data-stu-id="6b485-108">By contrast, the XPath expression uses a predicate with a value of 1 to find the immediately preceding element.</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
    @"<Root>  
    <Child1/>  
    <Child2/>  
    <Child3/>  
    <Child4/>  
</Root>");  
XElement child4 = root.Element("Child4");  
  
// LINQ to XML query  
XElement el1 =  
    child4  
    .ElementsBeforeSelf()  
    .Last();  
  
// XPath expression  
XElement el2 =  
    ((IEnumerable)child4  
                 .XPathEvaluate("preceding-sibling::*[1]"))  
                 .Cast<XElement>()  
                 .First();  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1);  
```  
  
 <span data-ttu-id="6b485-109">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="6b485-109">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Child3 />  
```  
