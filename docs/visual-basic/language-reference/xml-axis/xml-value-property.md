---
title: Propiedad Value de XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 571d9130ef69df580bbba5d90bc8758b4b627196
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349422"
---
# <a name="xml-value-property-visual-basic"></a>Value (Propiedad XML) (Visual Basic)

Provides access to the value of the first element of a collection of <xref:System.Xml.Linq.XElement> objects.

## <a name="syntax"></a>Sintaxis

```vb
object.Value
```

## <a name="parts"></a>Elementos

|Término|de esquema JSON|  
|---|---|  
|`object`|Requerido. Una colección de objetos <xref:System.Xml.Linq.XElement>.|  

## <a name="return-value"></a>Valor devuelto

 A `String` that contains the value of the first element of the collection, or `Nothing` if the collection is empty.

## <a name="remarks"></a>Comentarios

 The <xref:System.Xml.Linq.XElement.Value%2A> property makes it easy to access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> objects. This property first checks whether the collection contains at least one object. If the collection is empty, this property returns `Nothing`. Otherwise, this property returns the value of the <xref:System.Xml.Linq.XElement.Value%2A> property of the first element in the collection.

> [!NOTE]
> When you access the value of an XML attribute using the '\@' identifier, the attribute value is returned as a `String` and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.

 To access other elements in a collection, you can use the XML extension indexer property. For more information, see [Extension Indexer Property](extension-indexer-property.md).

## <a name="inheritance"></a>Herencia

 Most users will not have to implement <xref:System.Collections.Generic.IEnumerable%601>, and can therefore ignore this section.

 The <xref:System.Xml.Linq.XElement.Value%2A> property is an extension property for types that implement `IEnumerable(Of XElement)`. The binding of this extension property is like the binding of extension methods: if a type implements one of the interfaces and defines a property that has the name "Value", that property has precedence over the extension property. In other words, this <xref:System.Xml.Linq.XElement.Value%2A> property can be overridden by defining a new property in a class that implements `IEnumerable(Of XElement)`.

## <a name="example"></a>Ejemplo

 The following example shows how to use the <xref:System.Xml.Linq.XElement.Value%2A> property to access the first node in a collection of <xref:System.Xml.Linq.XElement> objects. The example uses the child axis property to get the collection of all child nodes named `phone` that are in the `contact` object.

 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]

 Este código muestra el siguiente texto:

 `Phone number: 206-555-0144`

## <a name="example"></a>Ejemplo

 The following example shows how to get the value of an XML attribute from a collection of <xref:System.Xml.Linq.XAttribute> objects. The example uses the attribute axis property to display the value of the `type` attribute for all of the `phone` elements.

 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]

 Este código muestra el siguiente texto:

 ```console
 home
 work
```

## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [Propiedades del eje XML](index.md)
- [Literales XML](../xml-literals/index.md)
- [Crear XML en Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Métodos de extensión](../../programming-guide/language-features/procedures/extension-methods.md)
- [Propiedad de indexador de extensión](extension-indexer-property.md)
- [Propiedad del eje secundario XML](xml-child-axis-property.md)
- [Propiedad del eje de atributo XML](xml-attribute-axis-property.md)
