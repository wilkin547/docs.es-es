---
title: "Palabras clave como nombres de elementos en código (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f410a0eaac0dcc034d406a89ed1d01a8f228a583
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a>Palabras clave como nombres de elementos en código (Visual Basic)
Cualquier elemento de programa, como una variable, una clase o un miembro, puede tener el mismo nombre que una palabra clave restringida. Por ejemplo, puede crear una variable denominada `Loop`. Sin embargo, para hacer referencia a la versión del mismo, que tiene el mismo nombre que restringido `Loop` palabra clave: debe ir precedida de una cadena de calificación completa o encerrar entre corchetes (`[ ]`), como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbcnConventions#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/keywords-as-element-names-in-code_1.vb)]  
  
 Si no hace cualquiera de estos, Visual Basic se supone el uso de la función intrínseca `Loop` palabra clave y genera un error, como en el ejemplo siguiente:  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 Puede utilizar corchetes al hacer referencia a los formularios y controles y al declarar una variable o al definir un procedimiento con el mismo nombre que una palabra clave restringida. Puede ser fácil olvidarse de calificar los nombres o incluir los corchetes y, por tanto, introducir errores en el código y dificultar la lectura. Por este motivo, se recomienda que no utilice palabras clave restringidas como nombres de elementos de programa. Sin embargo, si una futura versión de Visual Basic define una nueva palabra clave que entra en conflicto con un nombre de control o un formulario existente, a continuación, se puede usar esta técnica al actualizar el código para trabajar con la nueva versión.  
  
> [!NOTE]
>  El programa también puede incluir nombres de elementos proporcionados por otros ensamblados que se hace referencia. Si estos nombres entran en conflicto con palabras clave restringidas, a continuación, colocar corchetes alrededor de ellas hace que Visual Basic para interpretarlos como los elementos definidos.  
  
## <a name="see-also"></a>Vea también  
 [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
