---
title: Filtrar Etiqueta instrucciones (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: 69ec8c7625410f140c59ba8dd492dca76857eb96
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58828646"
---
# <a name="how-to-label-statements-visual-basic"></a>Filtrar Etiqueta instrucciones (Visual Basic)
Bloques de instrucciones se componen de líneas de código delimitadas por signos de dos puntos. Líneas de código precedido de un entero o cadena de identificación se consideran *con la etiqueta*. Las etiquetas de instrucciones se usan para marcar una línea de código para identificarla para su uso con instrucciones como `On Error Goto`.  
  
 Las etiquetas pueden ser identificadores Visual Basic válidos, como las que identifican elementos de programación, o literales enteros. Una etiqueta debe aparecer al principio de una línea de código fuente y debe ir seguida por dos puntos, independientemente de si está seguida por una instrucción en la misma línea.  
  
 El compilador identifica las etiquetas mediante la comprobación de si el principio de la línea coincide con cualquier identificador ya definido. Si no es así, el compilador supone que es una etiqueta.  
  
 Las etiquetas tienen su propio espacio de declaración y no interfieren con otros identificadores. Ámbito de una etiqueta es el cuerpo del método. Declaración de la etiqueta tiene prioridad en cualquier situación ambigua.  
  
> [!NOTE]
>  Etiquetas se pueden usar únicamente en las instrucciones ejecutables dentro de los métodos.  
  
### <a name="to-label-a-line-of-code"></a>Para etiquetar una línea de código  
  
-   Coloque un identificador, seguido de dos puntos, al principio de la línea de código fuente.  
  
     Por ejemplo, las siguientes líneas de código se etiquetan con `Jump` y `120`, respectivamente:  
  
     [!code-vb[VbVbalrStatements#708](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#708)]  
  
## <a name="see-also"></a>Vea también

- [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
- [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
