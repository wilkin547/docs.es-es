---
title: 'Cómo: Cambiar el valor de un argumento de procedimiento'
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
ms.openlocfilehash: deac87ca4690990a4d00f63d0ea9b843c3f9a9c4
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344485"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a>Cómo: Cambiar el valor de un argumento de procedimiento (Visual Basic)
Cuando se llama a un procedimiento, cada argumento proporcionado corresponde a uno de los parámetros definidos en el procedimiento. En algunos casos, el código de procedimiento puede cambiar el valor subyacente de un argumento en el código de llamada. En otros casos, el procedimiento solo puede cambiar su copia local de un argumento.  
  
 Cuando se llama al procedimiento, Visual Basic crea una copia local de todos los argumentos que se pasan por [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Para cada argumento pasado [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic proporciona al código de procedimiento una referencia directa al elemento de programación subyacente al argumento en el código de llamada.  
  
 Si el elemento subyacente del código de llamada es un elemento modificable y el argumento se pasa `ByRef`, el código de procedimiento puede utilizar la referencia directa para cambiar el valor del elemento en el código de llamada.  
  
## <a name="changing-the-underlying-value"></a>Cambiar el valor subyacente  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a>Para cambiar el valor subyacente de un argumento de procedimiento en el código de llamada  
  
1. En la declaración de procedimiento, especifique [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) para el parámetro correspondiente al argumento.  
  
2. En el código de llamada, pase un elemento de programación modificable como argumento.  
  
3. En el código de llamada, no incluya el argumento entre paréntesis en la lista de argumentos.  
  
4. En el código de procedimiento, use el nombre de parámetro para asignar un valor al elemento subyacente en el código de llamada.  
  
 Vea el ejemplo más adelante para obtener una demostración.  
  
## <a name="changing-local-copies"></a>Cambiar copias locales  
 Si el elemento subyacente del código de llamada es un elemento no modificable, o si se pasa el argumento `ByVal`, el procedimiento no puede cambiar su valor en el código de llamada. Sin embargo, el procedimiento puede cambiar su copia local de este tipo de argumento.  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a>Para cambiar la copia de un argumento de procedimiento en el código de procedimiento  
  
1. En la declaración de procedimiento, especifique [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) para el parámetro correspondiente al argumento.  
  
     O bien,  
  
     En el código de llamada, incluya el argumento entre paréntesis en la lista de argumentos. Esto obliga a Visual Basic a pasar el argumento por valor, incluso si el parámetro correspondiente especifica `ByRef`.  
  
2. En el código del procedimiento, use el nombre del parámetro para asignar un valor a la copia local del argumento. No se cambia el valor subyacente en el código de llamada.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestran dos procedimientos que toman una variable de matriz y operan en sus elementos. El procedimiento `increase` simplemente agrega uno a cada elemento. El procedimiento `replace` asigna una nueva matriz al parámetro `a()` y, a continuación, agrega una a cada elemento.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#36)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 La primera llamada a `MsgBox` muestra "después del aumento (n): 11, 21, 31, 41". Dado que la matriz `n` es un tipo de referencia, `replace` puede cambiar sus miembros, aunque se `ByVal`el mecanismo de paso.  
  
 La segunda llamada a `MsgBox` muestra "After Replace (n): 101, 201, 301". Dado que `n` se pasa `ByRef`, `replace` puede modificar la variable `n` en el código de llamada y asignarle una nueva matriz. Dado que `n` es un tipo de referencia, `replace` también puede cambiar sus miembros.  
  
 Puede evitar que el procedimiento modifique la variable en el código de llamada. Consulte [Cómo: proteger un argumento de procedimiento contra cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md).  
  
## <a name="compile-the-code"></a>Compilar el código  
 Al pasar una variable por referencia, debe usar la palabra clave `ByRef` para especificar este mecanismo.  
  
 De forma predeterminada, en Visual Basic es pasar argumentos por valor. Sin embargo, es aconsejable incluir la palabra clave [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) con cada parámetro declarado. Esto hace que el código sea más fácil de leer.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Siempre existe un riesgo potencial en permitir que un procedimiento cambie el valor subyacente de un argumento en el código de llamada. Asegúrese de que espera que se cambie este valor y prepárese para comprobar su validez antes de usarlo.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)
- [Paso de argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Diferencias entre argumentos modificables y no modificables](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Proteger un argumento de procedimiento para que no se realicen cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Forzar un argumento para que pase como un valor](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Paso de argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
