---
title: Procedimiento Buscar elementos descendientes (XPath-LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: e7e2dc9e-bda9-420d-a5b1-4fabf1cca46b
ms.openlocfilehash: 09f12dca7b6278327394126ffb0950682d285f88
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833404"
---
# <a name="how-to-find-descendant-elements-xpath-linq-to-xml-visual-basic"></a>Procedimiento Buscar elementos descendientes (XPath-LINQ to XML) (Visual Basic)
En este tema se muestra cómo obtener los elementos descendientes con un nombre particular.  
  
 La expresión XPath es `//Name`.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo busca todos los descendientes con el nombre `Name`.  
  
 Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
```vb  
      Dim po As XDocument = XDocument.Load("PurchaseOrders.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = po...<Name>  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = po.XPathSelectElements("//Name")  
  
If (list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count()) Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
Results are identical  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
## <a name="see-also"></a>Vea también

- [LINQ to XML para usuarios de XPath (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
