---
title: "Comentarios en código (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Uncomment button
- REM statement
- comments, in code
- comments, Visual Basic code
- Comment button
- buttons, Uncomment
- buttons, Comment
- code comments, Visual Basic
- Visual Basic code, comments
- comments
- code comments
ms.assetid: 90136fba-22eb-49f9-ba81-63db629b4a47
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 9663d83903ba2f9dcf93ecb5c293ac479e7dc175
ms.lasthandoff: 03/13/2017

---
# <a name="comments-in-code-visual-basic"></a>Comentarios en el código (Visual Basic)
Cuando lea ejemplos de código, encontrará el símbolo de comentario (`'`). Este símbolo solicita la [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador para pasar por alto el texto que aparece a continuación o el *comentario*. Los comentarios son notas cortas explicativas que se agregan al código para aportar mayor información a las personas que lo lean.  
  
 Una buena práctica de programación consiste en comenzar todos los procedimientos con un comentario breve que describe las características funcionales del procedimiento (lo que hace). Esto ayuda al desarrollador y a los que puedan examinar el código. Debería separar los detalles de implementación (cómo lo hace el procedimiento) de los comentarios que describen las características funcionales. Al incluir detalles de implementación en la descripción, recuerde actualizarlos en el momento de actualizar la función.  
  
 Los comentarios pueden ir a continuación de una instrucción en la misma línea, o pueden ocupar una línea completa. Ambas opciones quedan reflejadas en el código siguiente.  
  
 [!code-vb[VbVbcnConventions Nº&16;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_1.vb)]  
  
 Si el comentario necesita más de una línea, utilice el símbolo de comentario en cada línea, como se muestra en el siguiente ejemplo:  
  
 [!code-vb[VbVbcnConventions&#17;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_2.vb)]  
  
## <a name="commenting-guidelines"></a>Instrucciones sobre los comentarios  
 La tabla siguiente proporciona directrices generales sobre los tipos de comentarios que pueden preceder una sección de código. Se trata únicamente de sugerencias, ya que [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] no tiene reglas obligatorias para agregar comentarios. Escriba lo que considere más conveniente, para uso propio o para cualquier otra persona que lea el código.  
  
|||  
|---|---|  
|Tipo de comentario|Descripción del comentario|  
|Finalidad|Describe qué hace el procedimiento (no cómo lo hace).|  
|Suposiciones|Enumera cada variable externa, control, archivo abierto u otro elemento al cual el procedimiento tenga acceso.|  
|Efectos|Enumera cada variable externa, control o archivo que esté afectado, y el efecto que tienen (únicamente si no es evidente).|  
|Entradas|Especifica el propósito del argumento.|  
|Valores devueltos|Explica los valores que devuelve el procedimiento|  
  
 Recuerde los siguientes puntos:  
  
-   Cada declaración de variable importante debe incluir un comentario anterior que describa el uso de la variable que se declara.  
  
-   Las variables, controles y procedimientos deben tener un nombre lo suficientemente claro para asegurar que el uso de comentarios sólo sea necesario para detalles de implementación compleja.  
  
-   Después de la secuencia de continuación de línea no puede escribirse un comentario en la misma línea.  
  
 Puede agregar o quitar símbolos de comentario de un bloque de código seleccionando una o más líneas de código y eligiendo la **comentario** (![VisualBasicWinAppCodeEditorCommentButton](../../../visual-basic/programming-guide/program-structure/media/vacommentbutton.gif "vaCommentButton")) y **sin comentarios** (![VisualStudioWinAppProjectUncommentButton](../../../visual-basic/programming-guide/program-structure/media/vauncommentbutton.gif "vaUncommentButton")) los botones en la **editar** barra de herramientas.  
  
> [!NOTE]
>  También puede agregar comentarios al código poniendo la palabra clave `REM` antes del texto. Sin embargo, el `'` símbolo y el **comentario**/**sin comentarios** botones son más fáciles de utilizar y requieren menos espacio y memoria.  
  
## <a name="see-also"></a>Vea también  
 [Documentar el código con comentarios XML](http://msdn.microsoft.com/magazine/dd722812.aspx)   
 [Cómo: crear documentación XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)   
 [Etiquetas de comentario XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)   
 [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [REM (instrucción)](../../../visual-basic/language-reference/statements/rem-statement.md)
