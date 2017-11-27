---
title: Propiedades de eje secundario XML (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlPropertyChildAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 89a59d00-985e-4f5c-b59f-29b47bad11cb
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ea4db763bbed651a01845b49395255586cb60113
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xml-child-axis-property-visual-basic"></a>Propiedades de eje secundario XML (Visual Basic)
Proporciona el acceso a los elementos secundarios de uno de los siguientes: un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
object.<child>  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`object`|Obligatorio. Un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.|  
|.<|Requerido. Denota el inicio de una propiedad de eje secundario.|  
|`child`|Obligatorio. Nombre de los nodos secundarios para obtener acceso a la forma [`prefix``:`]`name`.<br /><br /> -   `Prefix`-Opcional. Prefijo de espacio de nombres XML para el nodo secundario. Debe ser un espacio de nombres XML global definido con una instrucción `Imports`.<br />-   `Name`-Required. Nombre del nodo secundario local. Vea [nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
|>|Obligatorio. Denota el final de una propiedad de eje secundario.|  
  
## <a name="return-value"></a>Valor devuelto  
 Una colección de objetos <xref:System.Xml.Linq.XElement>.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar una propiedad de eje secundario XML para tener acceso a los nodos secundarios por nombre desde un objeto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>, o desde una colección de objetos <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>. Utilice la propiedad XML `Value` para tener acceso al valor del primer nodo secundario de la colección devuelta. Para obtener más información, consulte [propiedad Value de XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
 El [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilador convierte las propiedades de eje secundario en llamadas a la <xref:System.Xml.Linq.XContainer.Elements%2A> método.  
  
## <a name="xml-namespaces"></a>Espacios de nombres XML  
 El nombre de una propiedad de eje secundario puede usar únicamente prefijos de espacios de nombres XML declarados globalmente con la instrucción `Imports`. No puede utilizar prefijos de espacio de nombres XML declarados localmente dentro de literales de elemento XML. Para obtener más información, consulte [instrucción Imports (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo obtener acceso a los nodos secundarios llamados `phone` desde el objeto `contact`.  
  
 [!code-vb[VbXMLSamples#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_1.vb)]  
  
 Este código muestra el siguiente texto:  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo tener acceso a los nodos secundarios denominados `phone` desde la colección devuelta por la propiedad `contact` del eje secundario del objeto `contacts`.  
  
 [!code-vb[VbXMLSamples#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_2.vb)]  
  
 Este código muestra el siguiente texto:  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML. A continuación, se usa el prefijo del espacio de nombres para crear un literal XML y obtener acceso al primer nodo secundario con el nombre completo `ns:name`.  
  
 [!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_3.vb)]  
  
 Este código muestra el siguiente texto:  
  
 `Patrick Hines`  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XElement>  
 [Propiedades del eje XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
