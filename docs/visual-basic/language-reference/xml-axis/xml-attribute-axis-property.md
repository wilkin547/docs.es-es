---
title: Propiedad de eje para atributos XML (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a286c70f57128d0406b3a300610fea5e1c44b32d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xml-attribute-axis-property-visual-basic"></a>Propiedad de eje para atributos XML (Visual Basic)
Proporciona acceso al valor de un atributo para un <xref:System.Xml.Linq.XElement> objeto o hasta el primer elemento de una colección de <xref:System.Xml.Linq.XElement> objetos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## <a name="parts"></a>Elementos  
 `object`  
 Obligatorio. Un <xref:System.Xml.Linq.XElement> objeto o una colección de <xref:System.Xml.Linq.XElement> objetos.  
  
 .@  
 Requerido. Denota el inicio de una propiedad de eje de atributo.  
  
 <  
 Opcional. Indica el principio del nombre del atributo cuando `attribute` no es un identificador válido en [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
 `attribute`  
 Obligatorio. Nombre del atributo para tener acceso a la forma [`prefix`:]`name`.  
  
|Parte|Descripción|  
|----------|-----------------|  
|`prefix`|Opcional. Prefijo de espacio de nombres XML para el atributo. Debe ser un espacio de nombres XML global definido con una instrucción `Imports`.|  
|`name`|Obligatorio. Nombre del atributo local. Vea [nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Opcional. Denota el final del nombre del atributo cuando `attribute` no es un identificador válido en [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
## <a name="return-value"></a>Valor devuelto  
 Una cadena que contiene el valor de `attribute`. Si no existe el nombre del atributo, `Nothing` se devuelve.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar una propiedad de eje de atributo XML para tener acceso al valor de un atributo por nombre desde un <xref:System.Xml.Linq.XElement> objeto o desde el primer elemento de una colección de <xref:System.Xml.Linq.XElement> objetos. Puede recuperar un valor de atributo por nombre o agregar un nuevo atributo a un elemento especificando un nombre nuevo precedido por el identificador @.  
  
 Cuando haga referencia a un atributo XML mediante el identificador @, se devuelve el valor de atributo como una cadena y no es necesario especificar explícitamente la <xref:System.Xml.Linq.XAttribute.Value%2A> propiedad.  
  
 Las reglas de nomenclatura para los atributos XML difieren de las reglas de nomenclatura [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] identificadores. Para obtener acceso a un atributo XML que tiene un nombre que no es un identificador válido de Visual Basic, ponga el nombre entre corchetes angulares (\< y >).  
  
## <a name="xml-namespaces"></a>Espacios de nombres XML  
 El nombre de una propiedad de eje de atributo puede usar únicamente prefijos espacios de nombres XML declarados globalmente mediante la `Imports` instrucción. No puede utilizar prefijos de espacio de nombres XML declarados localmente dentro de literales de elemento XML. Para obtener más información, consulte [instrucción Imports (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo obtener los valores de los atributos XML denominados `type` de una colección de elementos XML que se denomina `phone`.  
  
 [!code-vb[VbXMLSamples#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]  
  
 Este código muestra el siguiente texto:  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo crear atributos de un elemento XML tanto mediante declaración, como parte del código XML y dinámicamente mediante la adición de un atributo a una instancia de un <xref:System.Xml.Linq.XElement> objeto. El `type` atributo se crea mediante declaración y la `owner` atributo se crea de forma dinámica.  
  
 [!code-vb[VbXMLSamples#44](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]  
  
 Este código muestra el siguiente texto:  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza la sintaxis de corchetes angulares para obtener el valor del atributo XML denominado `number-type`, que no es un identificador válido en [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
 [!code-vb[VbXMLSamples#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]  
  
 Este código muestra el siguiente texto:  
  
 `Phone type: work`  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML. A continuación, utiliza el prefijo del espacio de nombres para crear un literal XML y obtener acceso al primer nodo secundario con el nombre completo "`ns:name`".  
  
 [!code-vb[VbXMLSamples#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]  
  
 Este código muestra el siguiente texto:  
  
 `Phone type: home`  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XElement>  
 [Propiedades del eje XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
