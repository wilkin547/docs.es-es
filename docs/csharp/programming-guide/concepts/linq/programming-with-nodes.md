---
title: Programar con nodos (C#) | Microsoft Docs
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
ms.assetid: c38df0f2-c805-431a-93ff-9103a4284c2f
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b5cc31077c31d6ba08521a9ba6d602409734e695
ms.lasthandoff: 03/13/2017

---
# <a name="programming-with-nodes-c"></a>Programar con nodos (C#)
Los desarrolladores de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] que deben escribir programar como un editor de XML, un sistema de transformación o un sistema de escritura de informes a menudo deben escribir programas que funcionan en un nivel de granularidad más fino que los elementos y los atributos. A menudo deben trabajar en el nivel del nodo, manipulando nodos de texto, procesando instrucciones y comentarios. En este tema se proporcionan algunos detalles acerca de la programación en el nivel del nodo.  
  
## <a name="node-details"></a>Detalles del nodo  
 Existen varios detalles de programación que un programador que trabaja en el nivel de nodo debe conocer.  
  
### <a name="parent-property-of-children-nodes-of-xdocument-is-set-to-null"></a>La propiedad primaria de los nodos secundarios de XDocument está establecida en NULL  
 La propiedad <xref:System.Xml.Linq.XObject.Parent%2A> contiene el elemento primario <xref:System.Xml.Linq.XElement>, no el nodo primario. Los nodos secundarios de <xref:System.Xml.Linq.XDocument> no tienen ningún elemento primario <xref:System.Xml.Linq.XElement>. Su elemento primario es el documento, de forma que la propiedad <xref:System.Xml.Linq.XObject.Parent%2A> para esos nodos se establece en NULL.  
  
 En el siguiente ejemplo se muestra esto:  
  
```csharp  
XDocument doc = XDocument.Parse(@"<!-- a comment --><Root/>");  
Console.WriteLine(doc.Nodes().OfType<XComment>().First().Parent == null);  
Console.WriteLine(doc.Root.Parent == null);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
True  
True  
```  
  
### <a name="adjacent-text-nodes-are-possible"></a>Los nodos de texto adyacentes son posibles  
 En varios modelos de programación XML, los nodos de texto adyacente siempre están combinados. A veces se denomina normalización de los nodos de texto. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] no normaliza nodos de texto. Si agrega dos nodos de texto al mismo elemento, tendrá como resultado nodos de texto adyacentes. Pero si se agrega contenido especificado como una cadena en lugar de como un nodo <xref:System.Xml.Linq.XText>, es posible que [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] combine la cadena con un nodo de texto adyacente.  
  
 En el siguiente ejemplo se muestra esto:  
  
```csharp  
XElement xmlTree = new XElement("Root", "Content");  
  
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());  
  
// this does not add a new text node  
xmlTree.Add("new content");  
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());  
  
// this does add a new, adjacent text node  
xmlTree.Add(new XText("more text"));  
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
1  
1  
2  
```  
  
### <a name="empty-text-nodes-are-possible"></a>Los nodos de texto adyacentes vacíos son posibles  
 En algunos modelos de programación XML, se garantiza que los nodos de texto no contienen la cadena vacía. El razonamiento es que ese nodo de texto no tiene ninguna incidencia en la serialización de XML. No obstante, por la misma razón que los nodos de texto adyacentes son posibles, si quita el texto de un nodo de texto estableciendo su valor en la cadena vacía, el nodo de texto en sí no se eliminará.  
  
```csharp  
XElement xmlTree = new XElement("Root", "Content");  
XText textNode = xmlTree.Nodes().OfType<XText>().First();  
  
// the following line does not cause the removal of the text node.  
textNode.Value = "";  
  
XText textNode2 = xmlTree.Nodes().OfType<XText>().First();  
Console.WriteLine(">>{0}<<", textNode2);   
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
>><<  
```  
  
### <a name="an-empty-text-node-impacts-serialization"></a>Un nodo de texto vacío incide sobre la serialización  
 Si un elemento contiene solamente un nodo de texto que está vacío, se serializa con la sintaxis de etiqueta larga: `<Child></Child>`. Si un elemento no contiene ningún nodo secundario, se serializa con la sintaxis de etiqueta corta: `<Child />`.  
  
