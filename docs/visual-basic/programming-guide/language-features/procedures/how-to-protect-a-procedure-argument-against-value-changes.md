---
title: Procedimiento Proteger un argumento de procedimiento contra cambios de valor (Visual Basic)
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
ms.openlocfilehash: 2548d7a686f3557d154fc4cc15f6fc8026ac46bf
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968379"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a>Procedimiento Proteger un argumento de procedimiento contra cambios de valor (Visual Basic)
Si un procedimiento declara un parámetro como [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic proporciona el código del procedimiento una referencia directa al elemento de programación subyacente del argumento en el código de llamada. Esto permite que el procedimiento para cambiar el valor subyacente del argumento en el código de llamada. En algunos casos es posible que desee el código de llamada para protegerse frente a este cambio.  
  
 Siempre puede proteger un argumento de cambio al declarar el parámetro correspondiente [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) en el procedimiento. Si desea poder cambiar un determinado argumento en algunos casos, pero no otros, puede declararlo `ByRef` y permitir que el código que realiza la llamada a determinar el mecanismo de paso en cada llamada. Para ello, incluya el argumento correspondiente entre paréntesis para pasarlo por valor o déjelo sin paréntesis para pasarlo por referencia. Para obtener más información, vea [Cómo: Forzar un argumento para pasar por valor](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra dos procedimientos que toman una variable de matriz y operan en sus elementos. El `increase` procedimiento simplemente agrega uno a cada elemento. El `replace` procedimiento asigna una nueva matriz al parámetro `a()` y, a continuación, agrega uno a cada elemento. Sin embargo, la reasignación no afecta a la variable de matriz subyacente en el código de llamada.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 La primera `MsgBox` llamada a muestra "después de Increase (n): 11, 21, 31, 41". Dado que la matriz `n` es un tipo de referencia, `increase` puede cambiar sus miembros, aunque es el mecanismo de paso `ByVal`.  
  
 El segundo `MsgBox` llamada a muestra "después de Replace (n): 11, 21, 31, 41". Dado que `n` se pasa `ByVal`, `replace` no se puede modificar la variable `n` en el código de llamada, se asigna una nueva matriz a él. Cuando `replace` crea la nueva instancia de matriz `k` y lo asigna a la variable local `a`, pierde la referencia a `n` pasada por el código de llamada. Cuando cambia los miembros de `a`, solo la matriz local `k` se ve afectado. Por lo tanto, `replace` no incrementar los valores de matriz `n` en el código de llamada.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El valor predeterminado en Visual Basic consiste en pasar argumentos por valor. Sin embargo, es buena práctica para incluir cualquiera de programación la [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) palabra clave con cada parámetro declarado. Esto hace que el código más fácil de leer.  
  
## <a name="see-also"></a>Vea también
- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Cómo: Pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)
- [Paso de argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Diferencias entre argumentos modificables y no modificables](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Cómo: Cambie el valor de un argumento de procedimiento](./how-to-change-the-value-of-a-procedure-argument.md)
- [Cómo: Forzar un argumento para pasar por valor](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Paso de argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
