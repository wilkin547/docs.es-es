---
description: 'Más información acerca de: propiedad de eje descendiente XML (Visual Basic)'
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
ms.openlocfilehash: c356d4d6f9a84755e9df171b26060fc6bfc4ead6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768784"
---
# <a name="xml-descendant-axis-property-visual-basic"></a>Propiedad de eje descendiente XML Visual Basic)

Proporciona acceso a los descendientes de los elementos siguientes: un <xref:System.Xml.Linq.XElement> objeto, un <xref:System.Xml.Linq.XDocument> objeto, una colección de <xref:System.Xml.Linq.XElement> objetos o una colección de <xref:System.Xml.Linq.XDocument> objetos.

## <a name="syntax"></a>Sintaxis

```vb
object...<descendant>
```

## <a name="parts"></a>Partes

`object` Obligatorio. Un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.

`...<` Obligatorio. Denota el inicio de una propiedad de eje descendiente.

`descendant` Obligatorio. Nombre de los nodos descendientes a los que se va a tener acceso, con el formato [ `prefix:]name` .

|Parte|Descripción|
|----------|-----------------|
|`prefix`|Opcional. Prefijo de espacio de nombres XML para el nodo descendiente. Debe ser un espacio de nombres XML global que se define mediante una `Imports` instrucción.|
|`name`|Necesario. Nombre local del nodo descendiente. Vea [nombres de atributos y elementos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|

`>` Obligatorio. Denota el final de una propiedad de eje descendiente.

## <a name="return-value"></a>Valor devuelto

Una colección de objetos <xref:System.Xml.Linq.XElement>.

## <a name="remarks"></a>Observaciones

Puede usar una propiedad de eje descendiente XML para tener acceso a los nodos descendientes por nombre desde un <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> objeto o, o desde una colección de <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> objetos o. Utilice la `Value` propiedad XML para tener acceso al valor del primer nodo descendiente de la colección devuelta. Para obtener más información, vea [propiedad valor XML](xml-value-property.md).

El compilador Visual Basic convierte las propiedades de los ejes descendientes en llamadas al <xref:System.Xml.Linq.XContainer.Descendants%2A> método.

## <a name="xml-namespaces"></a>Espacios de nombres XML

El nombre de una propiedad de eje descendiente solo puede utilizar espacios de nombres XML declarados globalmente con la `Imports` instrucción. No puede utilizar espacios de nombres XML declarados localmente dentro de literales de elemento XML. Para obtener más información, vea [instrucción Imports (espacio de nombres XML)](../statements/imports-statement-xml-namespace.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo obtener acceso al valor del primer nodo descendiente denominado `name` y los valores de todos los nodos descendientes denominados `phone` del `contacts` objeto.

[!code-vb[VbXMLSamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#25)]

Este código muestra el siguiente texto:

`Name: Patrick Hines`

`Home Phone = 206-555-0144`

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML. A continuación, usa el prefijo del espacio de nombres para crear un literal XML y tener acceso al valor del primer nodo secundario con el nombre completo `ns:name` .

[!code-vb[VbXMLSamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples12.vb#26)]

Este código muestra el siguiente texto:

`Name: Patrick Hines`

## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XElement>
- [Propiedades de eje XML](index.md)
- [Literales XML](../xml-literals/index.md)
- [Crear XML en Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Nombres de atributos y elementos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
