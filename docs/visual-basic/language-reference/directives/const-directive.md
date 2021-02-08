---
description: 'Más información acerca de: Directiva de #Const'
title: '#Directiva Const'
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
ms.openlocfilehash: 9597666ee1320f5dfda226040f93a84eb60a3deb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797281"
---
# <a name="const-directive"></a>#Const (Directiva)

Define constantes de compilador condicionales para Visual Basic.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
#Const constname = expression  
```  
  
## <a name="parts"></a>Partes  

 `constname`  
 Necesario. Nombre de la constante que se está definiendo.  
  
 `expression`  
 Necesario. Literal, otra constante del compilador condicional o cualquier combinación que incluya todos o todos los operadores aritméticos o lógicos, excepto `Is` .  
  
## <a name="remarks"></a>Observaciones  

 Las constantes de compilador condicionales siempre son privadas en el archivo en el que aparecen. No se pueden crear constantes del compilador públicas mediante la `#Const` directiva; solo se pueden crear en la interfaz de usuario o con la `/define` opción del compilador.  
  
 Solo se pueden usar constantes y literales de compilador condicionales en `expression` . El uso de una constante estándar definida con `Const` produce un error. Por el contrario, puede usar constantes definidas con la `#Const` palabra clave solo para la compilación condicional. Las constantes también pueden ser undefined, en cuyo caso tienen un valor de `Nothing` .  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se usa la directiva `#Const`.  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [-define (Visual Basic)](../../reference/command-line-compiler/define.md)
- [#If...Then...#Else (directivas)](if-then-else-directives.md)
- [Instrucción Const](../statements/const-statement.md)
- [Compilación condicional](../../programming-guide/program-structure/conditional-compilation.md)
- [Instrucción If...Then...Else](../statements/if-then-else-statement.md)
