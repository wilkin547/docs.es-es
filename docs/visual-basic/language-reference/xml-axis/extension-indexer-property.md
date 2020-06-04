---
title: Propiedad de indexador de extensión
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: c91061d49e22e648b7bf75a812071b352793abcb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401347"
---
# <a name="extension-indexer-property-visual-basic"></a>Propiedad de indizador de extensión (Visual Basic)
Proporciona acceso a los elementos individuales de una recopilación.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
object(index)  
```  
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`object`|Obligatorio. Colección consultable. Es decir, una colección que implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601> .|  
|(|Necesario. Denota el inicio de la propiedad de indizador.|  
|`index`|Necesario. Expresión de tipo entero que especifica la posición de base cero de un elemento de la colección.|  
|)|Necesario. Denota el final de la propiedad de indizador.|  
  
## <a name="return-value"></a>Valor devuelto  
 Objeto de la ubicación especificada en la colección o `Nothing` si el índice está fuera del intervalo.  
  
## <a name="remarks"></a>Observaciones  
 Puede usar la propiedad de indizador de extensión para tener acceso a los elementos individuales de una colección. Esta propiedad de indizador se utiliza normalmente en la salida de las propiedades del eje XML. Las propiedades XML secundario y del eje descendiente XML devuelven colecciones de <xref:System.Xml.Linq.XElement> objetos o un valor de atributo.  
  
 El compilador Visual Basic convierte las propiedades de indizador de extensión en llamadas al `ElementAtOrDefault` método. A diferencia de un indizador de matriz, el `ElementAtOrDefault` método devuelve `Nothing` si el índice está fuera del intervalo. Este comportamiento es útil cuando no se puede determinar fácilmente el número de elementos de una colección.  
  
 Esta propiedad de indizador es como una propiedad de extensión para las colecciones que implementan <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601> : solo se usa si la colección no tiene un indizador o una propiedad predeterminada.  
  
 Para tener acceso al valor del primer elemento de una colección de <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XAttribute> objetos o, puede usar la propiedad XML `Value` . Para obtener más información, vea [propiedad valor XML](xml-value-property.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar el indizador de extensión para tener acceso al segundo nodo secundario de una colección de <xref:System.Xml.Linq.XElement> objetos. Se tiene acceso a la colección mediante la propiedad del eje secundario, que obtiene todos los elementos secundarios denominados `phone` en el `contact` objeto.  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 Este código muestra el siguiente texto:  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Xml.Linq.XElement>
- [Propiedades de eje XML](index.md)
- [Literales XML](../xml-literals/index.md)
- [Crear XML en Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Propiedad de valor XML](xml-value-property.md)
