---
title: Palabras clave como nombres de elementos en código (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: c247ada67f6554362f287cf252dd49856c4995da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955589"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a>Palabras clave como nombres de elementos en código (Visual Basic)
Cualquier elemento de programa, como una variable, clase o miembro, puede tener el mismo nombre que una palabra clave restringida. Por ejemplo, puede crear una variable denominada `Loop`. Sin embargo, para hacer referencia a la versión del mismo, que tiene el mismo nombre que restringido `Loop` palabra clave, debe precedidos por una cadena de calificación completa o encerrarlo entre corchetes (`[ ]`), tal y como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbcnConventions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#8)]  
  
 Si no hace cualquiera de estos, a continuación, Visual Basic se da por supuesto el uso de la función intrínseca `Loop` palabra clave y se produce un error, como en el ejemplo siguiente:  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 Puede utilizar corchetes al hacer referencia a los formularios y controles y al declarar una variable o al definir un procedimiento con el mismo nombre que una palabra clave restringida. Puede ser fácil olvidarse de calificar los nombres o incluir los corchetes y, por tanto, introducir errores en el código y hacer más difícil de leer. Por este motivo, se recomienda que no utilice palabras clave restringidas como nombres de elementos de programa. Sin embargo, si una versión futura de Visual Basic define una nueva palabra clave que entra en conflicto con un nombre de control o formulario existente, a continuación, se puede usar esta técnica al actualizar el código para que funcione con la nueva versión.  
  
> [!NOTE]
>  El programa también puede incluir nombres de elementos proporcionados por otros ensamblados que se hace referencia. Si estos nombres entran en conflicto con palabras clave restringidas, a continuación, colocar corchetes alrededor de ellas hace que Visual Basic para interpretarlos como los elementos definidos.  
  
## <a name="see-also"></a>Vea también

- [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
