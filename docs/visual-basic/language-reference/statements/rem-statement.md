---
title: REM (Instrucción, Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: a3ad63472f6a3f7ae1ec13742185790667c7bcf0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54699056"
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
 Puede colocar un `REM` por sí solo en una línea o instrucción puede colocarlo en una línea después de otra instrucción. El `REM` instrucción debe ser la última instrucción en la línea. Si sigue otra instrucción, el `REM` deben estar separados de esa instrucción por un espacio.  
  
 Puede usar una comilla simple (`'`) en lugar de `REM`. Esto es cierto si el comentario sigue otra instrucción en la misma línea o se encuentra solo en una línea.  
  
> [!NOTE]
>  No puede continuar una `REM` instrucción mediante el uso de una secuencia de continuación de línea (`_`). Una vez que inicia un comentario, el compilador no examina los caracteres de un significado especial. Para un comentario de varias líneas, use otro `REM` instrucción o un símbolo de comentario (`'`) en cada línea.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente ilustra la `REM` instrucción, que se usa para incluir notas explicativas en un programa. También se muestra la alternativa de utilizar el carácter de comilla simple (`'`) en lugar de `REM`.  
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también
- [Comentarios en código](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [Cómo: Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
