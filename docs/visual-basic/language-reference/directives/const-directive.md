---
title: '#<a name="const-directive"></a>#Const (directiva)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6e162b01dc5c99fb7708337d259f9e66ddd6b64
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="const-directive"></a>#Const (Directiva)
Permite definir constantes condicionales para el compilador de Visual Basic.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a>Elementos  
 `constname`  
 Obligatorio. Nombre de la constante que se está definida.  
  
 `expression`  
 Obligatorio. Literal, otra constante de compilación condicional o cualquier combinación que incluya operadores aritméticos o lógicos, excepto `Is`.  
  
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
