---
title: Propiedad de eje descendiente XML (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyDescendantsAxis
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Baisc]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 434dc90c643381bdc27b2da54a7418e39bf15e98
ms.lasthandoff: 03/13/2017

---
# <a name="xml-descendant-axis-property-visual-basic"></a>Propiedad de eje descendiente XML Visual Basic)
Proporciona acceso a los descendientes de los siguientes: una <xref:System.Xml.Linq.XElement>objeto, un <xref:System.Xml.Linq.XDocument>(objeto), una colección de <xref:System.Xml.Linq.XElement>objetos o una colección de <xref:System.Xml.Linq.XDocument>objetos.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
object...<descendant>  
```  
  
## <a name="parts"></a>Elementos  
 `object`  
 Obligatorio. Un <xref:System.Xml.Linq.XElement>objeto, un <xref:System.Xml.Linq.XDocument>(objeto), una colección de <xref:System.Xml.Linq.XElement>objetos o una colección de <xref:System.Xml.Linq.XDocument>objetos.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>  
  
 ...<  
 Requerido. Denota el inicio de una propiedad de eje descendiente.  
  
 `descendant`  
 Obligatorio. Nombre de los nodos descendientes para tener acceso a la forma [`prefix``:`]`name`.  
  
|Parte|Descripción|  
|----------|-----------------|  
|`prefix`|Opcional. Prefijo de espacio de nombres XML para el nodo descendiente. Debe ser un espacio de nombres XML global que se define mediante una `Imports` instrucción.|  
|`name`|Obligatorio. Nombre local del nodo descendiente. Consulte [nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Obligatorio. Denota el final de una propiedad de eje descendiente.  
  
## <a name="return-value"></a>Valor devuelto  
 Una colección de <xref:System.Xml.Linq.XElement>objetos.</xref:System.Xml.Linq.XElement>  
  
## <a name="remarks"></a>Comentarios  
 Puede usar una propiedad de eje descendiente XML para obtener acceso a los nodos descendientes por nombre de un <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XDocument>objeto, o de una colección de <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XDocument>objetos.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> Utilice el XML `Value` propiedad para tener acceso al valor del primer nodo descendiente en la colección devuelta. Para obtener más información, consulte [propiedad Value de XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
 El [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador convierte las propiedades de eje descendiente en llamadas a la <xref:System.Xml.Linq.XContainer.Descendants%2A>método.</xref:System.Xml.Linq.XContainer.Descendants%2A>  
  
## <a name="xml-namespaces"></a>Espacios de nombres XML  
 El nombre de una propiedad de eje descendiente puede usar únicamente espacios de nombres XML declarados globalmente con la `Imports` instrucción. No puede utilizar espacios de nombres XML declarados localmente dentro de literales de elemento XML. Para obtener más información, consulte [instrucción Imports (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo tener acceso al valor del primer nodo descendiente denominado `name` y los valores de todos los nodos descendientes denominados `phone` desde el `contacts` objeto.  
  
 [!code-vb[VbXMLSamples&#25;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]  
  
 Este código muestra el siguiente texto:  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML. A continuación, usa el prefijo del espacio de nombres para crear un literal XML y obtener acceso al valor del primer nodo secundario con el nombre completo `ns:name`.  
  
 [!code-vb[26 de VbXMLSamples #](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]  
  
 Este código muestra el siguiente texto:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XElement>   
 [Propiedades de eje XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
