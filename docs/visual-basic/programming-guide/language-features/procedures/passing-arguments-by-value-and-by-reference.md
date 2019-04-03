---
title: Pasar argumentos por valor y por referencia (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- passing arguments [Visual Basic], by value or by reference
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing [Visual Basic], by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
ms.openlocfilehash: c23ca51322f57dc13a85c3ea94e0d335dc50ca13
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830362"
---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a>Pasar argumentos por valor y por referencia (Visual Basic)
En Visual Basic, puede pasar un argumento a un procedimiento *por valor* o *por referencia*. Esto se conoce como el *mecanismo para pasar*, y determina si el procedimiento puede modificar el elemento de programación subyacente del argumento en el código de llamada. La declaración de procedimiento determina el mecanismo de paso para cada parámetro especificando el [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) palabra clave.  
  
## <a name="distinctions"></a>Diferencias  
 Cuando se pasa un argumento a un procedimiento, tenga en distintas condiciones que interactúan entre sí:  
  
-   Si el elemento de programación subyacente es modificable o no modificable  
  
-   Si el propio argumento es modificable o no modificable  
  
-   Si el argumento que se ha pasado por valor o por referencia  
  
-   Si el tipo de datos del argumento es un tipo de valor o un tipo de referencia  
  
 Para obtener más información, consulte [argumentos modificables y las diferencias entre modificable](./differences-between-modifiable-and-nonmodifiable-arguments.md) y [las diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## <a name="choice-of-passing-mechanism"></a>Elección del mecanismo para pasar argumentos  
 Debe elegir el mecanismo de paso con cuidado para cada argumento.  
  
-   **Protección**. Elegir entre los mecanismos de dos paso, el criterio más importante es la exposición de una llamada a las variables a cambiar. La ventaja de pasar un argumento `ByRef` es que el procedimiento puede devolver un valor para el código que realiza la llamada a través de ese argumento. La ventaja de pasar un argumento `ByVal` es que evita que una variable que se está cambiando el procedimiento.  
  
-   **Rendimiento**. Aunque el mecanismo de paso puede afectar al rendimiento del código, la diferencia es suele ser insignificante. Una excepción a esto es un tipo de valor pasado `ByVal`. En este caso, Visual Basic copia todo el contenido datos del argumento. Por lo tanto, para un tipo de valor grande, como una estructura, puede ser más eficaz para pasarlo `ByRef`.  
  
     Tipos de referencia, sólo el puntero a los datos es copiados (cuatro bytes en plataformas de 32 bits, ocho bytes en plataformas de 64 bits). Por lo tanto, puede pasar argumentos de tipo `String` o `Object` por valor sin perjudicar al rendimiento.  
  
## <a name="determination-of-the-passing-mechanism"></a>Determinación del mecanismo de paso  
 La declaración de procedimiento especifica el mecanismo de paso para cada parámetro. El código de llamada no se puede invalidar un `ByVal` mecanismo.  
  
 Si se declara un parámetro con `ByRef`, el código de llamada puede forzar el mecanismo para `ByVal` , incluya el nombre del argumento entre paréntesis en la llamada. Para obtener más información, vea [Cómo: Forzar un argumento para pasar por valor](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
 El valor predeterminado en Visual Basic consiste en pasar argumentos por valor.  
  
## <a name="when-to-pass-an-argument-by-value"></a>Cuándo se debe pasar un argumento por valor  
  
-   Si el elemento de código que realiza la llamada subyacente del argumento es un elemento no modificable, declare el parámetro correspondiente [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Ningún código puede cambiar el valor de un elemento no modificable.  
  
-   Si el elemento subyacente es modificable, pero no desea que el procedimiento para que pueda cambiar su valor, declare el parámetro `ByVal`. Solo el código de llamada puede cambiar el valor de un elemento modificable que se pasan por valor.  
  
## <a name="when-to-pass-an-argument-by-reference"></a>Cuándo se debe pasar un argumento por referencia  
  
-   Si el procedimiento tiene necesidad de cambiar el elemento subyacente en el código que realiza la llamada original, declare el parámetro correspondiente [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).  
  
-   Si depende de la correcta ejecución del código en el procedimiento cambia el elemento subyacente en el código de llamada, declare el parámetro `ByRef`. Si se pasa por valor, o si el código de llamada reemplaza el `ByRef` mecanismo que pasa, incluya el argumento entre paréntesis, la llamada a procedimiento podría producir resultados inesperados.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 El ejemplo siguiente muestra cuándo se debe pasar argumentos por valor y cuándo se debe pasar por referencia. Procedimiento `Calculate` tiene tanto un `ByVal` y un `ByRef` parámetro. Dada una tasa de interés, `rate`y una cantidad de dinero, `debt`, la tarea del procedimiento consiste en calcular un nuevo valor para `debt` que es el resultado de aplicar la tasa de interés para el valor original de `debt`. Dado que `debt` es un `ByRef` parámetro, el nuevo total se refleja en el valor del argumento en el código de llamada que se corresponde con `debt`. Parámetro `rate` es un `ByVal` parámetro porque `Calculate` no debe cambiar su valor.  
  
### <a name="code"></a>Código  
 [!code-vb[VbVbcnProcedures#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class2.vb#74)]  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Cómo: Pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)
- [Cómo: Cambie el valor de un argumento de procedimiento](./how-to-change-the-value-of-a-procedure-argument.md)
- [Cómo: Proteger un argumento de procedimiento contra cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Cómo: Forzar un argumento para pasar por valor](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Paso de argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
