---
title: Value (Propiedad XML) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 9edf95c7cedced55ab2441baf51b7c2052e4654c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942986"
---
# <a name="xml-value-property-visual-basic"></a>Value (Propiedad XML) (Visual Basic)
Proporciona acceso al valor del primer elemento de una colección de <xref:System.Xml.Linq.XElement> objetos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
object.Value  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`object`|Necesario. Una colección de objetos <xref:System.Xml.Linq.XElement>.|  
  
## <a name="return-value"></a>Valor devuelto  
 Que contiene el valor del primer elemento de la colección o `Nothing` si la colección está vacía. `String`  
  
## <a name="remarks"></a>Comentarios  
 La <xref:System.Xml.Linq.XElement.Value%2A> propiedad facilita el acceso al valor del primer elemento de una colección de <xref:System.Xml.Linq.XElement> objetos. Esta propiedad comprueba primero si la colección contiene al menos un objeto. Si la colección está vacía, esta propiedad devuelve `Nothing`. De lo contrario, esta propiedad devuelve el valor <xref:System.Xml.Linq.XElement.Value%2A> de la propiedad del primer elemento de la colección.  
  
> [!NOTE]
> Cuando se tiene acceso al valor de un atributo XML mediante el\@identificador ' ', el valor del atributo se devuelve `String` como y no es necesario especificar explícitamente la <xref:System.Xml.Linq.XAttribute.Value%2A> propiedad.  
  
 Para tener acceso a otros elementos de una colección, puede usar la propiedad de indizador de extensión XML. Para más información, consulte [extensión](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)de la propiedad Indexer.  
  
## <a name="inheritance"></a>Herencia  
 La mayoría de los usuarios no tendrá <xref:System.Collections.Generic.IEnumerable%601>que implementar y, por tanto, puede omitir esta sección.  
  
 La <xref:System.Xml.Linq.XElement.Value%2A> propiedad es una propiedad de extensión para los tipos `IEnumerable(Of XElement)`que implementan. El enlace de esta propiedad de extensión es como el enlace de métodos de extensión: Si un tipo implementa una de las interfaces y define una propiedad con el nombre "Value", esa propiedad tiene prioridad sobre la propiedad de extensión. En otras palabras, esta <xref:System.Xml.Linq.XElement.Value%2A> propiedad se puede invalidar definiendo una nueva propiedad en una clase que `IEnumerable(Of XElement)`implementa.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar <xref:System.Xml.Linq.XElement.Value%2A> la propiedad para tener acceso al primer nodo de una <xref:System.Xml.Linq.XElement> colección de objetos. En el ejemplo se usa la propiedad del eje secundario para obtener la colección de todos `phone` los nodos secundarios denominados que están en el `contact` objeto.  
  
 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]  
  
 Este código muestra el siguiente texto:  
  
 `Phone number: 206-555-0144`  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo obtener el valor de un atributo XML de una colección <xref:System.Xml.Linq.XAttribute> de objetos. En el ejemplo se usa la propiedad de eje de atributo para mostrar `type` el valor del atributo para `phone` todos los elementos.  
  
 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]  
  
 Este código muestra el siguiente texto:  
  
 `home`  
  
 `work`  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [Propiedades del eje XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Métodos de extensión](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [Propiedad de indexador de extensión](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)
- [Propiedad del eje secundario XML](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [Propiedad del eje de atributo XML](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
