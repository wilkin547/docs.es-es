---
title: Procedimiento para escribir consultas con filtrado complejo
ms.date: 07/20/2015
ms.assetid: bf286ffc-7990-4b00-a4eb-ee3d70129950
ms.openlocfilehash: 18ed4379b7ec9c8007cc3c189fc45571b5161911
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397627"
---
# <a name="how-to-write-queries-with-complex-filtering-visual-basic"></a>Cómo: escribir consultas con filtrado complejo (Visual Basic)
Es posible que desee escribir consultas LINQ to XML con filtros complejos. Por ejemplo, quizás debe buscar todos los elementos que tienen un elemento secundario con un valor y un nombre específicos. En este tema se proporciona un ejemplo de escritura de una consulta con un filtrado complejo.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo buscar todos los elementos `PurchaseOrder` que tienen un elemento `Address` secundario que tiene un atributo `Type` igual a "Shipping" (envío) y un elemento `State` secundario igual a "NY". Utiliza una consulta anidada en la cláusula `Where` y el operador `Any` devuelve `True` si la colección tiene elementos en ella.  
  
 En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra (LINQ to XML)](sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
 Para obtener más información sobre el `Any` operador, vea [operaciones cuantificadoras (Visual Basic)](quantifier-operations.md).  
  
```vb  
Dim root As XElement = XElement.Load("PurchaseOrders.xml")  
Dim purchaseOrders As IEnumerable(Of XElement) = _  
    From el In root.<PurchaseOrder> _  
    Where _  
        (From add In el.<Address> _  
        Where _  
             add.@Type = "Shipping" And _  
             add.<State>.Value = "NY" _  
        Select add) _  
    .Any() _  
    Select el  
For Each el As XElement In purchaseOrders  
    Console.WriteLine(el.@PurchaseOrderNumber)  
Next  
```  
  
 Este código genera el siguiente resultado:  
  
```console  
99505  
```  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres. Para obtener más información, vea [información general sobre los espacios de nombres (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).  
  
 En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra en un espacio de nombres](sample-xml-file-multiple-purchase-orders-in-a-namespace.md).  
  
```vb  
Imports <xmlns:aw='http://www.adventure-works.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("PurchaseOrdersInNamespace.xml")  
        Dim purchaseOrders As IEnumerable(Of XElement) = _  
            From el In root.<aw:PurchaseOrder> _  
            Where _  
                (From add In el.<aw:Address> _  
                Where _  
                     add.@aw:Type = "Shipping" And _  
                     add.<aw:State>.Value = "NY" _  
                Select add) _  
            .Any() _  
            Select el  
        For Each el As XElement In purchaseOrders  
            Console.WriteLine(el.@aw:PurchaseOrderNumber)  
        Next  
    End Sub  
End Module  
```  
  
 Este código genera el siguiente resultado:  
  
```console  
99505  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [Consultas básicas (LINQ to XML) (Visual Basic)](basic-queries-linq-to-xml.md)
- [XML Child Axis Property](../../../language-reference/xml-axis/xml-child-axis-property.md)
- [XML Attribute Axis Property](../../../language-reference/xml-axis/xml-attribute-axis-property.md)
- [Propiedad de valor XML](../../../language-reference/xml-axis/xml-value-property.md)
- [Operaciones de proyección (Visual Basic)](projection-operations.md)
- [Operaciones cuantificadoras (Visual Basic)](quantifier-operations.md)
