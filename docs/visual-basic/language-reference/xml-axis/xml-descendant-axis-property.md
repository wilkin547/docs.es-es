---
title: XML Descendant Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Basic]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
ms.openlocfilehash: b2bf524214fa8ecca215d50c198b23d127e3b400
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349444"
---
# <a name="xml-descendant-axis-property-visual-basic"></a>Propiedad de eje descendiente XML Visual Basic)

Proporciona acceso a los descendientes de los elementos siguientes: un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.

## <a name="syntax"></a>Sintaxis

```vb
object...<descendant>
```

## <a name="parts"></a>Elementos

`object` Obligatorio. Un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.

`...<` Obligatorio. Denota el inicio de una propiedad de eje descendiente.

`descendant` Obligatorio. Nombre de los nodos descendientes a los que se va a tener acceso, con el formato [`prefix:]name`.

|Parte|Descripción|
|----------|-----------------|
|`prefix`|Opcional. Prefijo de espacio de nombres XML para el nodo descendiente. Debe ser un espacio de nombres XML global que se define mediante una instrucción `Imports`.|
|`name`|Obligatorio. Nombre local del nodo descendiente. Vea [nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|

`>` Obligatorio. Denota el final de una propiedad de eje descendiente.

## <a name="return-value"></a>Valor devuelto

Una colección de objetos <xref:System.Xml.Linq.XElement>.

## <a name="remarks"></a>Comentarios

Puede usar una propiedad de eje descendiente XML para tener acceso a los nodos descendientes por nombre de un objeto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>, o de una colección de objetos <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>. Utilice la propiedad `Value` XML para tener acceso al valor del primer nodo descendiente de la colección devuelta. Para obtener más información, vea [propiedad valor XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).

El compilador Visual Basic convierte las propiedades de los ejes descendientes en llamadas al método <xref:System.Xml.Linq.XContainer.Descendants%2A>.

## <a name="xml-namespaces"></a>Espacios de nombres XML

El nombre de una propiedad de eje descendiente solo puede utilizar espacios de nombres XML declarados globalmente con la instrucción `Imports`. No puede utilizar espacios de nombres XML declarados localmente dentro de literales de elemento XML. Para obtener más información, vea [instrucción Imports (espacio de nombres XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo obtener acceso al valor del primer nodo descendiente denominado `name` y los valores de todos los nodos descendientes denominados `phone` del objeto `contacts`.

[!code-vb[VbXMLSamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#25)]

Este código muestra el siguiente texto:

`Name: Patrick Hines`

`Home Phone = 206-555-0144`

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML. A continuación, usa el prefijo del espacio de nombres para crear un literal XML y tener acceso al valor del primer nodo secundario con el nombre completo `ns:name`.

[!code-vb[VbXMLSamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples12.vb#26)]

Este código muestra el siguiente texto:

`Name: Patrick Hines`

## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XElement>
- [Propiedades del eje XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
