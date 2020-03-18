---
title: Procedimiento para recuperar un único elemento secundario (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: ce37db9e-76fa-46eb-b4cc-e8f32d22ad90
ms.openlocfilehash: 0e10cf230a73e6419f2d9c663766f9a24a0930af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75347476"
---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-c"></a>Procedimiento para recuperar un único elemento secundario (LINQ to XML) (C#)
En este tema se explica cómo recuperar un único elemento secundario, dado el nombre del elemento secundario. Si conoce el nombre del elemento secundario y que solo hay un elemento que tiene ese nombre, puede resultar cómodo recuperar solamente un elemento, en lugar de una recopilación.  
  
 El método <xref:System.Xml.Linq.XContainer.Element%2A> devuelve el primer <xref:System.Xml.Linq.XElement> secundario con el <xref:System.Xml.Linq.XName> especificado.  
  
 Si desea recuperar un único elemento secundario de Visual Basic, un enfoque común consiste en utilizar la propiedad XML y después recuperar el primer elemento mediante una notación de indizador de matriz.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra el uso del método <xref:System.Xml.Linq.XContainer.Element%2A>. Este ejemplo toma un árbol XML con el nombre `po` y busca el primer elemento con el nombre `Comment`.  
  
 El ejemplo de Visual Basic muestra el uso de la notación del indizador de matriz para recuperar un elemento único.  
  
 En este ejemplo se usa el siguiente documento XML: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md) (Archivo XML de ejemplo: pedido de compra común [LINQ to XML]).  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
XElement e = po.Element("DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo muestra el mismo código sobre un XML que se encuentra en un espacio de nombres. Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).  
  
 En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común en un espacio de nombres](./sample-xml-file-typical-purchase-order-in-a-namespace.md).  
  
```csharp  
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
XElement e = po.Element(aw + "DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a>Vea también

- [LINQ to XML Axes (C#)](./linq-to-xml-axes-overview.md) (Ejes de LINQ to XML [C#])
