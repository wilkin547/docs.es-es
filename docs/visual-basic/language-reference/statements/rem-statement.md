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
ms.openlocfilehash: 3c63c5613b40cb2014c77a0a996e3acb2cc304d4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58817024"
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
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vea también

- [Comentarios en código](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [Cómo: Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
