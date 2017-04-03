---
title: Diferencias entre realizar consultas de un XDocument Realizar consultas de un XElement (C#) | Microsoft Docs
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 46221ff5-62ee-4de8-93ba-66465facb5c1
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9a3da563618ad3dbc9797f252ab51588a43ce8e6
ms.lasthandoff: 03/13/2017


---
# <a name="querying-an-xdocument-vs-querying-an-xelement-c"></a>Diferencias entre realizar consultas de un XDocument Realizar consultas de un XElement (C#)
Cuando cargue un documento a través de <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, observará que tiene que escribir las consultas de manera ligeramente diferente a cuando lo carga a través de <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>.  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a>Comparación entre XDocument.Load y XElement.Load  
 Cuando carga un documento XML en un <xref:System.Xml.Linq.XElement> a través de <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, el <xref:System.Xml.Linq.XElement> de la raíz del árbol XML contiene el elemento raíz del documento cargado. En cambio, cuando carga el mismo documento XML en un <xref:System.Xml.Linq.XDocument> a través de <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, la raíz del árbol es un nodo <xref:System.Xml.Linq.XDocument> y el elemento raíz del documento cargado es el nodo secundario permitido <xref:System.Xml.Linq.XElement> del <xref:System.Xml.Linq.XDocument>. Los ejes de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] funcionan en relación al nodo raíz.  
  
 En este primer ejemplo se carga un árbol XML mediante <xref:System.Xml.Linq.XElement.Load%2A>. A continuación, consulta los elementos secundarios de la raíz del árbol.  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XElement.Load");  
Console.WriteLine("----");  
XElement doc = XElement.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 Como cabe esperar, este ejemplo genera el siguiente resultado:  
  
```  
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 El ejemplo siguiente es el mismo que el anterior, con la excepción de que el árbol XML se carga en un <xref:System.Xml.Linq.XDocument> en lugar de un <xref:System.Xml.Linq.XElement>.  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
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
  
 Una forma de abordar esta situación consiste en usar la propiedad <xref:System.Xml.Linq.XDocument.Root%2A> antes de acceder a los métodos de los ejes, tal y como se indica a continuación:  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Root.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 Ahora, esta consulta genera el mismo resultado que la consulta del árbol cuya raíz se encuentra en <xref:System.Xml.Linq.XElement>. El ejemplo genera el siguiente resultado:  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
## <a name="see-also"></a>Vea también  
 [Consultas básicas (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
