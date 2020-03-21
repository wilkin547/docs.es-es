---
title: Introducción a los literales XML en Visual Basic2
ms.date: 07/20/2015
ms.assetid: 94fc0e03-978e-4c08-ab6c-0dc3c1e64f10
ms.openlocfilehash: 9f5c54574e51c537d9ea58d307afda10736d0d88
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266955"
---
# <a name="introduction-to-xml-literals-in-visual-basic"></a>Introducción a los literales XML de Visual Basic
En esta sección se proporciona información acerca de la creación de árboles XML en Visual Basic.  
  
 Para obtener información sobre el uso de los resultados de las consultas LINQ como contenido para un árbol XML, vea [Construcción funcional (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).  
  
 Para obtener más información sobre los literales XML en Visual Basic, vea [Información general de LINQ to XMLLINQ to XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md).  
  
## <a name="creating-xml-trees"></a>Crear árboles XML  
 El siguiente ejemplo muestra cómo crear un <xref:System.Xml.Linq.XElement>; en este caso, `contacts`:  
  
```vb  
Dim contacts As XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone>206-555-0144</Phone>  
            <Address>  
                <Street1>123 Main St</Street1>  
                <City>Mercer Island</City>  
                <State>WA</State>  
                <Postal>68042</Postal>  
            </Address>  
        </Contact>  
    </Contacts>  
```  
  
### <a name="creating-an-xelement-with-simple-content"></a>Crear un XElement con contenido simple  
 Puede crear un <xref:System.Xml.Linq.XElement> que incluya un contenido simple, tal y como se detalla a continuación:  
  
```vb  
Dim n as XElement = <Customer>Adventure Works</Customer>  
Console.WriteLine(n)
```  
  
 En este ejemplo se produce la siguiente salida:  
  
```xml  
<Customer>Adventure Works</Customer>  
```  
  
### <a name="creating-an-empty-element"></a>Crear un elemento vacío  
 Puede crear un <xref:System.Xml.Linq.XElement> vacío, tal y como se indica a continuación:  
  
```vb  
Dim n As XElement = <Customer/>  
Console.WriteLine(n)  
```  
  
 En este ejemplo se produce la siguiente salida:  
  
```xml  
<Customer />  
```  
  
### <a name="using-embedded-expressions"></a>Utilizar expresiones incrustadas  
 Una característica importante de los literales XML es que admiten el uso de expresiones incrustadas. Las expresiones incrustadas le permiten evaluar una expresión e incorporar los resultados de la expresión a un árbol XML. Si el resultado de evaluar la expresión es de tipo <xref:System.Xml.Linq.XElement>, se agregará un elemento al árbol. Si el resultado de evaluar la expresión es de tipo <xref:System.Xml.Linq.XAttribute>, se agregará un atributo al árbol. Puede agregar elementos y atributos al árbol solo en aquellos lugares donde sea válido.  
  
 Es importante reseñar que en una expresión incrustada solo puede aparecer una expresión única. No es posible incrustar varias instrucciones. Si una expresión se extiende más allá de una única línea, deberá utilizar el carácter de continuación de línea.  
  
 Si utiliza una expresión incrustada para agregar nodos (incluyendo elementos) y atributos ya existentes a nuevo árbol XML y los nodos existentes ya tienen elementos primarios, los nodos se clonarán. Esos nodos clonados nuevos se adjuntan al nuevo árbol XML. Si los nodos ya existentes no tienen elementos primarios, los nodos simplemente se adjuntan al nuevo árbol XML. El último ejemplo de este tema muestra este comportamiento.  
  
 El siguiente ejemplo utiliza una expresión incrustada para agregar un elemento al árbol:  
  
```vb  
xmlTree1 As XElement = _  
    <Root>  
        <Child>Contents</Child>  
    </Root>  
Dim xmlTree2 As XElement = _  
    <Root>  
        <%= xmlTree1.<Child> %>  
    </Root>  
Console.WriteLine(xmlTree2)  
```  
  
 En este ejemplo se produce la siguiente salida:  
  
```xml  
<Root>  
  <Child>Contents</Child>  
</Root>  
```  
  
### <a name="using-embedded-expressions-for-content"></a>Utilizar expresiones incrustadas para el contenido  
 Puede utilizar una expresión incrustada para proporcionar el contenido de un elemento:  
  
```vb  
Dim str As String  
str = "Some content"  
Dim root As XElement = <Root><%= str %></Root>  
Console.WriteLine(root)  
```  
  
 En este ejemplo se produce la siguiente salida:  
  
```xml  
<Root>Some content</Root>  
```  
  
### <a name="using-a-linq-query-in-an-embedded-expression"></a>Usar una consulta de LINQ en una expresión incrustada  
 Puede utilizar los resultados proporcionados por una consulta LINQ para el contenido de un elemento:  
  
```vb  
Dim arr As Integer() = {1, 2, 3}  
  
Dim n As XElement = _  
    <Root>  
        <%= From i In arr Select <Child><%= i %></Child> %>  
    </Root>  
  
Console.WriteLine(n)  
```  
  
 En este ejemplo se produce la siguiente salida:  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Child>3</Child>  
</Root>  
```  
  
### <a name="using-embedded-expressions-for-node-names"></a>Utilizar expresiones incrustadas para los nombres de los nodos  
 También puede utilizar expresiones incrustadas para calcular nombres de atributos, valores de atributos, nombres de elementos y valores de elementos:  
  
```vb  
Dim eleName As String = "ele"  
Dim attName As String = "att"  
Dim attValue As String = "aValue"  
Dim eleValue As String = "eValue"  
Dim n As XElement = _  
    <Root <%= attName %>=<%= attValue %>>  
        <<%= eleName %>>  
            <%= eleValue %>  
        </>  
    </Root>  
Console.WriteLine(n)  
```  
  
 En este ejemplo se produce la siguiente salida:  
  
```xml  
<Root att="aValue">  
  <ele>eValue</ele>  
</Root>  
```  
  
### <a name="cloning-vs-attaching"></a>Clonación frente a asociación  
 Como ya se mencionó anteriormente, si utiliza una expresión incrustada para agregar nodos (incluyendo elementos) y atributos ya existentes a nuevo árbol XML y los nodos existentes ya tienen elementos primarios, los nodos se clonarán y esos nuevos nodos clonados se adjuntarán al nuevo árbol XML. Si los nodos ya existentes no tienen elementos primarios, simplemente se adjuntan al nuevo árbol XML.  
  
```vb  
' Create a tree with a child element.  
Dim xmlTree1 As XElement = _  
    <Root>  
        <Child1>1</Child1>  
    </Root>  
  
' Create an element that is not parented.  
Dim child2 As XElement = <Child2>2</Child2>  
  
' Create a tree and add Child1 and Child2 to it.  
Dim xmlTree2 As XElement = _  
    <Root>  
        <%= xmlTree1.<Child1>(0) %>  
        <%= child2 %>  
    </Root>  
  
' Compare Child1 identity.  
Console.WriteLine("Child1 was {0}", _  
    IIf(xmlTree1.Element("Child1") Is xmlTree2.Element("Child1"), _  
    "attached", "cloned"))  
  
' Compare Child2 identity.  
Console.WriteLine("Child2 was {0}", _  
    IIf(child2 Is xmlTree2.Element("Child2"), _  
    "attached", "cloned"))  
```  
  
 En este ejemplo se produce la siguiente salida:  
  
```console  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a>Consulte también

- [Creación de árboles XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
