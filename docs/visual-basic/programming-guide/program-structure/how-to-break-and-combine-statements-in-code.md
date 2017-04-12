---
title: "Cómo: interrumpir y combinar instrucciones en código (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb._
dev_langs:
- VB
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
- underscores, in code
- statements [Visual Basic], line continuation in
- line breaks, in code
- line-continuation character
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 840036a91f430f72e0258b8be466770f2855a58f
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a>Cómo: Interrumpir y combinar instrucciones en código (Visual Basic)
Al escribir el código, a veces puede crear instrucciones largas que requieren un desplazamiento horizontal en el Editor de código. Aunque esto no afecta a la forma en el código se ejecuta, es difícil para que usted o cualquier otra persona leer el código tal y como aparece en el monitor. En estos casos, considere la posibilidad de dividir la única instrucción larga en varias líneas.  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a>Para dividir una instrucción única en varias líneas  
  
-   Utilice el carácter de continuación de línea, que es un carácter de subrayado (`_`), en el punto en el que desea que la línea se interrumpa. El carácter de subrayado debe tener inmediatamente antes un espacio e inmediatamente después un terminador de línea (retorno de carro).  
  
    > [!NOTE]
    >  En algunos casos, si se omite el carácter de continuación de línea, el compilador de Visual Basic continúa implícitamente la instrucción en la siguiente línea de código. Para obtener una lista de elementos de sintaxis que se puede omitir el carácter de continuación de línea, vea "Continuación de línea implícita" en [instrucciones](../../../visual-basic/programming-guide/language-features/statements.md).  
  
     En el ejemplo siguiente, la instrucción se segmenta en cuatro líneas con caracteres de continuación de línea final de todas excepto la última línea.  
  
     [!code-vb[VbVbcnConventions&#20;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]  
  
     Con esta secuencia hace el código más fácil de leer, tanto en línea como al imprimirlo.  
  
     El carácter de continuación de línea debe ser el último carácter de una línea. No puede seguir con nada más en la misma línea.  
  
     Existen algunas limitaciones en cuanto a donde puede usar el carácter de continuación de línea; Por ejemplo, no puede utilizar en medio de un nombre de argumento. Puede interrumpir una lista de argumentos con el carácter de continuación de línea, pero los nombres individuales de los argumentos deben permanecer intactos.  
  
     No puede continuar un comentario mediante un carácter de continuación de línea. El compilador no examina los caracteres en un comentario de un significado especial. Un comentario de varias líneas, repita el símbolo de comentario (`'`) en cada línea.  
  
 Aunque colocar cada instrucción en una línea independiente es el método recomendado, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] también permite colocar varias instrucciones en la misma línea.  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a>Para colocar varias instrucciones en la misma línea  
  
-   Separe las instrucciones con un signo de dos puntos (`:`), como en el ejemplo siguiente.  
  
     [!code-vb[VbVbcnConventions&#10;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
