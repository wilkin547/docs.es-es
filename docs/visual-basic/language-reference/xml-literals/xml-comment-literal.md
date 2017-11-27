---
title: Literal de comentario XML (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 36be34ac22cfe926a2eea946f5e4c4eb534de696
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
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
 Los literales de comentario XML no contienen el contenido del documento; que contienen información sobre el documento. La sección de comentario XML finaliza con la secuencia "-->". Esto implica lo siguiente:  
  
-   No se puede usar una expresión incrustada en un literal de comentario XML porque los delimitadores de expresión incrustada son contenido de comentario XML válido.  
  
-   Secciones de comentario XML no se pueden anidar, porque `content` no puede contener el valor "-->".  
  
 Puede asignar un literal de comentario XML a una variable o incluirlo en un literal de elemento XML.  
  
> [!NOTE]
>  Un literal XML puede abarcar varias líneas sin usar caracteres de continuación de línea. Esta característica le permite copiar el contenido de un documento XML y pegarlos directamente en un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programa.  
  
 El [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilador convierte el literal de comentario XML a una llamada a la <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un comentario XML que contiene el texto "Esto es un comentario".  
  
 [!code-vb[VbXMLSamples#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XComment>  
 [Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
