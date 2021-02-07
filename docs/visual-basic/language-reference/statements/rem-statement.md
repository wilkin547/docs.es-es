---
description: 'Más información acerca de: instrucción REM (Visual Basic)'
title: Instrucción REM
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
ms.openlocfilehash: c82621db98dc66060ae098ee6537ee58b24046a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741320"
---
# <a name="rem-statement-visual-basic"></a>REM (Instrucción, Visual Basic)

Se usa para incluir comentarios explicativos en el código fuente de un programa.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
REM comment  
' comment  
```  
  
## <a name="parts"></a>Partes  

 `comment`  
 Opcional. Texto de cualquier comentario que desee incluir. Se requiere un espacio entre la `REM` palabra clave y `comment` .  
  
## <a name="remarks"></a>Observaciones  

 Puede colocar una `REM` instrucción solo en una línea o puede colocarla en una línea después de otra instrucción. La `REM` instrucción debe ser la última instrucción de la línea. Si sigue otra instrucción, el `REM` debe estar separado de la instrucción por un espacio.  
  
 Puede usar una comilla simple ( `'` ) en lugar de `REM` . Esto es así si el comentario sigue a otra instrucción en la misma línea o solo se coloca en una línea.  
  
> [!NOTE]
> No se puede continuar una `REM` instrucción mediante una secuencia de continuación de línea ( `_` ). Una vez que se inicia un comentario, el compilador no examina los caracteres para un significado especial. Para un Comentario de varias líneas, use otra `REM` instrucción o un símbolo de comentario ( `'` ) en cada línea.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra la `REM` instrucción, que se usa para incluir comentarios explicativos en un programa. También se muestra la alternativa de usar el carácter de comilla simple ( `'` ) en lugar de `REM` .  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vea también

- [Comentarios en código](../../programming-guide/program-structure/comments-in-code.md)
- [Procedimiento Interrupción y combinación de instrucciones en código](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
