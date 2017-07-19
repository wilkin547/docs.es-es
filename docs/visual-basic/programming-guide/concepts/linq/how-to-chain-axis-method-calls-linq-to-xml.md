---
title: "Cómo: encadenar llamadas de método de eje (LINQ to XML) (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: e4e22942-39bd-460f-b3c0-9f09e53d3aa9
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7c0e9d440ab50b7f275296731e5210578bcedcaa
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-chain-axis-method-calls-linq-to-xml-visual-basic"></a>Cómo: encadenar llamadas de método de eje (LINQ to XML) (Visual Basic)
Un patrón común que puede utilizar en el código consiste en llamar a un método Axis y, después, llamar a uno de los métodos de extensión Axes.  
  
 Hay dos ejes con el nombre de `Elements` que devuelven una colección de elementos: el <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>método y <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName>método.</xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> </xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> Puede combinar estos dos ejes para encontrar todos los elementos de un nombre especificado en una profundidad determinada del árbol.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo utiliza <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>y <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName>para encontrar todos los `Name` en todos los elementos `Address` en todos los elementos `PurchaseOrder` elementos.</xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> </xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>  
  
 Este ejemplo utiliza el siguiente documento XML: [archivo XML de muestra: varios pedidos de compra (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
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
  
 Esto funciona porque una de las implementaciones de la `Elements` eje es un método de extensión de <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer> </xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement>se deriva de <xref:System.Xml.Linq.XContainer>, por lo que se puede llamar a la <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName>método en los resultados de una llamada a la <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>método.</xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> </xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> </xref:System.Xml.Linq.XContainer></xref:System.Xml.Linq.XElement>  
  
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
  
 Para ello, puede usar el <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName>eje, como sigue:</xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName>  
  
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
 El siguiente ejemplo muestra la misma técnica para XML que se encuentre en un espacio de nombres. Para obtener más información, consulte [trabajar con espacios de nombres XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
 Este ejemplo utiliza el siguiente documento XML: [archivo XML de muestra: varios pedidos de compra en un Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).  
  
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
 [Ejes LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
