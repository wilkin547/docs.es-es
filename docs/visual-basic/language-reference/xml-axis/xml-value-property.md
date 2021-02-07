---
description: 'Más información acerca de: propiedad Value de XML (Visual Basic)'
title: Propiedad de valor XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 49762c1fcc0059472a5be11726aa344a001807ea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768771"
---
# <a name="xml-value-property-visual-basic"></a>Value (Propiedad XML) (Visual Basic)

Proporciona acceso al valor del primer elemento de una colección de <xref:System.Xml.Linq.XElement> objetos.

## <a name="syntax"></a>Sintaxis

```vb
object.Value
```

## <a name="parts"></a>Partes

|Término|Definición|  
|---|---|  
|`object`|Obligatorio. Una colección de objetos <xref:System.Xml.Linq.XElement>.|  

## <a name="return-value"></a>Valor devuelto

 `String`Que contiene el valor del primer elemento de la colección o `Nothing` si la colección está vacía.

## <a name="remarks"></a>Observaciones

 La <xref:System.Xml.Linq.XElement.Value%2A> propiedad facilita el acceso al valor del primer elemento de una colección de <xref:System.Xml.Linq.XElement> objetos. Esta propiedad comprueba primero si la colección contiene al menos un objeto. Si la colección está vacía, esta propiedad devuelve `Nothing` . De lo contrario, esta propiedad devuelve el valor de la <xref:System.Xml.Linq.XElement.Value%2A> propiedad del primer elemento de la colección.

> [!NOTE]
> Cuando se tiene acceso al valor de un atributo XML mediante el \@ identificador ' ', el valor del atributo se devuelve como `String` y no es necesario especificar explícitamente la <xref:System.Xml.Linq.XAttribute.Value%2A> propiedad.

 Para tener acceso a otros elementos de una colección, puede usar la propiedad de indizador de extensión XML. Para más información, consulte [extensión de la propiedad Indexer](extension-indexer-property.md).

## <a name="inheritance"></a>Herencia

 La mayoría de los usuarios no tendrá que implementar <xref:System.Collections.Generic.IEnumerable%601> y, por tanto, puede omitir esta sección.

 La <xref:System.Xml.Linq.XElement.Value%2A> propiedad es una propiedad de extensión para los tipos que implementan `IEnumerable(Of XElement)` . El enlace de esta propiedad de extensión es como el enlace de métodos de extensión: Si un tipo implementa una de las interfaces y define una propiedad con el nombre "Value", esa propiedad tiene prioridad sobre la propiedad de extensión. En otras palabras, esta <xref:System.Xml.Linq.XElement.Value%2A> propiedad se puede invalidar definiendo una nueva propiedad en una clase que implementa `IEnumerable(Of XElement)` .

## <a name="example"></a>Ejemplo

 En el ejemplo siguiente se muestra cómo utilizar la <xref:System.Xml.Linq.XElement.Value%2A> propiedad para tener acceso al primer nodo de una colección de <xref:System.Xml.Linq.XElement> objetos. En el ejemplo se usa la propiedad del eje secundario para obtener la colección de todos los nodos secundarios denominados `phone` que están en el `contact` objeto.

 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]

 Este código muestra el siguiente texto:

 `Phone number: 206-555-0144`

## <a name="example"></a>Ejemplo

 En el ejemplo siguiente se muestra cómo obtener el valor de un atributo XML de una colección de <xref:System.Xml.Linq.XAttribute> objetos. En el ejemplo se usa la propiedad de eje de atributo para mostrar el valor del `type` atributo para todos los `phone` elementos.

 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]

 Este código muestra el siguiente texto:

 ```console
 home
 work
```

## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [Propiedades de eje XML](index.md)
- [Literales XML](../xml-literals/index.md)
- [Crear XML en Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Métodos de extensión](../../programming-guide/language-features/procedures/extension-methods.md)
- [Propiedad de indexador de extensión](extension-indexer-property.md)
- [XML Child Axis Property](xml-child-axis-property.md)
- [XML Attribute Axis Property](xml-attribute-axis-property.md)
