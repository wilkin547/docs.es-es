---
title: "Cómo: buscar el nodo inmediatamente anterior mismo nivel (XPath-LINQ to XML) (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec046283-9fe2-4440-b295-860bf700099d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6eb74dc4c106deadb92da1414e359d567fda6df
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="86535-102">Cómo: buscar el nodo inmediatamente anterior mismo nivel (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86535-102">How to: Find the Immediate Preceding Sibling (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="86535-103">Es posible que en alguna ocasión desee buscar el elemento del mismo nivel inmediatamente anterior a un nodo.</span><span class="sxs-lookup"><span data-stu-id="86535-103">Sometimes you want to find the immediate preceding sibling to a node.</span></span> <span data-ttu-id="86535-104">Debido a las diferencias de semántica de los predicados posicionales para los ejes de los elementos del mismo nivel anteriores de XPath en comparación con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], ésta es una de las comparaciones más interesantes.</span><span class="sxs-lookup"><span data-stu-id="86535-104">Due to the difference in the semantics of positional predicates for the preceding sibling axes in XPath as opposed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], this is one of the more interesting comparisons.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86535-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="86535-105">Example</span></span>  
 <span data-ttu-id="86535-106">En este ejemplo, la consulta [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] usa el operador <xref:System.Linq.Enumerable.Last%2A> para buscar el último nodo de la recopilación devuelto por <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</span><span class="sxs-lookup"><span data-stu-id="86535-106">In this example, the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query uses the <xref:System.Linq.Enumerable.Last%2A> operator to find the last node in the collection returned by <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</span></span> <span data-ttu-id="86535-107">Por el contrario, la expresión XPath usa un predicado con un valor de 1 para buscar el elemento inmediatamente anterior.</span><span class="sxs-lookup"><span data-stu-id="86535-107">By contrast, the XPath expression uses a predicate with a value of 1 to find the immediately preceding element.</span></span>  
  
```vb  
Dim root As XElement = _   
    <Root>  
        <Child1/>  
        <Child2/>  
        <Child3/>  
        <Child4/>  
    </Root>  
Dim child4 As XElement = root.Element("Child4")  
  
' LINQ to XML query  
Dim el1 As XElement = child4.ElementsBeforeSelf().Last()  
  
' XPath expression  
Dim el2 As XElement = _  
    DirectCast(child4.XPathEvaluate("preceding-sibling::*[1]"),  _  
    IEnumerable).Cast(Of XElement)().First()  
  
If el1 Is el2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(el1)  
```  
  
 <span data-ttu-id="86535-108">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="86535-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Child3 />  
```  
  
## <a name="see-also"></a><span data-ttu-id="86535-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="86535-109">See Also</span></span>  
 [<span data-ttu-id="86535-110">LINQ to XML para usuarios de XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86535-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
