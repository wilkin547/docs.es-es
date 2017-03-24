---
title: Subdividida objetos XName y XNamespace (LINQ to XML) (Visual Basic) | Documentos de Microsoft
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
ms.assetid: 21ee7585-7df9-40b4-8c76-a12bb5f29bb3
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b08f3116f5acb404cf2c33072ec31fbaada4e7cb
ms.lasthandoff: 03/13/2017


---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml-visual-basic"></a>Subdividida objetos XName y XNamespace (LINQ to XML) (Visual Basic)
<xref:System.Xml.Linq.XName>y <xref:System.Xml.Linq.XNamespace>son objetos *atomizan*; es decir, si contienen el mismo nombre completo, hacen referencia al mismo objeto.</xref:System.Xml.Linq.XNamespace></xref:System.Xml.Linq.XName> De esta forma, se incrementan los beneficios de rendimiento de las consultas: cuando compare la igualdad de dos nombres atomizados, el lenguaje intermedio subyacente solo debe determinar si los dos puntos de referencia apuntan al mismo objeto. El código subyacente no debe hacer comparaciones de cadenas, ya que sería un proceso muy lento.  
  
## <a name="atomization-semantics"></a>Semántica de atomización  
 Atomización significa que si dos <xref:System.Xml.Linq.XName>objetos tienen el mismo nombre local y se encuentran en el mismo espacio de nombres, comparten la misma instancia.</xref:System.Xml.Linq.XName> De la misma manera, si dos <xref:System.Xml.Linq.XNamespace>objetos tienen el mismo espacio de nombres URI, comparten la misma instancia.</xref:System.Xml.Linq.XNamespace>  
  
 Para que una clase habilite objetos atomizados, el constructor de la clase debe ser privado y no público. La razón es que si el constructor fuera público, podría crea un objeto no atomizado. <xref:System.Xml.Linq.XName>Y <xref:System.Xml.Linq.XNamespace>las clases implementan un operador de conversión implícita para convertir una cadena en una <xref:System.Xml.Linq.XName>o <xref:System.Xml.Linq.XNamespace>.</xref:System.Xml.Linq.XNamespace> </xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XNamespace> </xref:System.Xml.Linq.XName> De esta forma, obtiene una instancia de estos objetos. No puede obtener ninguna instancia mediante un constructor, ya que no se puede tener acceso a él.  
  
 <xref:System.Xml.Linq.XName>y <xref:System.Xml.Linq.XNamespace>también implementan los operadores de igualdad y desigualdad, para determinar si los dos objetos que se comparan son referencias a la misma instancia.</xref:System.Xml.Linq.XNamespace></xref:System.Xml.Linq.XName>  
  
## <a name="example"></a>Ejemplo  
 El siguiente código crea algunos <xref:System.Xml.Linq.XElement>objetos y muestra que nombres idénticos comparten la misma instancia.</xref:System.Xml.Linq.XElement>  
  
```vb  
Dim r1 As New XElement("Root", "data1")  
Dim r2 As XElement = XElement.Parse("<Root>data2</Root>")  
  
If DirectCast(r1.Name, Object) = DirectCast(r2.Name, Object) Then  
    Console.WriteLine("r1 and r2 have names that refer to the same instance.")  
Else  
    Console.WriteLine("Different")  
End If  
  
Dim n As XName = "Root"  
  
If DirectCast(n, Object) = DirectCast(r1.Name, Object) Then  
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.")  
Else  
    Console.WriteLine("Different")  
End If  
  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
r1 and r2 have names that refer to the same instance.  
The name of r1 and the name in 'n' refer to the same instance.  
```  
  
 Como se mencionó anteriormente, la ventaja de los objetos atomizados es que al utilizar uno de los métodos de eje que toman un <xref:System.Xml.Linq.XName>como un parámetro, el método de eje solo debe determinar que dos nombres hagan referencia a la misma instancia para seleccionar los elementos deseados.</xref:System.Xml.Linq.XName>  
  
 En el ejemplo siguiente se pasa un <xref:System.Xml.Linq.XName>a la <xref:System.Xml.Linq.XContainer.Descendants%2A>la llamada de método, que tiene un mejor rendimiento gracias al patrón de atomización.</xref:System.Xml.Linq.XContainer.Descendants%2A> </xref:System.Xml.Linq.XName>  
  
```vb  
Dim root As New XElement("Root", New XElement("C1", 1), New XElement("Z1", New XElement("C1", 2), New XElement("C1", 1)))  
  
Dim query = From e In root.Descendants("C1") Where CInt(e) = 1e  
  
For Each z As var In query  
    Console.WriteLine(z)  
Next  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
<C1>1</C1>  
<C1>1</C1>  
```  
  
## <a name="see-also"></a>Vea también  
 [Rendimiento (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)
