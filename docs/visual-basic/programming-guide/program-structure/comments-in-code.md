---
title: Comentarios en código
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
ms.openlocfilehash: 189810393db42c54cb8a0f97b22b3d1514d9a7c4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346169"
---
# <a name="comments-in-code-visual-basic"></a>Comentarios en el código (Visual Basic)
Cuando lea ejemplos de código, encontrará el símbolo de comentario (`'`). This symbol tells the Visual Basic compiler to ignore the text following it, or the *comment*. Los comentarios son notas cortas explicativas que se agregan al código para aportar mayor información a las personas que lo lean.  
  
 Una buena práctica de programación consiste en comenzar todos los procedimientos con un comentario breve que describe las características funcionales del procedimiento (lo que hace). Esto ayuda al desarrollador y a los que puedan examinar el código. Debería separar los detalles de implementación (cómo lo hace el procedimiento) de los comentarios que describen las características funcionales. Al incluir detalles de implementación en la descripción, recuerde actualizarlos en el momento de actualizar la función.  
  
 Los comentarios pueden ir a continuación de una instrucción en la misma línea, o pueden ocupar una línea completa. Ambas opciones quedan reflejadas en el código siguiente.  
  
 [!code-vb[VbVbcnConventions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#16)]  
  
 Si el comentario necesita más de una línea, utilice el símbolo de comentario en cada línea, como se muestra en el siguiente ejemplo:  
  
 [!code-vb[VbVbcnConventions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#17)]  
  
## <a name="commenting-guidelines"></a>Instrucciones sobre los comentarios  
 La tabla siguiente proporciona directrices generales sobre los tipos de comentarios que pueden preceder una sección de código. These are suggestions; Visual Basic does not enforce rules for adding comments. Escriba lo que considere más conveniente, para uso propio o para cualquier otra persona que lea el código.  
  
|||  
|---|---|  
|Tipo de comentario|Descripción del comentario|  
|Finalidad|Describe qué hace el procedimiento (no cómo lo hace).|  
|Suposiciones|Enumera cada variable externa, control, archivo abierto u otro elemento al cual el procedimiento tenga acceso.|  
|Efectos|Enumera cada variable externa, control o archivo que esté afectado, y el efecto que tienen (únicamente si no es evidente).|  
|Entradas|Especifica el propósito del argumento.|  
|Valores devueltos|Explica los valores que devuelve el procedimiento|  
  
 Recuerde los siguientes puntos:  
  
- Cada declaración de variable importante debe incluir un comentario anterior que describa el uso de la variable que se declara.  
  
- Las variables, controles y procedimientos deben tener un nombre lo suficientemente claro para asegurar que el uso de comentarios sólo sea necesario para detalles de implementación compleja.  
  
- Después de la secuencia de continuación de línea no puede escribirse un comentario en la misma línea.  
  
 You can add or remove comment symbols for a block of code by selecting one or more lines of code and choosing the **Comment** (![The Visual Basic Comment button in Visual Studio.](./media/comments-in-code/visual-basic-comment-button.gif)) and **Uncomment** (![The Visual Basic Uncomment button in Visual Studio.](./media/comments-in-code/visual-basic-uncomment-button.gif)) buttons on the **Edit** toolbar.  
  
> [!NOTE]
> También puede agregar comentarios al código poniendo la palabra clave `REM` antes del texto. However, the `'` symbol and the **Comment**/**Uncomment** buttons are easier to use and require less space and memory.  
  
## <a name="see-also"></a>Vea también

- [Basic Instincts - Documenting Your Code With XML Comments](https://docs.microsoft.com/archive/msdn-magazine/2009/may/documenting-your-code-with-xml-comments)
- [Crear documentación XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
- [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [REM (instrucción)](../../../visual-basic/language-reference/statements/rem-statement.md)
