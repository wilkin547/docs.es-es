---
title: Procedimiento para consultar LINQ to XML mediante XPath (C#)
description: Puede usar métodos de extensión de C# para consultar un árbol XML mediante XPath. En general, no se recomienda usar XPath con LINQ to XML.
ms.date: 07/20/2015
ms.assetid: ee5af263-4ab1-45e5-b792-33a3221b426d
ms.openlocfilehash: fff45a93380b5af85aa640fc690783cc95e6298b
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104347"
---
# <a name="how-to-query-linq-to-xml-using-xpath-c"></a><span data-ttu-id="253d1-104">Procedimiento para consultar LINQ to XML mediante XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="253d1-104">How to query LINQ to XML using XPath (C#)</span></span>
<span data-ttu-id="253d1-105">Este tema presenta los métodos de extensión que permiten consultar un árbol XML con XPath.</span><span class="sxs-lookup"><span data-stu-id="253d1-105">This topic introduces the extension methods that enable you to query an XML tree by using XPath.</span></span> <span data-ttu-id="253d1-106">Para obtener información detallada acerca del uso de estos métodos de extensión, vea <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="253d1-106">For detailed information about using these extension methods, see <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="253d1-107">A menos que tenga un motivo muy específico para realizar consultas con XPath, como en el caso del uso intensivo de código heredado, no se recomienda usar XPath con LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="253d1-107">Unless you have a very specific reason for querying using XPath, such as extensive use of legacy code, using XPath with LINQ to XML is not recommended.</span></span> <span data-ttu-id="253d1-108">Las consultas XPath no se realizarán tan bien como las consultas [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="253d1-108">XPath queries will not perform as well as [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="253d1-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="253d1-109">Example</span></span>  
 <span data-ttu-id="253d1-110">En el ejemplo siguiente se crea un árbol XML pequeño y se utiliza <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> para seleccionar un conjunto de elementos.</span><span class="sxs-lookup"><span data-stu-id="253d1-110">The following example creates a small XML tree and uses <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> to select a set of elements.</span></span>  
  
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
  
 <span data-ttu-id="253d1-111">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="253d1-111">This example produces the following output:</span></span>  
  
```xml  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  