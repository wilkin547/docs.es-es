---
title: REM (Instrucción)
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
ms.openlocfilehash: bdde4beae242c3175b02cd2af252babb850416f6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346729"
---
# <a name="rem-statement-visual-basic"></a>REM (Instrucción, Visual Basic)
Se usa para incluir comentarios explicativos en el código fuente de un programa.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
REM comment  
' comment  
```  
  
## <a name="parts"></a>Elementos  
 `comment`  
 Opcional. Texto de cualquier comentario que desee incluir. Se requiere un espacio entre la palabra clave `REM` y `comment`.  
  
## <a name="remarks"></a>Comentarios  
 Puede colocar una instrucción `REM` sola en una línea o puede colocarla en una línea después de otra instrucción. La instrucción `REM` debe ser la última instrucción de la línea. Si sigue otra instrucción, el `REM` debe estar separado de la instrucción por un espacio.  
  
 Puede usar una comilla simple (`'`) en lugar de `REM`. Esto es así si el comentario sigue a otra instrucción en la misma línea o solo se coloca en una línea.  
  
> [!NOTE]
> No se puede continuar una instrucción `REM` mediante una secuencia de continuación de línea (`_`). Una vez que se inicia un comentario, el compilador no examina los caracteres para un significado especial. Para un Comentario de varias líneas, use otra instrucción `REM` o un símbolo de comentario (`'`) en cada línea.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra la instrucción `REM`, que se usa para incluir comentarios explicativos en un programa. También se muestra la alternativa de usar el carácter de comilla simple (`'`) en lugar de `REM`.  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vea también

- [Comentarios en código](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
