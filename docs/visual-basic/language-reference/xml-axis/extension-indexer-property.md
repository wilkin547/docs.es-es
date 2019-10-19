---
title: Propiedad de indizador de extensión (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: 660cebadc78d260350f2849f7f4926f9cef7c8d2
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582185"
---
# <a name="extension-indexer-property-visual-basic"></a>Propiedad de indizador de extensión (Visual Basic)
Proporciona acceso a los elementos individuales de una recopilación.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
object(index)  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|de esquema JSON|  
|---|---|  
|`object`|Requerido. Colección consultable. Es decir, una colección que implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.|  
|(|Requerido. Denota el inicio de la propiedad de indizador.|  
|`index`|Requerido. Expresión de tipo entero que especifica la posición de base cero de un elemento de la colección.|  
|)|Requerido. Denota el final de la propiedad de indizador.|  
  
## <a name="return-value"></a>Valor devuelto  
 Objeto de la ubicación especificada en la colección, o `Nothing` si el índice está fuera del intervalo.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar la propiedad de indizador de extensión para tener acceso a los elementos individuales de una colección. Esta propiedad de indizador se utiliza normalmente en la salida de las propiedades del eje XML. Las propiedades XML secundario y del eje descendiente XML devuelven colecciones de objetos <xref:System.Xml.Linq.XElement> o un valor de atributo.  
  
 El compilador Visual Basic convierte las propiedades de indizador de extensión en llamadas al método `ElementAtOrDefault`. A diferencia de un indizador de matriz, el método `ElementAtOrDefault` devuelve `Nothing` si el índice está fuera del intervalo. Este comportamiento es útil cuando no se puede determinar fácilmente el número de elementos de una colección.  
  
 Esta propiedad de indizador es como una propiedad de extensión para las colecciones que implementan <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>: solo se usa si la colección no tiene un indizador o una propiedad predeterminada.  
  
 Para tener acceso al valor del primer elemento de una colección de objetos <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute>, puede usar la propiedad `Value` XML. Para obtener más información, vea [propiedad valor XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar el indizador de extensión para tener acceso al segundo nodo secundario de una colección de objetos <xref:System.Xml.Linq.XElement>. Se tiene acceso a la colección mediante la propiedad del eje secundario, que obtiene todos los elementos secundarios denominados `phone` en el objeto `contact`.  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 Este código muestra el siguiente texto:  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XElement>
- [Propiedades del eje XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Propiedad de valor XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
