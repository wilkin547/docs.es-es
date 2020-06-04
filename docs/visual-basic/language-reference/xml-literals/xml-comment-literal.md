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
ms.openlocfilehash: 93c1346e54106b93f3932a494dea85d082ec994d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400220"
---
# <a name="xml-comment-literal-visual-basic"></a>Literal de comentario XML (Visual Basic)
Literal que representa un <xref:System.Xml.Linq.XComment> objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`<!--`|Obligatorio. Denota el inicio del comentario XML.|  
|`content`|Necesario. Texto que se va a mostrar en el comentario XML. No puede contener una serie de dos guiones (--) ni terminar con un guión adyacente a la etiqueta de cierre.|  
|`-->`|Necesario. Denota el final del comentario XML.|  
  
## <a name="return-value"></a>Valor devuelto  
 Objeto <xref:System.Xml.Linq.XComment>.  
  
## <a name="remarks"></a>Observaciones  
 Los literales de comentario XML no incluyen el contenido del documento; contienen información sobre el documento. La sección de comentarios XML finaliza con la secuencia "-->". Esto implica los puntos siguientes:  
  
- No se puede usar una expresión insertada en un literal de comentario XML porque los delimitadores de expresión incrustados son contenido de comentario XML válido.  
  
- Las secciones de comentarios XML no se pueden anidar porque `content` no pueden contener el valor "-->".  
  
 Puede asignar un literal de comentario XML a una variable o puede incluirlo en un literal de elemento XML.  
  
> [!NOTE]
> Un literal XML puede abarcar varias líneas sin utilizar caracteres de continuación de línea. Esta característica permite copiar contenido de un documento XML y pegarlo directamente en un programa Visual Basic.  
  
 El compilador Visual Basic convierte el literal de comentario XML en una llamada al <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un comentario XML que contiene el texto "This is a comment".  
  
 [!code-vb[VbXMLSamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#9)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Xml.Linq.XComment>
- [Literal de elemento XML](xml-element-literal.md)
- [Literales XML](index.md)
- [Crear XML en Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
