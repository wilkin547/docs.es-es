---
title: "Cómo: recuperar el valor superficial de un elemento (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 730a6670-fb8c-41fc-8a1b-eb97a837e432
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 673b890ab842d1c18c8020eefe03d90086d1bf4e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-visual-basic"></a>Cómo: recuperar el valor superficial de un elemento (Visual Basic)
Este tema muestra cómo obtener el valor superficial de un elemento. El valor superficial es el valor del elemento específico solamente, en oposición al valor profundo, que incluye los valores de todos los elementos descendientes concatenados en una sola cadena.  
  
 Cuando se recupera el valor de un elemento utilizando la conversión o la propiedad <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>, se recupera el valor profundo. Para recuperar el valor superficial, se puede usar el método de extensión `ShallowValue`, como se muestra en el ejemplo siguiente. La recuperación del valor superficial es útil cuando se desea seleccionar elementos en función de su contenido.  
  
 En el ejemplo siguiente se declara un método de extensión que recupera el valor superficial de un elemento. A continuación, se utiliza el método de extensión en una consulta para enumerar todos los elementos que contienen un valor calculado.  
  
## <a name="example"></a>Ejemplo  
 El siguiente archivo de texto, Report.xml, es el origen de este ejemplo.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Report>  
  <Section>  
    <Heading>  
      <Column Name="CustomerId">=Customer.CustomerId.Heading</Column>  
      <Column Name="Name">=Customer.Name.Heading</Column>  
    </Heading>  
    <Detail>  
      <Column Name="CustomerId">=Customer.CustomerId</Column>  
      <Column Name="Name">=Customer.Name</Column>  
    </Detail>  
  </Section>  
</Report>  
```  
  
```vb  
Module Module1  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function ShallowValue(ByVal xe As XElement)  
        Return xe _  
               .Nodes() _  
               .OfType(Of XText)() _  
               .Aggregate(New StringBuilder(), _  
                              Function(s, c) s.Append(c), _  
                              Function(s) s.ToString())  
    End Function  
  
    Sub Main()  
        Dim root As XElement = XElement.Load("Report.xml")  
  
        Dim query As IEnumerable(Of XElement) = _  
            From el In root.Descendants() _  
            Where (el.ShallowValue().StartsWith("=")) _  
            Select el  
  
        For Each q As XElement In query  
            Console.WriteLine("{0}{1}{2}", _  
                q.Name.ToString().PadRight(8), _  
                q.Attribute("Name").ToString().PadRight(20), _  
                q.ShallowValue())  
        Next  
    End Sub  
End Module  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
Column  Name="CustomerId"   =Customer.CustomerId.Heading  
Column  Name="Name"         =Customer.Name.Heading  
Column  Name="CustomerId"   =Customer.CustomerId  
Column  Name="Name"         =Customer.Name  
```  
  
## <a name="see-also"></a>Vea también  
 [Ejes de LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
