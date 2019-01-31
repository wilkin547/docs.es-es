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
# <a name="how-to-query-linq-to-xml-using-xpath-c"></a>Procedimiento para consultar LINQ to XML mediante XPath (C#)
Este tema presenta los métodos de extensión que permiten consultar un árbol XML con XPath. Para obtener información detallada acerca del uso de estos métodos de extensión, vea <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.  
  
 A menos que tenga un motivo muy específico para realizar consultas con XPath, como en el caso del uso intensivo de código heredado, no se recomienda usar XPath con LINQ to XML. Las consultas XPath no se realizarán tan bien como las consultas [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un árbol XML pequeño y se utiliza <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> para seleccionar un conjunto de elementos.  
  
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
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  
## <a name="see-also"></a>Vea también

- [Técnicas de consulta avanzadas (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
