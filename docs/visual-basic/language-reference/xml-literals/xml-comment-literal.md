---
title: Literal de comentario XML (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralComment
dev_langs:
- VB
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 88cfb984be42345ae1e5c998cf82aa1415d2455e
ms.lasthandoff: 03/13/2017

---
# <a name="xml-comment-literal-visual-basic"></a>Literal de comentario XML (Visual Basic)
Un literal que representa un <xref:System.Xml.Linq.XComment>objeto.</xref:System.Xml.Linq.XComment>  
  
## <a name="syntax"></a>Sintaxis  
  
```  
<!-- content -->  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`<!--`|Obligatorio. Denota el inicio del comentario XML.|  
|`content`|Obligatorio. Texto que aparecerá en el comentario XML. No puede contener una serie de dos guiones (-) o finalizar con un guión adyacente a la etiqueta de cierre.|  
|`-->`|Obligatorio. Denota el final del comentario XML.|  
  
## <a name="return-value"></a>Valor devuelto  
 Un <xref:System.Xml.Linq.XComment>objeto.</xref:System.Xml.Linq.XComment>  
  
## <a name="remarks"></a>Comentarios  
 Los literales de comentario XML no contienen el contenido del documento; contienen información acerca del documento. La sección de comentario XML finaliza con la secuencia "-->". Esto implica los siguientes puntos:  
  
-   No puede usar una expresión incrustada en un literal de comentario XML porque los delimitadores de expresión incrustada son contenido de comentario XML válido.  
  
-   Secciones de comentario XML no se pueden anidar, ya que `content` no puede contener el valor "-->".  
  
 Puede asignar un literal de comentario XML a una variable o incluirlo en un literal de elemento XML.  
  
> [!NOTE]
>  Un literal XML puede abarcar varias líneas sin usar caracteres de continuación de línea. Esta característica le permite copiar el contenido de un documento XML y péguelo directamente en un [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programa.  
  
 El [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador convierte el literal de comentario XML a una llamada a la <xref:System.Xml.Linq.XComment.%23ctor%2A>constructor.</xref:System.Xml.Linq.XComment.%23ctor%2A>  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un comentario XML que contiene el texto "Esto es un comentario".  
  
 [!code-vb[VbXMLSamples&#9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XComment>   
 [Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
