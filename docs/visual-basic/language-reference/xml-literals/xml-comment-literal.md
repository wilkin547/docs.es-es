---
title: Literal de comentario XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
ms.openlocfilehash: 96a7281cde546c3077cf15c625c6e09d2d0ee46f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624683"
---
# <a name="xml-comment-literal-visual-basic"></a>Literal de comentario XML (Visual Basic)
Un literal que representa un <xref:System.Xml.Linq.XComment> objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`<!--`|Obligatorio. Denota el inicio del comentario XML.|  
|`content`|Obligatorio. Texto que aparecerá en el comentario XML. No puede contener una serie de dos guiones (-) ni terminar con un guión adyacente a la etiqueta de cierre.|  
|`-->`|Obligatorio. Denota el final del comentario XML.|  
  
## <a name="return-value"></a>Valor devuelto  
 Un objeto <xref:System.Xml.Linq.XComment>.  
  
## <a name="remarks"></a>Comentarios  
 Los literales de comentario XML no contienen el contenido del documento; que contienen información sobre el documento. La sección de comentarios XML finaliza con la secuencia "-->". Esto implica los siguientes puntos:  
  
-   No se puede usar una expresión incrustada en un literal de comentario XML porque los delimitadores de expresión incrustada son contenido de comentario XML válido.  
  
-   Las secciones de comentario XML no se pueden anidar, porque `content` no puede contener el valor "-->".  
  
 Puede asignar un literal de comentario XML a una variable o incluirlo en un literal de elemento XML.  
  
> [!NOTE]
>  Un literal XML puede abarcar varias líneas sin usar caracteres de continuación de línea. Esta característica le permite copiar el contenido de un documento XML y péguelo directamente en un programa de Visual Basic.  
  
 El compilador de Visual Basic convierte el literal de comentario XML en una llamada a la <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea un comentario XML que contiene el texto "Este es un comentario".  
  
 [!code-vb[VbXMLSamples#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Xml.Linq.XComment>
- [Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
