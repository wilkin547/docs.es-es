---
title: 'Cómo: Proteger un argumento de procedimiento para que no se realicen cambios de valor (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
ms.openlocfilehash: d2e131b770d8498a634d946a5900f9b373ca7e56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651523"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a>Cómo: Proteger un argumento de procedimiento para que no se realicen cambios de valor (Visual Basic)
Si un procedimiento declara un parámetro como [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic proporciona el código del procedimiento una referencia directa al elemento de programación subyacente del argumento en el código de llamada. Esto permite que el procedimiento para cambiar el valor subyacente del argumento en el código de llamada. En algunos casos, el código de llamada conviene para protegerse frente a este tipo de cambios.  
  
 Siempre puede proteger un argumento de cambio al declarar el parámetro correspondiente [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) en el procedimiento. Si desea poder cambiar un determinado argumento en algunos casos, pero no otros, puede declararlo `ByRef` y deje que el código que realiza la llamada a determinar el mecanismo de paso en cada llamada. Para ello, incluya el argumento correspondiente entre paréntesis para pasar por valor o no se incluye entre paréntesis para pasar por referencia. Para obtener más información, consulte [Cómo: forzar un argumento para pasar por valor](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra dos procedimientos que toman una variable de matriz y operan con sus elementos. El `increase` procedimiento simplemente agrega una unidad a cada elemento. El `replace` procedimiento asigna una nueva matriz al parámetro `a()` y, a continuación, agrega una unidad a cada elemento. Sin embargo, la reasignación no afecta a la variable de matriz subyacente en el código de llamada.  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]  
  
 La primera `MsgBox` llamada a muestra "después Increase (n): 11, 21, 31, 41". Dado que la matriz `n` es un tipo de referencia, `replace` puede cambiar sus miembros, aunque es el mecanismo para pasar argumentos `ByVal`.  
  
 El segundo `MsgBox` llamada a muestra "después Replace (n): 11, 21, 31, 41". Dado que `n` se pasa `ByVal`, `replace` no se puede modificar la variable `n` en el código que realiza la llamada mediante la asignación de una nueva matriz a él. Cuando `replace` crea la nueva instancia de la matriz `k` y lo asigna a la variable local `a`, pierde la referencia a `n` se pasa por el código de llamada. Cuando cambia los miembros de `a`, solo la matriz local `k` se ve afectado. Por lo tanto, `replace` no incrementa los valores de matriz `n` en el código de llamada.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El valor predeterminado en Visual Basic es pasar argumentos por valor. Sin embargo, resulta recomienda incluir la [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) palabra clave con cada parámetro declarado. Esto hace que el código más fácil de leer.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)  
 [Paso de argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)  
 [Diferencias entre argumentos modificables y no modificables](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [Diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [Cambiar el valor de un argumento de procedimiento](./how-to-change-the-value-of-a-procedure-argument.md)  
 [Forzar un argumento para que pase como un valor](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [Paso de argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)  
 [Tipos de valores y tipos de referencias](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
