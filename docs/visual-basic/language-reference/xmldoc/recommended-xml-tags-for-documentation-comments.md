---
title: "Etiquetas XML recomendadas para comentarios de documentación (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlDocComment
dev_langs:
- VB
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
caps.latest.revision: 14
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
ms.openlocfilehash: c6a47c12bc24864ef6ac9f80054becad98ec97f1
ms.lasthandoff: 03/13/2017

---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a>Etiquetas XML recomendadas para comentarios de documentación (Visual Basic)
El [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador puede procesar los comentarios de documentación en el código en un archivo XML. Puede utilizar herramientas adicionales para procesar el archivo XML en la documentación.  
  
 Los comentarios XML están permitidos en construcciones de código, como tipos y miembros de tipo. Para los tipos parciales, sólo una parte del tipo puede tener comentarios XML, aunque no hay ninguna restricción sobre los comentarios de sus miembros.  
  
> [!NOTE]
>  Los comentarios de documentación no se puede aplicar a espacios de nombres. El motivo es que un espacio de nombres puede abarcar varios ensamblados y no todos los ensamblados tienen que cargarse al mismo tiempo.  
  
 El compilador procesa cualquier etiqueta válida en XML. Las siguientes etiquetas proporcionan funcionalidad utiliza en la documentación de usuario.  
  
||||  
|---|---|---|  
|[\<c >](../../../visual-basic/language-reference/xmldoc/c.md)|[\<código >](../../../visual-basic/language-reference/xmldoc/code.md)|[\<ejemplo >](../../../visual-basic/language-reference/xmldoc/example.md)|  
|[\<excepción >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup>|[\<incluir >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup>|[\<list>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[\<para >](../../../visual-basic/language-reference/xmldoc/para.md)|[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup>|[\<paramref >](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|[\<permiso >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup>|[\<comentarios >](../../../visual-basic/language-reference/xmldoc/remarks.md)|[\<Devuelve >](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup>|[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup>|[\<Resumen >](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup>|[\<valor >](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 (<sup>1</sup> el compilador comprueba la sintaxis.)  
  
> [!NOTE]
>  Si desea que aparezcan en el texto de un comentario de documentación corchetes angulares, utilice `<` y `>`. Por ejemplo, la cadena `"<text in angle brackets>"` aparecerá como `<text in angle``brackets>`.  
  
## <a name="see-also"></a>Vea también  
 [Documentar el código con XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)   
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)   
 [Crear documentación XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
