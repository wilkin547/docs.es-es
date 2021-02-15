---
description: Más información acerca de cómo pasar argumentos por valor y por referencia (Visual Basic)
title: Pasar argumentos por valor y por referencia
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- passing arguments [Visual Basic], by value or by reference
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing [Visual Basic], by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
ms.openlocfilehash: dbe020a7fffd48c14d377fff740f57e4bcc43ed2
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466684"
---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a>Pasar argumentos por valor y por referencia (Visual Basic)

En Visual Basic, puede pasar un argumento a un procedimiento *por valor* o *por referencia*. Esto se conoce como *mecanismo de paso* y determina si el procedimiento puede modificar el elemento de programación subyacente al argumento en el código de llamada. La declaración de procedimiento determina el mecanismo de paso de cada parámetro especificando la palabra clave [ByVal](../../../language-reference/modifiers/byval.md) o [ByRef](../../../language-reference/modifiers/byref.md) .  
  
## <a name="distinctions"></a>Diferencias  

 Al pasar un argumento a un procedimiento, tenga en cuenta varias distinciones diferentes que interactúan entre sí:  
  
- Si el elemento de programación subyacente es modificable o no modificable  
  
- Si el propio argumento es modificable o no modificable  
  
- Si el argumento se pasa por valor o por referencia  
  
- Si el tipo de datos del argumento es un tipo de valor o un tipo de referencia  
  
 Para obtener más información, vea [diferencias entre argumentos modificables y no modificables](./differences-between-modifiable-and-nonmodifiable-arguments.md) y [diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## <a name="choice-of-passing-mechanism"></a>Elección del mecanismo de paso  

 Debe elegir cuidadosamente el mecanismo de paso para cada argumento.  
  
- **Protección**. Al elegir entre los dos mecanismos de paso, el criterio más importante es la exposición de las variables de llamada que se van a cambiar. La ventaja de pasar un argumento `ByRef` es que el procedimiento puede devolver un valor al código de llamada a través de ese argumento. La ventaja de pasar un argumento `ByVal` es que impide que el procedimiento cambie una variable.  
  
- **Rendimiento**. Aunque el mecanismo de paso puede afectar al rendimiento del código, la diferencia suele ser insignificante. Una excepción es un tipo de valor que se pasa `ByVal` . En este caso, Visual Basic copia todo el contenido de los datos del argumento. Por lo tanto, para un tipo de valor grande, como una estructura, puede ser más eficaz pasarlo `ByRef` .  
  
     En el caso de los tipos de referencia, solo se copia el puntero a los datos (cuatro bytes en las plataformas de 32 bits, ocho bytes en las plataformas de 64 bits). Por lo tanto, puede pasar argumentos de tipo `String` o `Object` por valor sin dañar el rendimiento.  
  
## <a name="determination-of-the-passing-mechanism"></a>Determinación del mecanismo de paso  

 La declaración de procedimiento especifica el mecanismo de paso de cada parámetro. El código de llamada no puede invalidar un `ByVal` mecanismo.  
  
 Si un parámetro se declara con `ByRef` , el código de llamada puede forzar el mecanismo para que incluya `ByVal` el nombre del argumento entre paréntesis en la llamada. Para obtener más información, vea [Cómo: forzar un argumento para que se pase por valor](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
 De forma predeterminada, en Visual Basic es pasar argumentos por valor.  
  
## <a name="when-to-pass-an-argument-by-value"></a>Cuándo pasar un argumento por valor  
  
- Si el elemento de código de llamada subyacente al argumento es un elemento no modificable, declare el parámetro correspondiente [ByVal](../../../language-reference/modifiers/byval.md). Ningún código puede cambiar el valor de un elemento no modificable.  
  
- Si el elemento subyacente es modificable, pero no desea que el procedimiento pueda cambiar su valor, declare el parámetro `ByVal` . Solo el código de llamada puede cambiar el valor de un elemento modificable que se pasa por valor.  
  
## <a name="when-to-pass-an-argument-by-reference"></a>Cuándo pasar un argumento por referencia  
  
- Si el procedimiento tiene una necesidad genuina de cambiar el elemento subyacente en el código de llamada, declare el parámetro correspondiente [ByRef](../../../language-reference/modifiers/byref.md).  
  
- Si la ejecución correcta del código depende del procedimiento que cambia el elemento subyacente en el código de llamada, declare el parámetro `ByRef` . Si se pasa por valor, o si el código de llamada invalida el `ByRef` mecanismo de paso mediante la inclusión del argumento entre paréntesis, la llamada al procedimiento podría producir resultados inesperados.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  

 En el ejemplo siguiente se muestra Cuándo pasar argumentos por valor y cuándo pasarlos por referencia. `Calculate`El procedimiento tiene un `ByVal` parámetro y `ByRef` . Dado un tipo de interés, `rate` y una suma de dinero, `debt` , la tarea del procedimiento es calcular un nuevo valor para `debt` que es el resultado de aplicar el tipo de interés al valor original de `debt` . Dado `debt` que es un `ByRef` parámetro, el nuevo total se refleja en el valor del argumento en el código de llamada correspondiente a `debt` . `rate`El parámetro es un `ByVal` parámetro porque `Calculate` no debe cambiar su valor.  
  
### <a name="code"></a>Código  

 [!code-vb[VbVbcnProcedures#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class2.vb#74)]  
  
## <a name="see-also"></a>Consulte también

- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Procedimiento para pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)
- [Procedimiento para cambiar el valor de un argumento de procedimiento](./how-to-change-the-value-of-a-procedure-argument.md)
- [Procedimiento para proteger un argumento de procedimiento para que no se realicen cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Procedimiento para forzar un argumento para que pase como un valor](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Paso de argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)
- [Tipos de valor y tipos de referencia](../data-types/value-types-and-reference-types.md)