```csharp  
XElement child1 = new XElement("Child1",  
    new XText("")  
);  
XElement child2 = new XElement("Child2");  
Console.WriteLine(child1);  
Console.WriteLine(child2);   
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
<Child1></Child1>  
<Child2 />  
```  
  
### <a name="namespaces-are-attributes-in-the-linq-to-xml-tree"></a>Los espacios de nombres son atributos en el árbol LINQ to XML  
 Aunque las declaraciones del espacio de nombres tienen una sintaxis idéntica a los atributos, en algunas interfaces de programación como XSLT y XPath, las declaraciones de espacios de nombres no se consideran atributos. Pero en [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], los espacios de nombres se almacenan como objetos <xref:System.Xml.Linq.XAttribute> en el árbol XML. Si recorre en iteración los atributos de un elemento que contiene una declaración de espacio de nombres, verá la declaración de espacio de nombres como uno de los elementos de la recopilación devuelta.  
  
 La propiedad <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A> indica si un atributo es una declaración de espacio de nombres.  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root  
    xmlns='http://www.adventure-works.com'  
    xmlns:fc='www.fourthcoffee.com'  
    AnAttribute='abc'/>");  
foreach (XAttribute att in root.Attributes())  
    Console.WriteLine("{0}  IsNamespaceDeclaration:{1}", att, att.IsNamespaceDeclaration);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
xmlns="http://www.adventure-works.com"  IsNamespaceDeclaration:True  
xmlns:fc="www.fourthcoffee.com"  IsNamespaceDeclaration:True  
AnAttribute="abc"  IsNamespaceDeclaration:False  
```  
  
### <a name="xpath-axis-methods-do-not-return-child-white-space-of-xdocument"></a>Los métodos del eje XPath no devuelven un espacio en blanco secundario de XDocument  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] permite nodos de texto secundarios de un <xref:System.Xml.Linq.XDocument>, mientras los nodos de texto solamente contengan espacio en blanco. Pero el modelo de objetos de XPath no incluye el espacio en blanco como nodos secundarios de un documento, por lo que cuando se recorren en iteración los elementos secundarios de un <xref:System.Xml.Linq.XDocument> usando el eje <xref:System.Xml.Linq.XContainer.Nodes%2A>, se devolverán los nodos de texto de espacio en blanco. En cambio, cuando se recorren en iteración los elementos secundarios de un <xref:System.Xml.Linq.XDocument> usando los métodos de eje de XPath, no se devolverán los nodos de texto de espacio en blanco.  
  
```csharp  
// Create a document with some white space child nodes of the document.  
XDocument root = XDocument.Parse(  
@"<?xml version='1.0' encoding='utf-8' standalone='yes'?>  
  
<Root/>  
  
<!--a comment-->  
", LoadOptions.PreserveWhitespace);  
  
// count the white space child nodes using LINQ to XML  
Console.WriteLine(root.Nodes().OfType<XText>().Count());  
  
// count the white space child nodes using XPathEvaluate  
Console.WriteLine(((IEnumerable)root.XPathEvaluate("text()")).OfType<XText>().Count());   
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
3  
0  
```  
  
### <a name="xdeclaration-objects-are-not-nodes"></a>Los objetos XDeclaration no son nodos  
 Cuando se recorren en iteración los nodos secundarios de un <xref:System.Xml.Linq.XDocument>, no se verá el objeto de declaración XML. Es una propiedad del documento, no un nodo secundario de él.  
  
```csharp  
XDocument doc = new XDocument(  
    new XDeclaration("1.0", "utf-8", "yes"),  
    new XElement("Root")  
);  
doc.Save("Temp.xml");  
Console.WriteLine(File.ReadAllText("Temp.xml"));  
  
// this shows that there is only one child node of the document  
Console.WriteLine(doc.Nodes().Count());  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root />  
1  
```  
  
## <a name="see-also"></a>Vea también  
 [Programación avanzada de LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
