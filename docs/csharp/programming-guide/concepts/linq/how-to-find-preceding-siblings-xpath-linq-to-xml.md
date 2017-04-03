---
title: Procedimiento para buscar elementos anteriores del mismo nivel (XPath-LINQ to XML) (C#) | Microsoft Docs
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: b281ff99-d08a-43d0-bea1-eff831b2f8ae
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 964a85548b7cf5fd7334c46f21e2d50a9ff17987
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-find-preceding-siblings-xpath-linq-to-xml-c"></a>Procedimiento para buscar elementos anteriores del mismo nivel (XPath-LINQ to XML) (C#)
En este tema se compara el eje `preceding-sibling` de XPath con el eje secundario <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName> de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
 La expresión XPath es:  
  
 `preceding-sibling::*`  
  
 Observe que los resultados de <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> y <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName> están en orden de documento.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo busca el elemento `FullAddress` y, a continuación, recupera los elementos anteriores utilizando el eje `preceding-sibling`.  
  
 En este ejemplo se usa el siguiente documento XML: [Archivo XML de muestra: clientes y pedidos (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).  
  
```csharp  
XElement co = XElement.Load("CustomersOrders.xml");  
  
XElement add = co.Element("Customers").Element("Customer").Element("FullAddress");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = add.ElementsBeforeSelf();  
  
// XPath expression  
IEnumerable<XElement> list2 = add.XPathSelectElements("preceding-sibling::*");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list2)  
    Console.WriteLine(el);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
Results are identical  
<CompanyName>Great Lakes Food Market</CompanyName>  
<ContactName>Howard Snyder</ContactName>  
<ContactTitle>Marketing Manager</ContactTitle>  
<Phone>(503) 555-7555</Phone>  
```  
  
## <a name="see-also"></a>Vea también  
 [LINQ to XML para usuarios de XPath (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
