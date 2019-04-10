---
title: Filtrar Cambie el valor de un argumento de procedimiento (Visual Basic)
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
ms.openlocfilehash: a56bdf888163c9559b87e857abb33522c547ed45
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59316627"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a>Filtrar Cambie el valor de un argumento de procedimiento (Visual Basic)
Cuando se llama a un procedimiento, cada argumento proporcionado se corresponde a uno de los parámetros definidos en el procedimiento. En algunos casos, el código del procedimiento puede cambiar el valor subyacente a un argumento en el código de llamada. En otros casos, el procedimiento puede cambiar sólo su copia local de un argumento.  
  
 Cuando se llama al procedimiento, Visual Basic hace una copia local de cada argumento que se pasa [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Para cada argumento pasado [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic proporciona el código del procedimiento una referencia directa al elemento de programación subyacente del argumento en el código de llamada.  
  
 Si el elemento subyacente en el código de llamada es un elemento modificable y se pasa el argumento `ByRef`, el código del procedimiento puede utilizar la referencia directa para cambiar el valor del elemento en el código de llamada.  
  
## <a name="changing-the-underlying-value"></a>Cambiar el valor subyacente  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a>Para cambiar el valor subyacente de un argumento de procedimiento en el código de llamada  
  
1. En la declaración de procedimiento, especifique [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) para el parámetro correspondiente al argumento.  
  
2. En el código que realiza la llamada, pasar un elemento de programación modificable como argumento.  
  
3. En el código que realiza la llamada, no incluya el argumento entre paréntesis en la lista de argumentos.  
  
4. En el código de procedimiento, utilice el nombre de parámetro para asignar un valor para el elemento subyacente en el código de llamada.  
  
 Vea el ejemplo más abajo para ver una demostración.  
  
## <a name="changing-local-copies"></a>Cambiar las copias locales  
 Si el elemento subyacente en el código de llamada es un elemento no modificable, o si se pasa el argumento `ByVal`, el procedimiento no puede cambiar su valor en el código de llamada. Sin embargo, el procedimiento puede cambiar su copia local de dicho argumento.  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a>Para cambiar la copia de un argumento de procedimiento en el código de procedimiento  
  
1. En la declaración de procedimiento, especifique [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) para el parámetro correspondiente al argumento.  
  
     -o bien-  
  
     En el código que realiza la llamada, incluya el argumento entre paréntesis en la lista de argumentos. Esto obligará a Visual Basic para pasar el argumento por valor, incluso si se especifica el parámetro correspondiente `ByRef`.  
  
2. En el código de procedimiento, utilice el nombre del parámetro para asignar un valor a la copia local del argumento. No se cambia el valor subyacente en el código de llamada.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra dos procedimientos que toman una variable de matriz y operan en sus elementos. El `increase` procedimiento simplemente agrega uno a cada elemento. El `replace` procedimiento asigna una nueva matriz al parámetro `a()` y, a continuación, agrega uno a cada elemento.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#36)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 La primera `MsgBox` llamada a muestra "después de Increase (n): 11, 21, 31, 41". Dado que la matriz `n` es un tipo de referencia, `replace` puede cambiar sus miembros, aunque es el mecanismo de paso `ByVal`.  
  
 El segundo `MsgBox` llamada a muestra "después de Replace (n): 101, 201, 301". Dado que `n` se pasa `ByRef`, `replace` puede modificar la variable `n` en el código de llamada y asignar una nueva matriz a él. Dado que `n` es un tipo de referencia, `replace` también se puede cambiar sus miembros.  
  
 Puede impedir que el procedimiento modificar la variable en el código de llamada. Vea [Cómo: Proteger un argumento de procedimiento contra cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md).  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Cuando se pasa una variable por referencia, debe usar el `ByRef` palabra clave para especificar este mecanismo.  
  
 El valor predeterminado en Visual Basic consiste en pasar argumentos por valor. Sin embargo, es buena práctica para incluir cualquiera de programación la [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) palabra clave con cada parámetro declarado. Esto hace que el código más fácil de leer.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Siempre hay un riesgo potencial de permitir que un procedimiento cambiar el valor subyacente a un argumento en el código de llamada. Asegúrese de que se espera que este valor se puede cambiar, y estar preparado para comprobar su validez antes de usarlo.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Filtrar para pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)
- [Pasar argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Diferencias entre argumentos modificables y no modificables](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Filtrar para proteger un argumento de procedimiento para que no se realicen cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Filtrar para forzar un argumento para que pase como un valor](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Pasar argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)
- [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
