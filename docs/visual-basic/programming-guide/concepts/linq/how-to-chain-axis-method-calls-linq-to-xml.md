---
title: Procedimiento para encadenar llamadas de métodos de eje (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: e4e22942-39bd-460f-b3c0-9f09e53d3aa9
ms.openlocfilehash: 51396c9aaffb43badf405600251ed5cb06198dc3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84375140"
---
# <a name="how-to-chain-axis-method-calls-linq-to-xml-visual-basic"></a>Cómo: encadenar llamadas a métodos de eje (LINQ to XML) (Visual Basic)
Un patrón común que puede utilizar en el código consiste en llamar a un método Axis y, después, llamar a uno de los métodos de extensión Axes.  
  
 Hay dos métodos Axes con el nombre `Elements` que devuelven una colección de elementos: el método <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> y el método <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>. Puede combinar estos dos ejes para encontrar todos los elementos de un nombre especificado en una profundidad determinada del árbol.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> y <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> para buscar todos los elementos `Name` en todos los elementos `Address` de todos los elementos `PurchaseOrder`.  
  
 En este ejemplo se usa el siguiente documento XML: [Archivo XML de muestra: varios pedidos de compra (LINQ to XML)](sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
```vb  
Dim purchaseOrders As XElement = XElement.Load("PurchaseOrders.xml")  
Dim names As IEnumerable(Of XElement) = _  
    From el In purchaseOrders.<PurchaseOrder>.<Address>.<Name> _  
    Select el  
For Each e As XElement In names  
    Console.WriteLine(e)  
Next  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
 Esto funciona porque una de las implementaciones del eje `Elements` es un método de extensión en <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XContainer>. <xref:System.Xml.Linq.XElement> se deriva de <xref:System.Xml.Linq.XContainer>, de modo que puede llamar al método <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> según los resultados de una llamada al método <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>.  
  
## <a name="example"></a>Ejemplo  
 A veces, desea recuperar todos los elementos de una profundidad determinada cuando es posible que intervengan (o no) antecesores. Por ejemplo, en el siguiente documento, podría recuperar todos los elementos `ConfigParameter` que son secundarios del elemento `Customer`, pero no el elemento `ConfigParameter` que es un secundario del elemento `Root`.  
  
```xml  
<Root>  
  <ConfigParameter>RootConfigParameter</ConfigParameter>  
  <Customer>  
    <Name>Frank</Name>  
    <Config>  
      <ConfigParameter>FirstConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
  <Customer>  
    <Name>Bob</Name>  
    <!--This customer doesn't have a Config element-->  
  </Customer>  
  <Customer>  
    <Name>Bill</Name>  
    <Config>  
      <ConfigParameter>SecondConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
</Root>  
```  
  
 Para ello, puede usar el eje <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> de la siguiente manera:  
  
```vb  
Dim root As XElement = XElement.Load("Irregular.xml")  
Dim configParameters As IEnumerable(Of XElement) = _  
    root.<Customer>.<Config>.<ConfigParameter>  
For Each cp As XElement In configParameters  
    Console.WriteLine(cp)  
Next  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<ConfigParameter>FirstConfigParameter</ConfigParameter>  
<ConfigParameter>SecondConfigParameter</ConfigParameter>  
```  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo muestra la misma técnica para XML que se encuentre en un espacio de nombres. Para obtener más información, vea [información general sobre los espacios de nombres (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).  
  
 En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra en un espacio de nombres](sample-xml-file-multiple-purchase-orders-in-a-namespace.md).  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim purchaseOrders As XElement = XElement.Load("PurchaseOrdersInNamespace.xml")  
        Dim names As IEnumerable(Of XElement) = _  
            From el In purchaseOrders.<aw:PurchaseOrder>.<aw:Address>.<aw:Name> _  
            Select el  
        For Each e As XElement In names  
            Console.WriteLine(e)  
        Next  
    End Sub  
End Module  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<aw:Name xmlns:aw="http://www.adventure-works.com">Ellen Adams</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Tai Yee</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
```  
  
## <a name="see-also"></a>Vea también

- [Ejes de LINQ to XML (Visual Basic)](linq-to-xml-axes.md)
