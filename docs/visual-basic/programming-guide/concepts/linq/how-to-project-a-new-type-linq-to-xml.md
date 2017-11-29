---
title: "Cómo: proyectar un nuevo tipo (LINQ to XML) (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8cfb24f5-89b2-4cfb-b85d-e7963f8f1845
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 73b677e45be1d457d54de01331c93f60348e6bfd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-project-a-new-type-linq-to-xml-visual-basic"></a>Cómo: proyectar un nuevo tipo (LINQ to XML) (Visual Basic)
Otros ejemplos de esta sección han mostrado consultados que devuelven resultados como <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> de `string` y <xref:System.Collections.Generic.IEnumerable%601> de `int`. Se trata de tipos de resultados comunes, pero no son adecuados para cada caso. En muchos casos querrá que sus consultas devuelvan un <xref:System.Collections.Generic.IEnumerable%601> de algún otro tipo.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra como crear instancias de objetos en la cláusula `Select`. El código primero define una nueva clase con un constructor y después modifica la instrucción `Select` para que la expresión sea una nueva instancia de la nueva clase.  
  
 En este ejemplo se usa el siguiente documento XML: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md) (Archivo XML de ejemplo: pedido de compra común [LINQ to XML]).  
  
```vb  
Public Class NameQty  
    Public name As String  
    Public qty As Integer  
    Public Sub New(ByVal n As String, ByVal q As Integer)  
        name = n  
        qty = q  
    End Sub  
End Class  
  
Public Class Program  
    Shared Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
  
        Dim nqList As IEnumerable(Of NameQty) = _  
            From n In po...<Item> _  
            Select New NameQty( _  
                n.<ProductName>.Value, CInt(n.<Quantity>.Value))  
  
        For Each n As NameQty In nqList  
            Console.WriteLine(n.name & ":" & n.qty)  
        Next  
    End Sub  
End Class  
```  
  
 Este ejemplo se utiliza la `M:System.Xml.Linq.XElement.Element` método que se introdujo en el tema [Cómo: recuperar un único elemento secundario (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md). También utiliza conversiones para recuperar los valores de los elementos devueltos por el método `M:System.Xml.Linq.XElement.Element`.  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
Lawnmower:1  
Baby Monitor:2  
```  
  
## <a name="see-also"></a>Vea también  
 [Proyecciones y transformaciones (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
