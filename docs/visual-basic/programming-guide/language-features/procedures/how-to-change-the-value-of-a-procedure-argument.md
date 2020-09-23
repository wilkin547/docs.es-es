---
title: Procedimiento para cambiar el valor de un argumento de procedimiento
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
ms.openlocfilehash: 9960dacc053c5dc8d8cfdfd6eaa0ea3258ed0fea
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077077"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a>Cómo: Cambiar el valor de un argumento de procedimiento (Visual Basic)

Cuando se llama a un procedimiento, cada argumento proporcionado corresponde a uno de los parámetros definidos en el procedimiento. En algunos casos, el código de procedimiento puede cambiar el valor subyacente de un argumento en el código de llamada. En otros casos, el procedimiento solo puede cambiar su copia local de un argumento.  
  
 Cuando se llama al procedimiento, Visual Basic crea una copia local de todos los argumentos que se pasan por [ByVal](../../../language-reference/modifiers/byval.md). Para cada argumento pasado [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic proporciona al código de procedimiento una referencia directa al elemento de programación subyacente al argumento en el código de llamada.  
  
 Si el elemento subyacente del código de llamada es un elemento modificable y se pasa el argumento `ByRef` , el código de procedimiento puede utilizar la referencia directa para cambiar el valor del elemento en el código de llamada.  
  
## <a name="changing-the-underlying-value"></a>Cambiar el valor subyacente  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a>Para cambiar el valor subyacente de un argumento de procedimiento en el código de llamada  
  
1. En la declaración de procedimiento, especifique [ByRef](../../../language-reference/modifiers/byref.md) para el parámetro correspondiente al argumento.  
  
2. En el código de llamada, pase un elemento de programación modificable como argumento.  
  
3. En el código de llamada, no incluya el argumento entre paréntesis en la lista de argumentos.  
  
4. En el código de procedimiento, use el nombre de parámetro para asignar un valor al elemento subyacente en el código de llamada.  
  
 Vea el ejemplo más adelante para obtener una demostración.  
  
## <a name="changing-local-copies"></a>Cambiar copias locales  

 Si el elemento subyacente del código de llamada es un elemento no modificable, o si se pasa el argumento `ByVal` , el procedimiento no puede cambiar su valor en el código de llamada. Sin embargo, el procedimiento puede cambiar su copia local de este tipo de argumento.  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a>Para cambiar la copia de un argumento de procedimiento en el código de procedimiento  
  
1. En la declaración de procedimiento, especifique [ByVal](../../../language-reference/modifiers/byval.md) para el parámetro correspondiente al argumento.  
  
     o bien  
  
     En el código de llamada, incluya el argumento entre paréntesis en la lista de argumentos. Esto obliga a Visual Basic a pasar el argumento por valor, incluso si el parámetro correspondiente especifica `ByRef` .  
  
2. En el código del procedimiento, use el nombre del parámetro para asignar un valor a la copia local del argumento. No se cambia el valor subyacente en el código de llamada.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestran dos procedimientos que toman una variable de matriz y operan en sus elementos. El `increase` procedimiento simplemente agrega uno a cada elemento. El `replace` procedimiento asigna una nueva matriz al parámetro `a()` y, a continuación, agrega una a cada elemento.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#36)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 La primera `MsgBox` llamada muestra "después del aumento (n): 11, 21, 31, 41". Dado que la matriz `n` es un tipo de referencia, `replace` puede cambiar sus miembros, aunque el mecanismo de paso sea `ByVal` .  
  
 La segunda `MsgBox` llamada muestra "After Replace (n): 101, 201, 301". Dado `n` que se pasa `ByRef` , `replace` puede modificar la variable `n` en el código de llamada y asignarle una nueva matriz. Dado `n` que es un tipo de referencia, `replace` también puede cambiar sus miembros.  
  
 Puede evitar que el procedimiento modifique la variable en el código de llamada. Consulte [Cómo: proteger un argumento de procedimiento contra cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md).  
  
## <a name="compile-the-code"></a>Compilar el código  

 Al pasar una variable por referencia, debe usar la `ByRef` palabra clave para especificar este mecanismo.  
  
 De forma predeterminada, en Visual Basic es pasar argumentos por valor. Sin embargo, es aconsejable incluir la palabra clave [ByVal](../../../language-reference/modifiers/byval.md) o [ByRef](../../../language-reference/modifiers/byref.md) con cada parámetro declarado. Esto hace que el código sea más fácil de leer.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  

 Siempre existe un riesgo potencial en permitir que un procedimiento cambie el valor subyacente de un argumento en el código de llamada. Asegúrese de que espera que se cambie este valor y prepárese para comprobar su validez antes de usarlo.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Procedimiento para pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)
- [Pasar argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Diferencias entre argumentos modificables y no modificables](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Procedimiento para proteger un argumento de procedimiento para que no se realicen cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Procedimiento para forzar un argumento para que pase como un valor](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Paso de argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)
- [Tipos de valor y tipos de referencia](../data-types/value-types-and-reference-types.md)
