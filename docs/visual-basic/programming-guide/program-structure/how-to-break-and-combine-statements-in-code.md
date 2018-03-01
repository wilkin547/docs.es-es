---
title: "Cómo: Interrumpir y combinar instrucciones en código (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb._
helpviewer_keywords:
- colons (:)
- line continuation
- _ line-continuation character
- ': line separator character'
- Visual Basic code, line breaks in
- Visual Basic code, line breaks
- Visual Basic code, line continuation
- long lines of code
- line terminator
- line-continuation sequence
- underscores [Visual Basic], in code
- statements [Visual Basic], line continuation in
- line breaks [Visual Basic], in code
- line-continuation character [Visual Basic]
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cf6b3ce7e5f9549ca04c4980bd3c91513b343ff6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a>Cómo: Interrumpir y combinar instrucciones en código (Visual Basic)
Al escribir el código, en ocasiones puede crear instrucciones largas que requieren un desplazamiento horizontal en el Editor de código. Aunque esto no afecta a la forma en el código se ejecuta, es difícil para que usted o cualquier persona leer el código tal y como aparece en el monitor. En estos casos, considere la posibilidad de dividir la única instrucción larga en varias líneas.  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a>Para dividir una única instrucción en varias líneas  
  
-   Utilice el carácter de continuación de línea, que es un carácter de subrayado (`_`), en el punto en el que desea segmentar la línea. El carácter de subrayado debe tener inmediatamente antes un espacio e inmediatamente después un terminador de línea (retorno de carro).  
  
    > [!NOTE]
    >  En algunos casos, si se omite el carácter de continuación de línea, el compilador de Visual Basic implícitamente continuará, en la siguiente línea de código, la instrucción. Para obtener una lista de elementos de sintaxis para el que se puede omitir el carácter de continuación de línea, vea "Continuación de línea implícita" en [instrucciones](../../../visual-basic/programming-guide/language-features/statements.md).  
  
     En el ejemplo siguiente, la instrucción se divide en cuatro líneas con caracteres de continuación de línea todas las terminar líneas excepto la última.  
  
     [!code-vb[VbVbcnConventions#20](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]  
  
     Uso de esta secuencia, el código será más fácil de leer, tanto en línea como al imprimirlo.  
  
     El carácter de continuación de línea debe ser el último carácter de una línea. No puede seguir con cualquier otra cosa en la misma línea.  
  
     Existen algunas limitaciones en cuanto a donde puede usar el carácter de continuación de línea; Por ejemplo, no podrá utilizarla en el medio de un nombre de argumento. Puede interrumpir una lista de argumentos con el carácter de continuación de línea, pero los nombres individuales de los argumentos deben permanecer intactos.  
  
     No puede continuar un comentario mediante el uso de un carácter de continuación de línea. El compilador no examina los caracteres en un comentario de un significado especial. Para un comentario ocupe varias líneas, repita el símbolo de comentario (`'`) en cada línea.  
  
 Aunque la colocación de cada instrucción en una línea independiente es el método recomendado, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] también le permite colocar varias instrucciones en la misma línea.  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a>Para colocar varias instrucciones en la misma línea  
  
-   Separe las instrucciones con un signo de dos puntos (`:`), como en el ejemplo siguiente.  
  
     [!code-vb[VbVbcnConventions#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
