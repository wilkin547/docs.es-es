---
title: "Propiedad de indizador de extensión (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 99d14b6e54a59ffc904a9e786c22498d23ee8ab6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
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
|`object`|Obligatorio. Una colección consultable. Es decir, una colección que implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.|  
|(|Requerido. Denota el inicio de la propiedad de indizador.|  
|`index`|Obligatorio. Expresión entera que especifica la posición de base cero de un elemento de la colección.|  
|)|Requerido. Denota el final de la propiedad de indizador.|  
  
## <a name="return-value"></a>Valor devuelto  
 El objeto desde la ubicación especificada en la colección, o `Nothing` si el índice está fuera del intervalo.  
  
## <a name="remarks"></a>Comentarios  
 Puede utilizar la propiedad de indizador de extensión para obtener acceso a los elementos individuales de una colección. Esta propiedad de indizador se suele usar en la salida de las propiedades de eje XML. El elemento secundario XML y propiedades de eje descendiente XML devuelven colecciones de <xref:System.Xml.Linq.XElement> objetos o un valor de atributo.  
  
 El [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilador convierte las propiedades de indizador de extensión en llamadas a la `ElementAtOrDefault` método. A diferencia de un indizador de matriz, el `ElementAtOrDefault` método `Nothing` si el índice está fuera del intervalo. Este comportamiento es útil cuando no se puede determinar fácilmente el número de elementos de una colección.  
  
 Esta propiedad de indizador es similar a una propiedad de extensión para las colecciones que implementan <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>: se utiliza sólo si la colección no tiene un indizador o una propiedad predeterminada.  
  
 Para obtener acceso al valor del primer elemento de una colección de <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute> objetos, puede utilizar el código XML `Value` propiedad. Para obtener más información, consulte [propiedad Value de XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar el indizador de extensión para tener acceso al segundo nodo secundario en una colección de <xref:System.Xml.Linq.XElement> objetos. Se tiene acceso a la colección utilizando la propiedad de eje secundario, que obtiene todos los elementos secundarios llamados `phone` en la `contact` objeto.  
  
 [!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 Este código muestra el siguiente texto:  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XElement>  
 [Propiedades del eje XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Propiedad de valor XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
