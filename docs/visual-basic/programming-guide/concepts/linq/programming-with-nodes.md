---
title: Programar con nodos
ms.date: 07/20/2015
ms.assetid: d8422a9b-dd37-44a3-8aac-2237ed9561e0
ms.openlocfilehash: b2c9022cb57cf122af47bbe6d1a7fe2b4d41327c
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266968"
---
# <a name="programming-with-nodes-visual-basic"></a>Programación con nodos (Visual Basic)
Los desarrolladores de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] que deben escribir programar como un editor de XML, un sistema de transformación o un sistema de escritura de informes a menudo deben escribir programas que funcionan en un nivel de granularidad más fino que los elementos y los atributos. A menudo deben trabajar en el nivel del nodo, manipulando nodos de texto, procesando instrucciones y comentarios. En este tema se proporcionan algunos detalles acerca de la programación en el nivel del nodo.  
  
## <a name="node-details"></a>Detalles del nodo  
 Existen varios detalles de programación que un programador que trabaja en el nivel de nodo debe conocer.  
  
### <a name="parent-property-of-children-nodes-of-xdocument-is-set-to-null"></a>La propiedad primaria de los nodos secundarios de XDocument está establecida en NULL  
 La propiedad <xref:System.Xml.Linq.XObject.Parent%2A> contiene el <xref:System.Xml.Linq.XElement> primario, no el nodo primario. Los nodos secundarios de <xref:System.Xml.Linq.XDocument> no tienen <xref:System.Xml.Linq.XElement> primario. Su elemento primario es el documento, de forma que la propiedad <xref:System.Xml.Linq.XObject.Parent%2A> para esos nodos se establece en NULL.  
  
 En el siguiente ejemplo se muestra esto:  
  
```vb  
Dim doc As XDocument = XDocument.Parse("<!-- a comment --><Root/>")  
Console.WriteLine(doc.Nodes().OfType(Of XComment).First().Parent Is Nothing)  
Console.WriteLine(doc.Root.Parent Is Nothing)  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```console  
True  
True  
```  
  
### <a name="adjacent-text-nodes-are-possible"></a>Los nodos de texto adyacentes son posibles  
 En varios modelos de programación XML, los nodos de texto adyacente siempre están combinados. A veces se denomina normalización de los nodos de texto. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] no normaliza nodos de texto. Si agrega dos nodos de texto al mismo elemento, tendrá como resultado nodos de texto adyacentes. En cambio, si agrega contenido especificado como una cadena en lugar de un nodo <xref:System.Xml.Linq.XText>, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] puede combinar la cadena con un nodo de texto adyacente.  
  
 En el siguiente ejemplo se muestra esto:  
  
```vb  
Dim xmlTree As XElement = <Root>Content</Root>  
Console.WriteLine(xmlTree.Nodes().OfType(Of XText)().Count())  
  
' This does not add a new text node.  
xmlTree.Add("new content")  
Console.WriteLine(xmlTree.Nodes().OfType(Of XText)().Count())  
  
'// This does add a new, adjacent text node.  
xmlTree.Add(New XText("more text"))  
Console.WriteLine(xmlTree.Nodes().OfType(Of XText)().Count())  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```console  
1  
1  
2  
```  
  
### <a name="empty-text-nodes-are-possible"></a>Los nodos de texto adyacentes vacíos son posibles  
 En algunos modelos de programación XML, se garantiza que los nodos de texto no contienen la cadena vacía. El razonamiento es que ese nodo de texto no tiene ninguna incidencia en la serialización de XML. No obstante, por la misma razón que los nodos de texto adyacentes son posibles, si quita el texto de un nodo de texto estableciendo su valor en la cadena vacía, el nodo de texto en sí no se eliminará.  
  
