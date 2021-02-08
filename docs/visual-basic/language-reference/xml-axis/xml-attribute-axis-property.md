---
description: 'Más información acerca de: propiedad de eje de atributo XML (Visual Basic)'
title: XML Attribute Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
ms.openlocfilehash: 2085ef2151e7aef7c5642e0ba9ac2e6fa90bfd4e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795175"
---
# <a name="xml-attribute-axis-property-visual-basic"></a>Propiedad de eje para atributos XML (Visual Basic)

Proporciona acceso al valor de un atributo para un <xref:System.Xml.Linq.XElement> objeto o al primer elemento de una colección de <xref:System.Xml.Linq.XElement> objetos.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
object.@attribute  
' -or-  
object.@<attribute>  
```  
  
## <a name="parts"></a>Partes  

 `object`  
 Necesario. <xref:System.Xml.Linq.XElement>Objeto o colección de <xref:System.Xml.Linq.XElement> objetos.  
  
 .@  
 Necesario. Denota el inicio de una propiedad de eje de atributo.  
  
 <  
 Opcional. Denota el principio del nombre del atributo cuando `attribute` no es un identificador válido en Visual Basic.  
  
 `attribute`  
 Necesario. Nombre del atributo al que se va a tener acceso, con el formato [ `prefix` :] `name` .  
  
|Parte|Descripción|  
|----------|-----------------|  
|`prefix`|Opcional. Prefijo de espacio de nombres XML para el atributo. Debe ser un espacio de nombres XML global definido con una instrucción `Imports`.|  
|`name`|Necesario. Nombre del atributo local. Vea [nombres de atributos y elementos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Opcional. Denota el final del nombre del atributo cuando `attribute` no es un identificador válido en Visual Basic.  
  
## <a name="return-value"></a>Valor devuelto  

 Cadena que contiene el valor de `attribute` . Si el nombre de atributo no existe, `Nothing` se devuelve.  
  
## <a name="remarks"></a>Observaciones  

 Puede usar una propiedad de eje de atributo XML para tener acceso al valor de un atributo por nombre desde un <xref:System.Xml.Linq.XElement> objeto o desde el primer elemento de una colección de <xref:System.Xml.Linq.XElement> objetos. Puede recuperar un valor de atributo por nombre o agregar un nuevo atributo a un elemento especificando un nuevo nombre precedido por el identificador @.  
  
 Cuando se hace referencia a un atributo XML mediante el identificador @, el valor del atributo se devuelve como una cadena y no es necesario especificar explícitamente la <xref:System.Xml.Linq.XAttribute.Value%2A> propiedad.  
  
 Las reglas de nomenclatura para los atributos XML difieren de las reglas de nomenclatura para los identificadores de Visual Basic. Para obtener acceso a un atributo XML que tiene un nombre que no es un identificador de Visual Basic válido, incluya el nombre entre corchetes angulares ( \< and > ).  
  
## <a name="xml-namespaces"></a>Espacios de nombres XML  

 El nombre de una propiedad de eje de atributo solo puede usar prefijos de espacio de nombres XML declarados globalmente mediante la `Imports` instrucción. No puede utilizar prefijos de espacio de nombres XML declarados localmente dentro de literales de elemento XML. Para obtener más información, vea [instrucción Imports (espacio de nombres XML)](../statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo obtener los valores de los atributos XML denominados `type` de una colección de elementos XML que se denominan `phone` .  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 Este código muestra el siguiente texto:  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo crear atributos para un elemento XML mediante declaración, como parte del XML, y dinámicamente agregando un atributo a una instancia de un <xref:System.Xml.Linq.XElement> objeto. El `type` atributo se crea mediante declaración y el `owner` atributo se crea dinámicamente.  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 Este código muestra el siguiente texto:  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usa la sintaxis de corchetes angulares para obtener el valor del atributo XML denominado `number-type` , que no es un identificador válido en Visual Basic.  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 Este código muestra el siguiente texto:  
  
 `Phone type: work`  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML. A continuación, usa el prefijo del espacio de nombres para crear un literal XML y acceder al primer nodo secundario con el nombre completo " `ns:name` ".  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 Este código muestra el siguiente texto:  
  
 `Phone type: home`  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XElement>
- [Propiedades de eje XML](index.md)
- [Literales XML](../xml-literals/index.md)
- [Crear XML en Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Nombres de atributos y elementos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
