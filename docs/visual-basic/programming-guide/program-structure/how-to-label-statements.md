---
title: "Cómo: Aplicar etiquetas a las instrucciones (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 190ec9fc2392e6e4adae9b2b612edd69d73cedfd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-label-statements-visual-basic"></a>Cómo: Aplicar etiquetas a las instrucciones (Visual Basic)
Bloques de instrucciones se componen de líneas de código delimitadas por dos puntos. Se dice que las líneas de código precedidas por una cadena o entero identificación *con la etiqueta*. Las etiquetas de instrucciones se utilizan para marcar una línea de código que se identifique para su uso con instrucciones como `On Error Goto`.  
  
 Las etiquetas pueden ser identificadores Visual Basic válidos, como las que identifican elementos de programación, o literales enteros. Una etiqueta debe aparecer al principio de una línea de código fuente y debe ir seguida por un signo de dos puntos, independientemente de si es seguida por una instrucción en la misma línea.  
  
 El compilador identifica las etiquetas comprobando si el principio de la línea coincide con cualquier identificador ya definido. Si no es así, el compilador supone que es una etiqueta.  
  
 Las etiquetas tienen su propio espacio de declaración y no interfieren con otros identificadores. Ámbito de una etiqueta es el cuerpo del método. Declaración de la etiqueta tiene prioridad en cualquier situación ambigua.  
  
> [!NOTE]
>  Las etiquetas se pueden utilizar sólo en las instrucciones ejecutables dentro de métodos.  
  
### <a name="to-label-a-line-of-code"></a>Para etiquetar una línea de código  
  
-   Coloque un identificador, seguido de dos puntos, al principio de la línea de código fuente.  
  
     Por ejemplo, las siguientes líneas de código están etiquetadas con `Jump` y `120`, respectivamente:  
  
     [!code-vb[VbVbalrStatements#708](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/how-to-label-statements_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)  
 [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
