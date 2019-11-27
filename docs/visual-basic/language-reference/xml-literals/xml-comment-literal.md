---
title: Literal de comentario XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
ms.openlocfilehash: 8d9db66aabe344bd5c8f9a92ac8618b7bc1abb43
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349400"
---
# <a name="xml-comment-literal-visual-basic"></a>Literal de comentario XML (Visual Basic)
Literal que representa un objeto <xref:System.Xml.Linq.XComment>.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`<!--`|Obligatorio. Denota el inicio del comentario XML.|  
|`content`|Obligatorio. Texto que se va a mostrar en el comentario XML. No puede contener una serie de dos guiones (--) ni terminar con un guión adyacente a la etiqueta de cierre.|  
|`-->`|Obligatorio. Denota el final del comentario XML.|  
  
## <a name="return-value"></a>Valor devuelto  
 Un objeto <xref:System.Xml.Linq.XComment>.  
  
## <a name="remarks"></a>Comentarios  
 Los literales de comentario XML no incluyen el contenido del documento; contienen información sobre el documento. La sección de comentarios XML finaliza con la secuencia "-->". Esto implica los puntos siguientes:  
  
- No se puede usar una expresión insertada en un literal de comentario XML porque los delimitadores de expresión incrustados son contenido de comentario XML válido.  
  
- Las secciones de comentarios XML no se pueden anidar porque `content` no pueden contener el valor "-->".  
  
 Puede asignar un literal de comentario XML a una variable o puede incluirlo en un literal de elemento XML.  
  
> [!NOTE]
> Un literal XML puede abarcar varias líneas sin utilizar caracteres de continuación de línea. Esta característica permite copiar contenido de un documento XML y pegarlo directamente en un programa Visual Basic.  
  
 El compilador Visual Basic convierte el literal de comentario XML en una llamada al constructor <xref:System.Xml.Linq.XComment.%23ctor%2A>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un comentario XML que contiene el texto "This is a comment".  
  
 [!code-vb[VbXMLSamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#9)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XComment>
- [Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
