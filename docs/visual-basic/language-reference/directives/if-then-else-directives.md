---
title: '#<a name="ifthenelse-directives"></a>If... Then... #Else directivas'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.#EndIf
- '#End If'
- '#Then'
- '#ElseIf'
- vb.#ElseIf
- vb.#Else
- vb.#If
helpviewer_keywords:
- Visual Basic code, compiling
- '#If directive [Visual Basic]'
- conditional compilation [Visual Basic], directives
- '#End if directive [Visual Basic]'
- selective compiling
- else directive (#else)
- '#Else directive [Visual Basic]'
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 77757e441ae937aa86122f237e839d1005644409
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ifthenelse-directives"></a>#If...Then...#Else (Directivas)
Compila condicionalmente bloques de código de Visual Basic seleccionados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
#If expression Then  
   statements  
[ #ElseIf expression Then  
   [ statements ]  
...  
#ElseIf expression Then  
   [ statements ] ]  
[ #Else  
   [ statements ] ]  
#End If  
```  
  
## <a name="parts"></a>Elementos  
 `expression`  
 Necesario para `#If` y `#ElseIf` instrucciones, opcionales en otro lugar. Cualquier expresión, que consta únicamente de una o más constantes de compilación condicional, literales y operadores, que se evalúa como `True` o `False`.  
  
 `statements`  
 Necesario para `#If` bloque de instrucción, opcional en otro lugar. Líneas de programa de Visual Basic o directivas de compilación que se compilan si la expresión asociada se evalúa como `True`.  
  
 `#End If`  
 Finaliza el `#If` bloque de instrucciones.  
  
## <a name="remarks"></a>Comentarios  
 En la superficie, el comportamiento de la `#If...Then...#Else` Else es el mismo que el de la `If...Then...Else` las instrucciones. Sin embargo, el `#If...Then...#Else` Else evalúan lo que compila el compilador, mientras que la `If...Then...Else` instrucciones evalúan las condiciones en tiempo de ejecución.  
  
 Compilación condicional se utiliza normalmente para compilar el mismo programa para diferentes plataformas. También se utiliza para evitar que código de depuración aparezca en un archivo ejecutable. Código excluido durante la compilación condicional se omite por completo desde el archivo ejecutable final, por lo que no tiene ningún efecto en el tamaño o el rendimiento.  
  
 Independientemente del resultado de la evaluación, todas las expresiones se evalúan utilizando `Option Compare Binary`. El `Option Compare` instrucción no afecta a las expresiones en `#If` y `#ElseIf` las instrucciones.  
  
> [!NOTE]
>  No hay ningún formulario de línea de la `#If`, `#Else`, `#ElseIf`, y `#End If` directivas existe. Ningún otro código puede aparecer en la misma línea que cualquiera de las directivas.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza la `#If...Then...#Else` construcción para determinar si se compilan ciertas instrucciones.  
  
 [!code-vb[VbVbalrConditionalComp#1](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/if-then-else-directives_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [#Const (directiva)](../../../visual-basic/language-reference/directives/const-directive.md)  
 [If...Then...Else (instrucción)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
