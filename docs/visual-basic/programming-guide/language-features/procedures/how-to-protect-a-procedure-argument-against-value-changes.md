---
title: 'Cómo: Proteger un argumento de procedimiento para que no se realicen cambios de valor'
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
ms.openlocfilehash: 75c718c83f36e2f0b2c4cfb5504c2d740eaa3520
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347899"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a>Cómo: Proteger un argumento de procedimiento para que no se realicen cambios de valor (Visual Basic)
Si un procedimiento declara un parámetro como [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic proporciona al código de procedimiento una referencia directa al elemento de programación subyacente al argumento en el código de llamada. Esto permite al procedimiento cambiar el valor subyacente del argumento en el código de llamada. En algunos casos, es posible que el código de llamada desee proteger contra este tipo de cambio.  
  
 Siempre puede proteger un argumento del cambio declarando el parámetro correspondiente [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) en el procedimiento. Si desea poder cambiar un argumento determinado en algunos casos, pero no en otros, puede declararlo `ByRef` y permitir que el código de llamada determine el mecanismo de paso en cada llamada. Para ello, incluye el argumento correspondiente entre paréntesis para pasarlo por valor o no lo incluye entre paréntesis para pasarlo por referencia. Para obtener más información, vea [Cómo: forzar un argumento para que se pase por valor](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestran dos procedimientos que toman una variable de matriz y operan en sus elementos. El procedimiento `increase` simplemente agrega uno a cada elemento. El procedimiento `replace` asigna una nueva matriz al parámetro `a()` y, a continuación, agrega una a cada elemento. Sin embargo, la reasignación no afecta a la variable de matriz subyacente en el código de llamada.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 La primera llamada a `MsgBox` muestra "después del aumento (n): 11, 21, 31, 41". Dado que la matriz `n` es un tipo de referencia, `increase` puede cambiar sus miembros, aunque se `ByVal`el mecanismo de paso.  
  
 La segunda llamada a `MsgBox` muestra "After Replace (n): 11, 21, 31, 41". Dado que `n` se pasa `ByVal`, `replace` no puede modificar la variable `n` en el código de llamada mediante la asignación de una nueva matriz a ella. Cuando `replace` crea la nueva instancia de la matriz `k` y la asigna a la variable local `a`, pierde la referencia a `n` pasada por el código de llamada. Cuando cambia los miembros de `a`, solo se ve afectada la `k` de la matriz local. Por lo tanto, `replace` no incrementa los valores de la matriz `n` en el código de llamada.  
  
## <a name="compile-the-code"></a>Compilar el código  
 De forma predeterminada, en Visual Basic es pasar argumentos por valor. Sin embargo, es aconsejable incluir la palabra clave [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) con cada parámetro declarado. Esto hace que el código sea más fácil de leer.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)
- [Paso de argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Diferencias entre argumentos modificables y no modificables](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Cambiar el valor de un argumento de procedimiento](./how-to-change-the-value-of-a-procedure-argument.md)
- [Forzar un argumento para que pase como un valor](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Paso de argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
