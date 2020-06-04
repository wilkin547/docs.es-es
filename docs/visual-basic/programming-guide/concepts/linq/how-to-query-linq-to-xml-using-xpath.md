---
title: Procedimiento para consultar LINQ to XML mediante XPath
ms.date: 07/20/2015
ms.assetid: e1f69a20-1efa-452d-9089-c472fa84b3d5
ms.openlocfilehash: d95e5a82d146c357f52d03375119474b042d49f6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397926"
---
# <a name="how-to-query-linq-to-xml-using-xpath-visual-basic"></a><span data-ttu-id="e0fb6-102">Cómo: consultar LINQ to XML mediante XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0fb6-102">How to: Query LINQ to XML Using XPath (Visual Basic)</span></span>
<span data-ttu-id="e0fb6-103">Este tema presenta los métodos de extensión que permiten consultar un árbol XML con XPath.</span><span class="sxs-lookup"><span data-stu-id="e0fb6-103">This topic introduces the extension methods that enable you to query an XML tree by using XPath.</span></span> <span data-ttu-id="e0fb6-104">Para obtener información detallada acerca del uso de estos métodos de extensión, vea <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e0fb6-104">For detailed information about using these extension methods, see <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="e0fb6-105">A menos que tenga un motivo muy específico para realizar consultas con XPath, como en el caso del uso intensivo de código heredado, no se recomienda usar XPath con LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="e0fb6-105">Unless you have a very specific reason for querying using XPath, such as extensive use of legacy code, using XPath with LINQ to XML is not recommended.</span></span> <span data-ttu-id="e0fb6-106">Las consultas XPath no se realizarán tan bien como las consultas [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0fb6-106">XPath queries will not perform as well as [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0fb6-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0fb6-107">Example</span></span>  
 <span data-ttu-id="e0fb6-108">En el ejemplo siguiente se crea un árbol XML pequeño y se utiliza <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> para seleccionar un conjunto de elementos.</span><span class="sxs-lookup"><span data-stu-id="e0fb6-108">The following example creates a small XML tree and uses <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> to select a set of elements.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>1</Child1>  
        <Child1>2</Child1>  
        <Child1>3</Child1>  
        <Child2>4</Child2>  
        <Child2>5</Child2>  
        <Child2>6</Child2>  
    </Root>  
  
Dim list As IEnumerable(Of XElement) = root.XPathSelectElements("./Child2")  
For Each el As XElement In list  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="e0fb6-109">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="e0fb6-109">This example produces the following output:</span></span>  
  
```xml  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e0fb6-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0fb6-110">See also</span></span>

- [<span data-ttu-id="e0fb6-111">Técnicas de consulta avanzadas (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0fb6-111">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](advanced-query-techniques-linq-to-xml.md)
