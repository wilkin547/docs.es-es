---
title: 'Cómo: Buscar el nodo inmediatamente anterior del mismo nivel (XPath-LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: ec046283-9fe2-4440-b295-860bf700099d
ms.openlocfilehash: b2cb9efba0ef65a1b1ab1d7dadd54759f7d2a26b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344620"
---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="c8adc-102">Cómo: buscar el elemento del mismo nivel inmediatamente anterior (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8adc-102">How to: Find the Immediate Preceding Sibling (XPath-LINQ to XML) (Visual Basic)</span></span>

<span data-ttu-id="c8adc-103">Es posible que en alguna ocasión desee buscar el elemento del mismo nivel inmediatamente anterior a un nodo.</span><span class="sxs-lookup"><span data-stu-id="c8adc-103">Sometimes you want to find the immediate preceding sibling to a node.</span></span> <span data-ttu-id="c8adc-104">Debido a las diferencias de semántica de los predicados posicionales para los ejes de los elementos del mismo nivel anteriores de XPath en comparación con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], ésta es una de las comparaciones más interesantes.</span><span class="sxs-lookup"><span data-stu-id="c8adc-104">Due to the difference in the semantics of positional predicates for the preceding sibling axes in XPath as opposed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], this is one of the more interesting comparisons.</span></span>

## <a name="example"></a><span data-ttu-id="c8adc-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c8adc-105">Example</span></span>

<span data-ttu-id="c8adc-106">En este ejemplo, la consulta [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] usa el operador <xref:System.Linq.Enumerable.Last%2A> para buscar el último nodo de la recopilación devuelto por <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8adc-106">In this example, the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query uses the <xref:System.Linq.Enumerable.Last%2A> operator to find the last node in the collection returned by <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</span></span> <span data-ttu-id="c8adc-107">Por el contrario, la expresión XPath usa un predicado con un valor de 1 para buscar el elemento inmediatamente anterior.</span><span class="sxs-lookup"><span data-stu-id="c8adc-107">By contrast, the XPath expression uses a predicate with a value of 1 to find the immediately preceding element.</span></span>

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

<span data-ttu-id="c8adc-108">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="c8adc-108">This example produces the following output:</span></span>

```console
Results are identical
<Child3 />
```

## <a name="see-also"></a><span data-ttu-id="c8adc-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8adc-109">See also</span></span>

- [<span data-ttu-id="c8adc-110">LINQ to XML para los usuarios de XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8adc-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
