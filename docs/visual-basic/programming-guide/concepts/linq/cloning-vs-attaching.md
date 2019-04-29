---
title: Diferencias entre clonación y Asociación (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 3c3bd105-c9d3-49bd-875b-27ab4e8bc7a3
ms.openlocfilehash: 59ffedfdbb2820683f1e6cc232154688f5c29fc8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789108"
---
# <a name="cloning-vs-attaching-visual-basic"></a>Diferencias entre clonación y Asociación (Visual Basic)
Cuando se asocian objetos <xref:System.Xml.Linq.XNode> (incluyendo el objeto <xref:System.Xml.Linq.XElement>) o <xref:System.Xml.Linq.XAttribute> a un árbol nuevo, si el contenido nuevo no tiene un elemento primario, los objetos simplemente se adjuntan al árbol XML. Si el nuevo contenido ya tiene un elemento primario y forma parte de otro árbol XML, se clona el nuevo contenido. Es nuevo contenido clonado se adjunta al árbol XML.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código demuestra qué ocurre si agrega un elemento que tiene elemento primario a un árbol y qué ocurre si agrega un elemento que no tenga elemento primario a un árbol.  
  
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
  
 Este ejemplo produce el siguiente resultado:  
  
```  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a>Vea también

- [Crear árboles XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