```vb  
Dim xmlTree As XElement = <Root>Content</Root>  
Dim textNode As XText = xmlTree.Nodes().OfType(Of XText)().First()  
  
' The following line does not cause the removal of the text node.  
textNode.Value = ""  
  
Dim textNode2 As XText = xmlTree.Nodes().OfType(Of XText)().First()  
Console.WriteLine(">>{0}<<", textNode2)  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```console  
>><<  
```  
  
### <a name="an-empty-text-node-impacts-serialization"></a>Un nodo de texto vacío incide sobre la serialización  
 Si un elemento contiene solamente un nodo de texto que está vacío, se serializa con la sintaxis de etiqueta larga: `<Child></Child>`. Si un elemento no contiene ningún nodo secundario, se serializa con la sintaxis de etiqueta corta: `<Child />`.  
  
```vb  
Dim child1 As XElement = New XElement("Child1", _  
    New XText("") _  
)  
Dim child2 As XElement = New XElement("Child2")  
Console.WriteLine(child1)  
Console.WriteLine(child2)  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Child1></Child1>  
<Child2 />  
```  
  
### <a name="namespaces-are-attributes-in-the-linq-to-xml-tree"></a>Los espacios de nombres son atributos en el árbol LINQ to XML  
 Aunque las declaraciones del espacio de nombres tienen una sintaxis idéntica a los atributos, en algunas interfaces de programación como XSLT y XPath, las declaraciones de espacios de nombres no se consideran atributos. No obstante, en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], los espacios de nombres se almacenan como objetos <xref:System.Xml.Linq.XAttribute> en el árbol XML. Si recorre en iteración los atributos de un elemento que contiene una declaración de espacio de nombres, verá la declaración de espacio de nombres como uno de los elementos de la recopilación devuelta.  
  
 La propiedad <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A> indica si un atributo es una declaración de espacio de nombres.  
  
```vb  
Dim root As XElement = _
<Root  
    xmlns='http://www.adventure-works.com'  
    xmlns:fc='www.fourthcoffee.com'  
    AnAttribute='abc'/>  
For Each att As XAttribute In root.Attributes()  
    Console.WriteLine("{0}  IsNamespaceDeclaration:{1}", att, _  
                      att.IsNamespaceDeclaration)  
Next  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```console  
xmlns="http://www.adventure-works.com"  IsNamespaceDeclaration:True  
xmlns:fc="www.fourthcoffee.com"  IsNamespaceDeclaration:True  
AnAttribute="abc"  IsNamespaceDeclaration:False  
```  
  
### <a name="xpath-axis-methods-do-not-return-child-white-space-of-xdocument"></a>Los métodos del eje XPath no devuelven un espacio en blanco secundario de XDocument  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] permite nodos de texto secundarios de un <xref:System.Xml.Linq.XDocument> mientras los nodos de texto contengan solamente espacios en blanco. No obstante, el modelo del objeto XPath no incluye el espacio en blanco como nodos secundarios de un documento, así que cuando recorra en iteración los elementos secundarios de <xref:System.Xml.Linq.XDocument> usando el eje <xref:System.Xml.Linq.XContainer.Nodes%2A>, se devolverán los nodos de texto del espacio en blanco. Sin embargo, cuando recorra en iteración los elementos secundarios de <xref:System.Xml.Linq.XDocument> usando los métodos del eje de XPath, no se devolverán los nodos de texto de espacio en blanco.  
  
```vb  
' Create a document with some white space child nodes of the document.  
Dim root As XDocument = XDocument.Parse( _  
"<?xml version='1.0' encoding='utf-8' standalone='yes'?>" & _  
vbNewLine & "<Root/>" & vbNewLine & "<!--a comment-->" & vbNewLine, _  
LoadOptions.PreserveWhitespace)  
  
' Count the white space child nodes using LINQ to XML.  
Console.WriteLine(root.Nodes().OfType(Of XText)().Count())  
  
' Count the white space child nodes using XPathEvaluate.  
Dim nodes As IEnumerable = CType(root.XPathEvaluate("text()"), IEnumerable)  
Console.WriteLine(nodes.OfType(Of XText)().Count())  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```console  
3  
0  
```  
  
### <a name="xdeclaration-objects-are-not-nodes"></a>Los objetos XDeclaration no son nodos  
 Cuando recorra en iteración los nodos secundarios de <xref:System.Xml.Linq.XDocument>, no verá el objeto de declaración XML. Es una propiedad del documento, no un nodo secundario de él.  
  
```vb  
Dim doc As XDocument = _  
<?xml version='1.0' encoding='utf-8' standalone='yes'?>  
<Root/>  
  
doc.Save("Temp.xml")  
Console.WriteLine(File.ReadAllText("Temp.xml"))  
  
' This shows that there is only one child node of the document.  
Console.WriteLine(doc.Nodes().Count())  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root />  
1  
```  
  
## <a name="see-also"></a>Consulte también

- [Programación avanzada de LINQ to XMLLINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
