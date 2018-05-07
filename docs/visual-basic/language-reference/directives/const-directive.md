---
title: '##Const (directiva)'
ms.date: 07/20/2015
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
ms.openlocfilehash: a3b3318f6b44f7d1798e08195be5aeb920b61c0c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="const-directive"></a>#Const (Directiva)
Permite definir constantes condicionales para el compilador de Visual Basic.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a>Elementos  
 `constname`  
 Requerido. Nombre de la constante que se está definida.  
  
 `expression`  
 Requerido. Literal, otra constante de compilación condicional o cualquier combinación que incluya operadores aritméticos o lógicos, excepto `Is`.  
  
## <a name="remarks"></a>Comentarios  
 Constantes de compilación condicional siempre son privados para el archivo en que aparecen. No se puede crear constantes de compilación públicas con el `#Const` directiva; puede crear solo en la interfaz de usuario o con el `/define` opción del compilador.  
  
 Puede usar únicamente constantes de compilación condicional y literales en `expression`. Uso de una constante estándar definida con `Const` produce un error. Por el contrario, puede usar constantes definidas con el `#Const` palabra clave solo para la compilación condicional. Constantes también se definido, en cuyo caso tienen un valor de `Nothing`.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa la directiva `#Const`.  
  
 [!code-vb[VbVbalrConditionalComp#3](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/const-directive_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)  
 [#If...Then...#Else (directivas)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [Const (instrucción)](../../../visual-basic/language-reference/statements/const-statement.md)  
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [If...Then...Else (instrucción)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
