---
title: "REM (Instrucción, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.'
- vb.Rem
- Rem
- "'"
helpviewer_keywords:
- REM statement [Visual Basic]
- comments, Visual Basic code
- code comments, Visual Basic
- Visual Basic code, comments
- "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d64ce970e3e74437f5e8c63c8a4d578900902192
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="rem-statement-visual-basic"></a>REM (Instrucción, Visual Basic)
Se usa para incluir notas explicativas en el código fuente de un programa.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a>Elementos  
 `comment`  
 Opcional. El texto de cualquier comentario que desee incluir. Se requiere un espacio entre el `REM` palabra clave y `comment`.  
  
## <a name="remarks"></a>Comentarios  
 Puede colocar una `REM` instrucción aislada en una línea o puede colocar en una línea después de otra instrucción. El `REM` instrucción debe ser la última instrucción en la línea. Si sigue otra instrucción, la `REM` debe estar separada de esa instrucción por un espacio.  
  
 Puede utilizar una comilla simple (`'`) en lugar de `REM`. Esto es cierto si el comentario sigue a otra instrucción en la misma línea o se encuentra sola en una línea.  
  
> [!NOTE]
>  No se puede continuar una `REM` instrucción mediante una secuencia de continuación de línea (`_`). Una vez que inicia un comentario, el compilador no examina los caracteres de un significado especial. Para un comentario ocupe varias líneas, usar otra `REM` instrucción o un símbolo de comentario (`'`) en cada línea.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el `REM` instrucción, que se usa para incluir notas explicativas en un programa. También muestra la alternativa de utilizar el carácter de comilla simple (`'`) en lugar de `REM`.  
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Comentarios en código](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 [Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
