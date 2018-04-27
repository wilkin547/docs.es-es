---
title: Propiedad de indizador de extensión (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6bcb19388a9449a76eed5689b12fb95c5a4fb8de
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
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
|`object`|Requerido. Una colección consultable. Es decir, una colección que implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.|  
|(|Requerido. Denota el inicio de la propiedad de indizador.|  
|`index`|Requerido. Expresión entera que especifica la posición de base cero de un elemento de la colección.|  
|)|Requerido. Denota el final de la propiedad de indizador.|  
  
## <a name="return-value"></a>Valor devuelto  
 El objeto desde la ubicación especificada en la colección, o `Nothing` si el índice está fuera del intervalo.  
  
## <a name="remarks"></a>Comentarios  
 Puede utilizar la propiedad de indizador de extensión para obtener acceso a los elementos individuales de una colección. Esta propiedad de indizador se suele usar en la salida de las propiedades de eje XML. El elemento secundario XML y propiedades de eje descendiente XML devuelven colecciones de <xref:System.Xml.Linq.XElement> objetos o un valor de atributo.  
  
 El compilador de Visual Basic convierte las propiedades de indizador de extensión para las llamadas a la `ElementAtOrDefault` método. A diferencia de un indizador de matriz, el `ElementAtOrDefault` método `Nothing` si el índice está fuera del intervalo. Este comportamiento es útil cuando no se puede determinar fácilmente el número de elementos de una colección.  
  
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
