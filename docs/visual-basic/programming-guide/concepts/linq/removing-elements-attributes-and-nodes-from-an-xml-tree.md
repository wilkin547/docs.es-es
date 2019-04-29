---
title: Quitar elementos, atributos y nodos de un árbol XML (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 5cf21919-4360-4b49-b29d-58ea3164ac72
ms.openlocfilehash: 85a7a3b4047e269c562177cfa045b952472aaac2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787075"
---
# <a name="removing-elements-attributes-and-nodes-from-an-xml-tree-visual-basic"></a>Quitar elementos, atributos y nodos de un árbol XML (Visual Basic)
Puede modificar un árbol XML mediante la eliminación de elementos, atributos y otros tipos de nodos.  
  
 Quitar un elemento o un atributo de un documento XML resulta sencillo. Sin embargo, al quitar colecciones de elementos o atributos, primero debe materializar una colección en una lista y, a continuación, eliminar los elementos o los atributos de ésta. El mejor método consiste en usar el método de extensión <xref:System.Xml.Linq.Extensions.Remove%2A>, que se ocupará de todo esto.  
  
 El motivo principal radica en que la mayoría de las colecciones que se recuperan de un árbol XML se producen con una ejecución aplazada. Si no las materializa primero en una lista, o bien si no usa los métodos de extensión, es posible que aparezca una clase determinada de errores. Para obtener más información, consulte [declarativa código/errores imperativos mixtos (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).  
  
 Los siguientes métodos sirven para quitar nodos y atributos de un árbol XML.  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Remove%2A?displayProperty=nameWithType>|Quita un elemento <xref:System.Xml.Linq.XAttribute> de su elemento primario.|  
|<xref:System.Xml.Linq.XContainer.RemoveNodes%2A?displayProperty=nameWithType>|Quita los nodos secundarios de un elemento <xref:System.Xml.Linq.XContainer> de la colección.|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|Quita el contenido y los atributos de un elemento <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|Quita los atributos de un elemento <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|Si pasa `null` para el valor, quita el atributo.|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|Si pasa `null` para el valor, quita el elemento secundario.|  
|<xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=nameWithType>|Quita un elemento <xref:System.Xml.Linq.XNode> de su elemento primario.|  
|<xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=nameWithType>|Quita todos los atributos o elementos de la colección de origen de su elemento primario.|  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 Este ejemplo demuestra tres métodos para quitar elementos. Primero, quita un solo elemento. En segundo lugar, recupera una colección de elementos, los materializa con el operador <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> y quita la colección. Por último, recupera una colección de elementos y los quita con el método de extensión <xref:System.Xml.Linq.Extensions.Remove%2A>.  
  
 Para obtener más información sobre la <xref:System.Linq.Enumerable.ToList%2A> operador, consulte [convertir tipos de datos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).  
  
### <a name="code"></a>Código  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>  
            <GrandChild1/>  
            <GrandChild2/>  
            <GrandChild3/>  
        </Child1>  
        <Child2>  
            <GrandChild4/>  
            <GrandChild5/>  
            <GrandChild6/>  
        </Child2>  
        <Child3>  
            <GrandChild7/>  
            <GrandChild8/>  
            <GrandChild9/>  
        </Child3>  
    </Root>  
root.<Child1>.<GrandChild1>.Remove()  
root.<Child2>.Elements().ToList().Remove()  
root.<Child3>.Elements().Remove()  
Console.WriteLine(root)  
```  
  
### <a name="comments"></a>Comentarios  
 Este código genera el siguiente resultado:  
  
```xml  
<Root>  
  <Child1>  
    <GrandChild2 />  
    <GrandChild3 />  
  </Child1>  
  <Child2 />  
  <Child3 />  
</Root>  
```  
  
 Tenga en cuenta que el primer elemento descendiente del secundario se ha quitado de `Child1`. Todos los elementos descendientes del secundario se han quitado de `Child2` y `Child3`.  
  
## <a name="see-also"></a>Vea también

- [Modificar árboles XML (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
