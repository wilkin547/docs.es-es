---
title: Quitar elementos, atributos y nodos de un árbol XML (C#)
ms.date: 07/20/2015
ms.assetid: 07dd06d6-1117-4077-bf98-9120cf51176e
ms.openlocfilehash: badaa6bab35367d62a73f56c5221cb7d6d4a45f7
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69591262"
---
# <a name="removing-elements-attributes-and-nodes-from-an-xml-tree-c"></a>Quitar elementos, atributos y nodos de un árbol XML (C#)

Puede modificar un árbol XML mediante la eliminación de elementos, atributos y otros tipos de nodos.

Quitar un elemento o un atributo de un documento XML resulta sencillo. Sin embargo, al quitar colecciones de elementos o atributos, primero debe materializar una colección en una lista y, a continuación, eliminar los elementos o los atributos de ésta. El mejor método consiste en usar el método de extensión <xref:System.Xml.Linq.Extensions.Remove%2A>, que se ocupará de todo esto.

El motivo principal radica en que la mayoría de las colecciones que se recuperan de un árbol XML se producen con una ejecución aplazada. Si no las materializa primero en una lista, o bien si no usa los métodos de extensión, es posible que aparezca una clase determinada de errores. Para obtener más información, vea [Errores en códigos declarativos/imperativos mixtos (LINQ to XML) (C#)](./mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).

Los siguientes métodos sirven para quitar nodos y atributos de un árbol XML.

|Método|DESCRIPCIÓN|
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

### <a name="description"></a>DESCRIPCIÓN

Este ejemplo demuestra tres métodos para quitar elementos. Primero, quita un solo elemento. En segundo lugar, recupera una colección de elementos, los materializa con el operador <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> y quita la colección. Por último, recupera una colección de elementos y los quita con el método de extensión <xref:System.Xml.Linq.Extensions.Remove%2A>.

Para obtener más información sobre el operador <xref:System.Linq.Enumerable.ToList%2A>, vea [Convertir tipos de datos (C#)](./converting-data-types.md).

### <a name="code"></a>Código

```csharp
XElement root = XElement.Parse(@"<Root>
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
</Root>");
root.Element("Child1").Element("GrandChild1").Remove();
root.Element("Child2").Elements().ToList().Remove();
root.Element("Child3").Elements().Remove();
Console.WriteLine(root);
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
