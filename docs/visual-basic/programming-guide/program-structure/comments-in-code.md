---
title: Comentarios en el código (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Uncomment button
- REM statement [Visual Basic]
- comments [Visual Basic], in code
- comments [Visual Basic], Visual Basic code
- Comment button
- buttons [Visual Basic], Uncomment
- buttons [Visual Basic], Comment
- code comments [Visual Basic], Visual Basic
- Visual Basic code, comments
- comments
- code comments
ms.assetid: 90136fba-22eb-49f9-ba81-63db629b4a47
ms.openlocfilehash: 92aadfe851514dcba713455664cf8f7b0aa1c17b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597546"
---
# <a name="comments-in-code-visual-basic"></a>Comentarios en el código (Visual Basic)
Cuando lea ejemplos de código, encontrará el símbolo de comentario (`'`). Este símbolo indica al compilador de Visual Basic para pasar por alto el texto que aparece a continuación o *comentario*. Los comentarios son notas cortas explicativas que se agregan al código para aportar mayor información a las personas que lo lean.  
  
 Una buena práctica de programación consiste en comenzar todos los procedimientos con un comentario breve que describe las características funcionales del procedimiento (lo que hace). Esto ayuda al desarrollador y a los que puedan examinar el código. Debería separar los detalles de implementación (cómo lo hace el procedimiento) de los comentarios que describen las características funcionales. Al incluir detalles de implementación en la descripción, recuerde actualizarlos en el momento de actualizar la función.  
  
 Los comentarios pueden ir a continuación de una instrucción en la misma línea, o pueden ocupar una línea completa. Ambas opciones quedan reflejadas en el código siguiente.  
  
 [!code-vb[VbVbcnConventions#16](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_1.vb)]  
  
 Si el comentario necesita más de una línea, utilice el símbolo de comentario en cada línea, como se muestra en el siguiente ejemplo:  
  
 [!code-vb[VbVbcnConventions#17](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_2.vb)]  
  
## <a name="commenting-guidelines"></a>Instrucciones sobre los comentarios  
 La tabla siguiente proporciona directrices generales sobre los tipos de comentarios que pueden preceder una sección de código. Estos son sugerencias; Visual Basic no aplica las reglas para agregar comentarios. Escriba lo que considere más conveniente, para uso propio o para cualquier otra persona que lea el código.  
  
|||  
|---|---|  
|Tipo de comentario|Descripción del comentario|  
|Propósito|Describe qué hace el procedimiento (no cómo lo hace).|  
|Suposiciones|Enumera cada variable externa, control, archivo abierto u otro elemento al cual el procedimiento tenga acceso.|  
|Efectos|Enumera cada variable externa, control o archivo que esté afectado, y el efecto que tienen (únicamente si no es evidente).|  
|Entradas|Especifica el propósito del argumento.|  
|Valores devueltos|Explica los valores que devuelve el procedimiento|  
  
 Recuerde los siguientes puntos:  
  
-   Cada declaración de variable importante debe incluir un comentario anterior que describa el uso de la variable que se declara.  
  
-   Las variables, controles y procedimientos deben tener un nombre lo suficientemente claro para asegurar que el uso de comentarios sólo sea necesario para detalles de implementación compleja.  
  
-   Después de la secuencia de continuación de línea no puede escribirse un comentario en la misma línea.  
  
 Puede agregar o quitar símbolos de comentario de un bloque de código seleccionando una o varias líneas de código y eligiendo la **comentario** (![VisualBasicWinAppCodeEditorCommentButton](../../../visual-basic/programming-guide/program-structure/media/vacommentbutton.gif "vaCommentButton ")) y **sin comentarios** (![VisualStudioWinAppProjectUncommentButton](../../../visual-basic/programming-guide/program-structure/media/vauncommentbutton.gif "vaUncommentButton")) los botones de la **editar**  barra de herramientas.  
  
> [!NOTE]
>  También puede agregar comentarios al código poniendo la palabra clave `REM` antes del texto. Sin embargo, el `'` símbolo y el **comentario**/**sin comentarios** botones son más fáciles de utilizar y requieren menos espacio y memoria.  
  
## <a name="see-also"></a>Vea también
- [Documentar el código con comentarios XML](https://msdn.microsoft.com/magazine/dd722812.aspx)
- [Cómo: Crear documentación XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
- [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [REM (instrucción)](../../../visual-basic/language-reference/statements/rem-statement.md)
