---
title: Procedimiento para recuperar una colección de elementos (LINQ to XML) (C#)
description: El método Elements de C# recupera una colección de los elementos secundarios de un elemento. En este ejemplo de LINQ to XML se itera por los elementos secundarios de un elemento.
ms.date: 07/20/2015
ms.assetid: b849668c-7976-4974-b8e1-1cd587d34258
ms.openlocfilehash: 4f9b6ae4713af9ce1a4eeb5257f57cd9724f68b2
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103358"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-c"></a>Procedimiento para recuperar una colección de elementos (LINQ to XML) (C#)
En este tema se demuestra el método <xref:System.Xml.Linq.XContainer.Elements%2A>. Este método recupera una colección de elementos secundarios de un elemento.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo recorre en iteración los elementos secundarios del elemento `purchaseOrder`.  
  
 Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> childElements =  
    from el in po.Elements()  
    select el;  
foreach (XElement el in childElements)  
    Console.WriteLine("Name: " + el.Name);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```output  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a>Vea también

- [Ejes de LINQ to XML (C#)](./linq-to-xml-axes-overview.md)
