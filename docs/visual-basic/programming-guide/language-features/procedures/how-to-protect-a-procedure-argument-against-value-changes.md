---
title: Procedimiento para proteger un argumento de procedimiento para que no se realicen cambios de valor
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
ms.openlocfilehash: 84eadf3d364b69120221d80e464b1175b1602e13
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071487"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a>Cómo: Proteger un argumento de procedimiento para que no se realicen cambios de valor (Visual Basic)

Si un procedimiento declara un parámetro como [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic proporciona al código de procedimiento una referencia directa al elemento de programación subyacente al argumento en el código de llamada. Esto permite al procedimiento cambiar el valor subyacente del argumento en el código de llamada. En algunos casos, es posible que el código de llamada desee proteger contra este tipo de cambio.  
  
 Siempre puede proteger un argumento del cambio declarando el parámetro correspondiente [ByVal](../../../language-reference/modifiers/byval.md) en el procedimiento. Si desea poder cambiar un argumento determinado en algunos casos, pero no en otros, puede declararlo `ByRef` y permitir que el código de llamada determine el mecanismo de paso en cada llamada. Para ello, incluye el argumento correspondiente entre paréntesis para pasarlo por valor o no lo incluye entre paréntesis para pasarlo por referencia. Para obtener más información, vea [Cómo: forzar un argumento para que se pase por valor](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestran dos procedimientos que toman una variable de matriz y operan en sus elementos. El `increase` procedimiento simplemente agrega uno a cada elemento. El `replace` procedimiento asigna una nueva matriz al parámetro `a()` y, a continuación, agrega una a cada elemento. Sin embargo, la reasignación no afecta a la variable de matriz subyacente en el código de llamada.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 La primera `MsgBox` llamada muestra "después del aumento (n): 11, 21, 31, 41". Dado que la matriz `n` es un tipo de referencia, `increase` puede cambiar sus miembros, aunque el mecanismo de paso sea `ByVal` .  
  
 La segunda `MsgBox` llamada muestra "After Replace (n): 11, 21, 31, 41". Dado `n` que se pasa `ByVal` , `replace` no se puede modificar la variable `n` en el código de llamada mediante la asignación de una nueva matriz a ella. Cuando `replace` crea la nueva instancia de la matriz `k` y la asigna a la variable local `a` , pierde la referencia a `n` pasada por el código de llamada. Cuando cambia los miembros de `a` , solo `k` se ve afectada la matriz local. Por lo tanto, no `replace` incrementa los valores de array `n` en el código de llamada.  
  
## <a name="compile-the-code"></a>Compilar el código  

 De forma predeterminada, en Visual Basic es pasar argumentos por valor. Sin embargo, es aconsejable incluir la palabra clave [ByVal](../../../language-reference/modifiers/byval.md) o [ByRef](../../../language-reference/modifiers/byref.md) con cada parámetro declarado. Esto hace que el código sea más fácil de leer.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Procedimiento para pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)
- [Pasar argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Diferencias entre argumentos modificables y no modificables](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Procedimiento para cambiar el valor de un argumento de procedimiento](./how-to-change-the-value-of-a-procedure-argument.md)
- [Procedimiento para forzar un argumento para que pase como un valor](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Paso de argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)
- [Tipos de valor y tipos de referencia](../data-types/value-types-and-reference-types.md)
