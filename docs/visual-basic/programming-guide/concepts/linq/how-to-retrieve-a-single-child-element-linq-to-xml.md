---
title: "Cómo: recuperar un único elemento secundario (LINQ to XML) (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0033e258-d9c4-4569-86f6-79b7c06d1204
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 580315fda6ef6f1919f7f2aabc0cf3604a5c4337
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-visual-basic"></a>Cómo: recuperar un único elemento secundario (LINQ to XML) (Visual Basic)
En este tema se explica cómo recuperar un único elemento secundario, dado el nombre del elemento secundario. Si conoce el nombre del elemento secundario y que solo hay un elemento que tiene ese nombre, puede resultar cómodo recuperar solamente un elemento, en lugar de una recopilación.  
  
 El método <xref:System.Xml.Linq.XContainer.Element%2A> devuelve el primer <xref:System.Xml.Linq.XElement> secundario con el <xref:System.Xml.Linq.XName> especificado.  
  
 Si desea recuperar un único elemento secundario de Visual Basic, un enfoque común consiste en utilizar la propiedad XML y después recuperar el primer elemento mediante una notación de indizador de matriz.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra el uso del método <xref:System.Xml.Linq.XContainer.Element%2A>. Este ejemplo toma un árbol XML con el nombre `po` y busca el primer elemento con el nombre `Comment`.  
  
 El ejemplo de Visual Basic muestra el uso de la notación del indizador de matriz para recuperar un elemento único.  
  
 En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim e As XElement = po.<DeliveryNotes>(0)  
Console.WriteLine(e)  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo muestra el mismo código sobre un XML que se encuentra en un espacio de nombres. Para obtener más información, consulte [trabajar con espacios de nombres XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
 En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común en un espacio de nombres](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrderInNamespace.xml")  
        Dim e As XElement = po.<aw:DeliveryNotes>(0)  
        Console.WriteLine(e)  
    End Sub  
End Module  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a>Vea también  
 [Ejes de LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
