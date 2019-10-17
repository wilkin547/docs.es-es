---
title: 'Cómo: recuperar una colección de elementos (LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 2269f9de-8fb9-4666-b8a1-a4e754fa6a81
ms.openlocfilehash: 2a5afea4fddda17ad78f45421821dcc13ad0e276
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72315928"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-visual-basic"></a>Cómo: recuperar una colección de elementos (LINQ to XML) (Visual Basic)
En este tema se demuestra el método <xref:System.Xml.Linq.XContainer.Elements%2A>. Este método recupera una colección de elementos secundarios de un elemento.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo recorre en iteración los elementos secundarios del elemento `purchaseOrder`.  
  
 En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim childElements As IEnumerable(Of XElement)  
childElements = _  
    From el In po.Elements() _  
    Select el  
For Each el As XElement In childElements  
    Console.WriteLine("Name: " & el.Name.ToString())  
Next  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```console  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a>Vea también

- [Ejes de LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
