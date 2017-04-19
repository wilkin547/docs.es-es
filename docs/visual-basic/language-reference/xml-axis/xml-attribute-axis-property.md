---
title: Propiedad Axis para atributo XML (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyAttributeAxis
dev_langs:
- VB
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 94211f7c951976426ba17e73df214444a6c227b4
ms.lasthandoff: 03/13/2017

---
# <a name="xml-attribute-axis-property-visual-basic"></a>Propiedad de eje para atributos XML (Visual Basic)
Proporciona acceso al valor de un atributo para un <xref:System.Xml.Linq.XElement>objeto o en el primer elemento de una colección de <xref:System.Xml.Linq.XElement>objetos.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement>  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## <a name="parts"></a>Elementos  
 `object`  
 Obligatorio. Un <xref:System.Xml.Linq.XElement>objeto o una colección de <xref:System.Xml.Linq.XElement>objetos.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement>  
  
 .@  
 Requerido. Denota el inicio de una propiedad de eje de atributo.  
  
 <  
 Opcional. Denota el principio del nombre del atributo cuando `attribute` no es un identificador válido en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 `attribute`  
 Obligatorio. Nombre del atributo para obtener acceso a la forma [`prefix`:]`name`.  
  
|Parte|Descripción|  
|----------|-----------------|  
|`prefix`|Opcional. Prefijo de espacio de nombres XML para el atributo. Debe ser un espacio de nombres XML global definido con una instrucción `Imports`.|  
|`name`|Obligatorio. Nombre local del atributo. Consulte [nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Opcional. Denota el final del nombre del atributo cuando `attribute` no es un identificador válido en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## <a name="return-value"></a>Valor devuelto  
 Una cadena que contiene el valor de `attribute`. Si no existe el nombre del atributo, `Nothing` se devuelve.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar una propiedad de eje de atributo XML para tener acceso al valor de un atributo por nombre desde un <xref:System.Xml.Linq.XElement>objeto o desde el primer elemento de una colección de <xref:System.Xml.Linq.XElement>objetos.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement> Puede recuperar un valor de atributo por nombre o agregar un nuevo atributo a un elemento especificando un nombre nuevo precedido por el identificador @.  
  
 Cuando haga referencia a un atributo XML mediante el identificador @, el valor del atributo se devuelve como una cadena y no es necesario especificar explícitamente el <xref:System.Xml.Linq.XAttribute.Value%2A>propiedad.</xref:System.Xml.Linq.XAttribute.Value%2A>  
  
 Las reglas de nomenclatura para los atributos XML difieren de las reglas de nomenclatura [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] identificadores. Para obtener acceso a un atributo XML que tiene un nombre que no es un identificador válido de Visual Basic, ponga el nombre entre corchetes angulares (\< y >).  
  
## <a name="xml-namespaces"></a>Espacios de nombres XML  
 El nombre de una propiedad de eje de atributo puede usar únicamente prefijos espacios de nombres XML declarados globalmente mediante la `Imports` instrucción. No puede utilizar prefijos de espacio de nombres XML declarados localmente dentro de literales de elemento XML. Para obtener más información, consulte [instrucción Imports (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo obtener los valores de los atributos XML denominados `type` de una colección de elementos XML que se denomina `phone`.  
  
 [!code-vb[VbXMLSamples&#12;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]  
  
 Este código muestra el siguiente texto:  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo crear atributos de un elemento XML tanto mediante declaración, como parte del XML y dinámicamente agregando un atributo a una instancia de un <xref:System.Xml.Linq.XElement>objeto.</xref:System.Xml.Linq.XElement> El `type` atributo se crea mediante declaración y la `owne`r atributo se crea dinámicamente.  
  
 [!code-vb[VbXMLSamples&#44;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]  
  
 Este código muestra el siguiente texto:  
  
```  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza la sintaxis de corchetes angulares para obtener el valor del atributo XML denominado `number-type`, que no es un identificador válido en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 [!code-vb[VbXMLSamples&#13;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]  
  
 Este código muestra el siguiente texto:  
  
 `Phone type: work`  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML. A continuación, usa el prefijo del espacio de nombres para crear un literal XML y obtener acceso al primer nodo secundario con el nombre completo "`ns:name`".  
  
 [!code-vb[VbXMLSamples&#14;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]  
  
 Este código muestra el siguiente texto:  
  
 `Phone type: home`  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XElement>   
 [Propiedades de eje XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
