---
title: Procedimiento para consultar LINQ to XML mediante XPath (C#)
ms.date: 07/20/2015
ms.assetid: ee5af263-4ab1-45e5-b792-33a3221b426d
ms.openlocfilehash: a3e9cb29b9ba027cfc70eeb0cd163b24834dff83
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564112"
---
# <a name="how-to-query-linq-to-xml-using-xpath-c"></a><span data-ttu-id="220d3-102">Procedimiento para consultar LINQ to XML mediante XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="220d3-102">How to: Query LINQ to XML Using XPath (C#)</span></span>
<span data-ttu-id="220d3-103">Este tema presenta los métodos de extensión que permiten consultar un árbol XML con XPath.</span><span class="sxs-lookup"><span data-stu-id="220d3-103">This topic introduces the extension methods that enable you to query an XML tree by using XPath.</span></span> <span data-ttu-id="220d3-104">Para obtener información detallada acerca del uso de estos métodos de extensión, vea <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="220d3-104">For detailed information about using these extension methods, see <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="220d3-105">A menos que tenga un motivo muy específico para realizar consultas con XPath, como en el caso del uso intensivo de código heredado, no se recomienda usar XPath con LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="220d3-105">Unless you have a very specific reason for querying using XPath, such as extensive use of legacy code, using XPath with LINQ to XML is not recommended.</span></span> <span data-ttu-id="220d3-106">Las consultas XPath no se realizarán tan bien como las consultas [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="220d3-106">XPath queries will not perform as well as [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="220d3-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="220d3-107">Example</span></span>  
 <span data-ttu-id="220d3-108">En el ejemplo siguiente se crea un árbol XML pequeño y se utiliza <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> para seleccionar un conjunto de elementos.</span><span class="sxs-lookup"><span data-stu-id="220d3-108">The following example creates a small XML tree and uses <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> to select a set of elements.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", 1),  
    new XElement("Child1", 2),  
    new XElement("Child1", 3),  
    new XElement("Child2", 4),  
    new XElement("Child2", 5),  
    new XElement("Child2", 6)  
);  
IEnumerable<XElement> list = root.XPathSelectElements("./Child2");  
foreach (XElement el in list)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="220d3-109">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="220d3-109">This example produces the following output:</span></span>  
  
```xml  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  
## <a name="see-also"></a><span data-ttu-id="220d3-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="220d3-110">See also</span></span>

- [<span data-ttu-id="220d3-111">Técnicas de consulta avanzadas (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="220d3-111">Advanced Query Techniques (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
