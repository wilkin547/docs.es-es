---
title: "Propiedad de indizador de extensión (Visual Basic) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyExtensionIndexer
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
caps.latest.revision: 22
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
ms.openlocfilehash: 25f434a5b5f8caf013ad5f778897e4e98e3d825d
ms.lasthandoff: 03/13/2017

---
# <a name="extension-indexer-property-visual-basic"></a>Propiedad de indizador de extensión (Visual Basic)
Proporciona acceso a los elementos individuales de una recopilación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
object(index)  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`object`|Obligatorio. Una colección consultable. Es decir, una colección que implementa <xref:System.Collections.Generic.IEnumerable%601>o <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601>|  
|(|Requerido. Denota el inicio de la propiedad de indizador.|  
|`index`|Obligatorio. Una expresión entera que especifica la posición de base cero de un elemento de la colección.|  
|)|Requerido. Denota el final de la propiedad de indizador.|  
  
## <a name="return-value"></a>Valor devuelto  
 El objeto de la ubicación especificada en la colección, o `Nothing` si el índice está fuera del intervalo.  
  
## <a name="remarks"></a>Comentarios  
 Puede utilizar la propiedad de indizador de extensión para obtener acceso a los elementos individuales de una colección. Esta propiedad de indizador se usa normalmente en la salida de las propiedades de eje XML. El elemento secundario XML y propiedades de eje descendiente XML devuelven colecciones de <xref:System.Xml.Linq.XElement>objetos o un valor de atributo.</xref:System.Xml.Linq.XElement>  
  
 El [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador convierte las propiedades de indizador de extensión para las llamadas a la`ElementAtOrDefault` (método). A diferencia de un indizador de matriz, el`ElementAtOrDefault` método devuelve `Nothing` si el índice está fuera del intervalo. Este comportamiento resulta útil cuando no se puede determinar fácilmente el número de elementos de una colección.  
  
 Esta propiedad de indizador es similar a una propiedad de extensión para las colecciones que implementan <xref:System.Collections.Generic.IEnumerable%601>o <xref:System.Linq.IQueryable%601>: se usa sólo si la colección no tiene un indizador o una propiedad predeterminada.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601>  
  
 Para obtener acceso al valor del primer elemento de una colección de <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XAttribute>objetos, puede utilizar el archivo XML `Value` propiedad.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> Para obtener más información, consulte [propiedad Value de XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar el indizador de extensión para tener acceso el segundo nodo secundario de una colección de <xref:System.Xml.Linq.XElement>objetos.</xref:System.Xml.Linq.XElement> Se tiene acceso a la colección utilizando la propiedad de eje secundario, que obtiene todos los elementos secundarios denominados `phone` en la `contact` objeto.  
  
 [!code-vb[VbXMLSamples&#24;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 Este código muestra el siguiente texto:  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XElement>   
 [Propiedades de eje XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Propiedad de valor XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
