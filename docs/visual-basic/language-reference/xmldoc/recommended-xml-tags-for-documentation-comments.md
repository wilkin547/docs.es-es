---
title: Etiquetas XML recomendadas para comentarios de documentación (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: 8f27a892117980e89fa7143b7e49551b9e8703f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604430"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a>Etiquetas XML recomendadas para comentarios de documentación (Visual Basic)
El compilador de Visual Basic puede procesar los comentarios de documentación en el código en un archivo XML. Puede utilizar herramientas adicionales para procesar el archivo XML en la documentación.  
  
 Comentarios XML están permitidos en construcciones de código, como tipos y miembros de tipo. Para los tipos parciales, solo una parte del tipo puede tener comentarios XML, aunque no hay ninguna restricción sobre la creación de comentarios de sus miembros.  
  
> [!NOTE]
>  Los comentarios de documentación no se puede aplicar a espacios de nombres. El motivo es que un espacio de nombres puede abarcar varios ensamblados y no todos los ensamblados tienen que cargarse al mismo tiempo.  
  
 El compilador procesa cualquier etiqueta XML válido. Las siguientes etiquetas proporcionan funcionalidad utilizada en la documentación de usuario.  
  
||||  
|---|---|---|  
|[\<c>](../../../visual-basic/language-reference/xmldoc/c.md)|[\<code>](../../../visual-basic/language-reference/xmldoc/code.md)|[\<example>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|[\<excepción >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup>|[\<Incluir >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup>|[\<list>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[\<para>](../../../visual-basic/language-reference/xmldoc/para.md)|[\<param >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup>|[\<paramref>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|[\<permiso >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup>|[\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|[\<Consulte >](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup>|[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup>|[\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup>|[\<value>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 (<sup>1</sup> el compilador comprueba la sintaxis.)  
  
> [!NOTE]
>  Si desea que aparezcan en el texto de un comentario de documentación corchetes angulares, utilice `<` y `>`. Por ejemplo, la cadena `"<text in angle brackets>"` aparecerá como `<text in angle``brackets>`.  
  
## <a name="see-also"></a>Vea también  
 [Documentar el código con XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [Crear documentación XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
