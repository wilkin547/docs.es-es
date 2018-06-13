---
title: 'Cómo: Cambiar el valor de un argumento de procedimiento (Visual Basic)'
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
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
ms.openlocfilehash: 118dd3389804794801d39e7d67b68ab195bbad3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655842"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a>Cómo: Cambiar el valor de un argumento de procedimiento (Visual Basic)
Cuando se llama a un procedimiento, cada argumento proporcionado se corresponde a uno de los parámetros definidos en el procedimiento. En algunos casos, el código del procedimiento puede cambiar el valor subyacente a un argumento en el código de llamada. En otros casos, el procedimiento puede cambiar solo su copia local de un argumento.  
  
 Cuando se llama al procedimiento, Visual Basic realiza una copia local de cada argumento que se pasa [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Para cada argumento pasado [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic proporciona el código del procedimiento una referencia directa al elemento de programación subyacente del argumento en el código de llamada.  
  
 Si el elemento subyacente en el código de llamada es un elemento modificable y el argumento se pasa `ByRef`, el código del procedimiento puede utilizar la referencia directa para cambiar el valor del elemento en el código de llamada.  
  
## <a name="changing-the-underlying-value"></a>Cambiar el valor subyacente  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a>Para cambiar el valor subyacente de un argumento de procedimiento en el código de llamada  
  
1.  En la declaración de procedimiento, especifique [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) para el parámetro correspondiente al argumento.  
  
2.  En el código que realiza la llamada, pasar un elemento de programación modificable como argumento.  
  
3.  En el código que realiza la llamada, no incluya el argumento entre paréntesis en la lista de argumentos.  
  
4.  En el código de procedimiento, utilice el nombre de parámetro para asignar un valor al elemento subyacente en el código de llamada.  
  
 Vea el ejemplo más abajo para ver una demostración.  
  
## <a name="changing-local-copies"></a>Cambiar las copias locales  
 Si el elemento subyacente en el código de llamada es un elemento no modificable, o si se pasa el argumento `ByVal`, el procedimiento no puede cambiar su valor en el código de llamada. Sin embargo, el procedimiento puede cambiar su copia local de dicho argumento.  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a>Para cambiar la copia de un argumento de procedimiento en el código de procedimiento  
  
1.  En la declaración de procedimiento, especifique [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) para el parámetro correspondiente al argumento.  
  
     -o bien-  
  
     En el código que realiza la llamada, incluya el argumento entre paréntesis en la lista de argumentos. Esto obligará a Visual Basic para pasar el argumento por valor, incluso si el parámetro correspondiente especifica `ByRef`.  
  
2.  En el código de procedimiento, utilice el nombre de parámetro para asignar un valor a la copia local del argumento. No se cambia el valor subyacente en el código de llamada.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra dos procedimientos que toman una variable de matriz y operan con sus elementos. El `increase` procedimiento simplemente agrega una unidad a cada elemento. El `replace` procedimiento asigna una nueva matriz al parámetro `a()` y, a continuación, agrega una unidad a cada elemento.  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#36](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]  
  
 La primera `MsgBox` llamada a muestra "después Increase (n): 11, 21, 31, 41". Dado que la matriz `n` es un tipo de referencia, `replace` puede cambiar sus miembros, aunque es el mecanismo para pasar argumentos `ByVal`.  
  
 El segundo `MsgBox` llamada a muestra "después Replace (n): 101, 201, 301". Dado que `n` se pasa `ByRef`, `replace` puede modificar la variable `n` en el código que realiza la llamada y asignar una nueva matriz a él. Dado que `n` es un tipo de referencia, `replace` también se puede cambiar sus miembros.  
  
 Puede impedir que el procedimiento modificar la variable en el código de llamada. Vea [Cómo: proteger un argumento de procedimiento no se realicen cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md).  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Cuando se pasa una variable por referencia, debe utilizar el `ByRef` palabra clave para especificar este mecanismo.  
  
 El valor predeterminado en Visual Basic es pasar argumentos por valor. Sin embargo, resulta recomienda incluir la [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) palabra clave con cada parámetro declarado. Esto hace que el código más fácil de leer.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Siempre es un riesgo potencial al permitir a un procedimiento cambiar el valor subyacente a un argumento en el código de llamada. Asegúrese de que se espera que este valor puede cambiar, y estar preparado para comprobar su validez antes de usarlo.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)  
 [Paso de argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)  
 [Diferencias entre argumentos modificables y no modificables](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [Diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [Proteger un argumento de procedimiento para que no se realicen cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [Forzar un argumento para que pase como un valor](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [Paso de argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)  
 [Tipos de valores y tipos de referencias](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
