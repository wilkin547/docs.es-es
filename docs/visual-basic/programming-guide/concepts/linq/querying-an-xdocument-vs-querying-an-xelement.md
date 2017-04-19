---
title: Diferencias entre realizar consultas de un XDocument Un XElement (Visual Basic) | Documentos de Microsoft
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
ms.assetid: 2d111f84-0ded-4cde-8d93-5440557a726d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 29044cd118bfd8ecc12bddca722ee3656d455e0f
ms.lasthandoff: 03/13/2017


---
# <a name="querying-an-xdocument-vs-querying-an-xelement-visual-basic"></a>Diferencias entre realizar consultas de un XDocument Un XElement (Visual Basic)
Cuando carga un documento a través de <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, observará que tiene que escribir las consultas de forma ligeramente diferente que cuando se carga a través de <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>.</xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a>Comparación entre XDocument.Load y XElement.Load  
 Cuando carga un documento XML en un <xref:System.Xml.Linq.XElement>a través de <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, el <xref:System.Xml.Linq.XElement>en la raíz de XML árbol contiene el elemento raíz del documento cargado.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement> Sin embargo, cuando carga el mismo documento XML en una <xref:System.Xml.Linq.XDocument>a través de <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>la raíz del árbol es un <xref:System.Xml.Linq.XDocument>nodo y el elemento raíz del documento cargado es el secundario permitido un <xref:System.Xml.Linq.XElement>nodo del <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XDocument> Los ejes de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] funcionan en relación al nodo raíz.  
  
 Este primer ejemplo carga un árbol XML usando <xref:System.Xml.Linq.XElement.Load%2A>.</xref:System.Xml.Linq.XElement.Load%2A> A continuación, consulta los elementos secundarios de la raíz del árbol.  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XElement.Load")  
Console.WriteLine("----")  
Dim doc As XElement = XElement.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 Como cabe esperar, este ejemplo genera el siguiente resultado:  
  
```  
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 El ejemplo siguiente es el mismo que el anterior, con la excepción de que el árbol XML se carga en una <xref:System.Xml.Linq.XDocument>en lugar de un <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument>  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XDocument.Load")  
Console.WriteLine("----")  
Dim doc As XDocument = XDocument.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
</Root>  
```  
  
 Observe que la misma consulta devolvió el nodo `Root` en vez de los tres nodos secundarios.  
  
 Un enfoque para tratar con esto es usar el <xref:System.Xml.Linq.XDocument.Root%2A>propiedad antes de obtener acceso a los métodos de ejes, como sigue:</xref:System.Xml.Linq.XDocument.Root%2A>  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XDocument.Load")  
Console.WriteLine("----")  
Dim doc As XDocument = XDocument.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Root.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 Esta consulta se realiza ahora en la misma forma que la consulta en el árbol se basa en <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> El ejemplo genera el siguiente resultado:  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
## <a name="see-also"></a>Vea también  
 [Consultas básicas (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
