---
description: 'Más información acerca de: literal de comentario XML (Visual Basic)'
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
ms.openlocfilehash: f44d2e132236d74d312910921fabb3a85afd82d6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768745"
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XComment>
- [Literal de elemento XML](xml-element-literal.md)
- [Literales XML](index.md)
- [Crear XML en Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
