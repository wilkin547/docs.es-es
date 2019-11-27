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

Proporciona acceso al valor del primer elemento de una colección de objetos <xref:System.Xml.Linq.XElement>.

## <a name="syntax"></a>Sintaxis

```vb
object.Value
```

## <a name="parts"></a>Elementos

|Término|Definición|  
|---|---|  
|`object`|Obligatorio. Una colección de objetos <xref:System.Xml.Linq.XElement>.|  

## <a name="return-value"></a>Valor devuelto

 `String` que contiene el valor del primer elemento de la colección, o `Nothing` si la colección está vacía.

## <a name="remarks"></a>Comentarios

 La propiedad <xref:System.Xml.Linq.XElement.Value%2A> facilita el acceso al valor del primer elemento de una colección de objetos <xref:System.Xml.Linq.XElement>. Esta propiedad comprueba primero si la colección contiene al menos un objeto. Si la colección está vacía, esta propiedad devuelve `Nothing`. De lo contrario, esta propiedad devuelve el valor de la <xref:System.Xml.Linq.XElement.Value%2A> propiedad del primer elemento de la colección.

> [!NOTE]
> Cuando se tiene acceso al valor de un atributo XML mediante el identificador '\@', el valor de atributo se devuelve como un `String` y no es necesario especificar explícitamente la propiedad <xref:System.Xml.Linq.XAttribute.Value%2A>.

 Para tener acceso a otros elementos de una colección, puede usar la propiedad de indizador de extensión XML. Para más información, consulte [extensión de la propiedad Indexer](extension-indexer-property.md).

## <a name="inheritance"></a>Herencia

 La mayoría de los usuarios no tendrá que implementar <xref:System.Collections.Generic.IEnumerable%601>y, por tanto, puede omitir esta sección.

 La propiedad <xref:System.Xml.Linq.XElement.Value%2A> es una propiedad de extensión para los tipos que implementan `IEnumerable(Of XElement)`. El enlace de esta propiedad de extensión es como el enlace de métodos de extensión: Si un tipo implementa una de las interfaces y define una propiedad con el nombre "Value", esa propiedad tiene prioridad sobre la propiedad de extensión. En otras palabras, esta propiedad de <xref:System.Xml.Linq.XElement.Value%2A> se puede invalidar definiendo una nueva propiedad en una clase que implementa `IEnumerable(Of XElement)`.

## <a name="example"></a>Ejemplo

 En el ejemplo siguiente se muestra cómo utilizar la propiedad <xref:System.Xml.Linq.XElement.Value%2A> para tener acceso al primer nodo de una colección de objetos <xref:System.Xml.Linq.XElement>. En el ejemplo se usa la propiedad del eje secundario para obtener la colección de todos los nodos secundarios denominados `phone` que se encuentran en el objeto `contact`.

 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]

 Este código muestra el siguiente texto:

 `Phone number: 206-555-0144`

## <a name="example"></a>Ejemplo

 En el ejemplo siguiente se muestra cómo obtener el valor de un atributo XML de una colección de objetos <xref:System.Xml.Linq.XAttribute>. En el ejemplo se usa la propiedad de eje de atributo para mostrar el valor del atributo `type` de todos los elementos `phone`.

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
