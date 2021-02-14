---
description: 'Más información sobre: Cómo: interrumpir y combinar instrucciones en código (Visual Basic)'
title: Procedimiento Interrupción y combinación de instrucciones en código
ms.date: 07/20/2015
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
ms.openlocfilehash: 33a8b87171c4ee14e73ada564cff406637e96783
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475999"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a>Cómo: Interrumpir y combinar instrucciones en código (Visual Basic)

Al escribir el código, puede crear a veces instrucciones largas que requieren un desplazamiento horizontal en el editor de código. Aunque esto no afecta al modo en que se ejecuta el código, dificulta la lectura del código tal y como aparece en el monitor. En tales casos, debería considerar la posibilidad de dividir la única instrucción larga en varias líneas.

## <a name="to-break-a-single-statement-into-multiple-lines"></a>Para dividir una sola instrucción en varias líneas

Use el carácter de continuación de línea, que es un carácter de subrayado ( `_` ), en el punto en el que desea que se interrumpa la línea. El carácter de subrayado debe ir inmediatamente precedido de un espacio y seguido inmediatamente de un terminador de línea (retorno de carro) o (a partir de la versión 16,0) un comentario seguido de un retorno de carro.

  > [!NOTE]
  > En algunos casos, si se omite el carácter de continuación de línea, el compilador Visual Basic continuará implícitamente la instrucción en la siguiente línea de código. Para obtener una lista de los elementos de sintaxis para los que puede omitir el carácter de continuación de línea, vea "continuación de línea implícita" en las [instrucciones](../language-features/statements.md).

  En el ejemplo siguiente, la instrucción se divide en cuatro líneas con caracteres de continuación de línea que terminan todo excepto la última línea.

  [!code-vb[VbVbcnConventions#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#20)]

  El uso de esta secuencia hace que el código sea más fácil de leer, tanto en línea como en el momento de su impresión.

  El carácter de continuación de línea debe ser el último carácter de una línea. No puede seguirlo con nada más en la misma línea.

  Existen algunas limitaciones en cuanto a dónde se puede usar el carácter de continuación de línea; por ejemplo, no se puede utilizar en medio de un nombre de argumento. Puede dividir una lista de argumentos con el carácter de continuación de línea, pero los nombres individuales de los argumentos deben permanecer intactos.

  No se puede continuar un comentario mediante un carácter de continuación de línea. El compilador no examina los caracteres de un comentario para obtener un significado especial. Para un Comentario de varias líneas, repita el símbolo de comentario ( `'` ) en cada línea.

 Aunque la colocación de cada instrucción en una línea independiente es el método recomendado, Visual Basic también permite colocar varias instrucciones en la misma línea.

## <a name="to-place-multiple-statements-on-the-same-line"></a>Para colocar varias instrucciones en la misma línea

Separe las instrucciones con dos puntos ( `:` ), como en el ejemplo siguiente:

  [!code-vb[VbVbcnConventions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#10)]

## <a name="see-also"></a>Consulte también

- [Convenciones de código y estructura de programas](program-structure-and-code-conventions.md)
- [Instrucciones](../language-features/statements.md)
