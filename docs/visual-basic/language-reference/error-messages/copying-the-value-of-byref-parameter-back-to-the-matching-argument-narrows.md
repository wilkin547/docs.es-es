---
title: La acción de volver a copiar el valor del parámetro 'ByRef' '<parametername>' en el argumento coincidente restringe del tipo '<typename1>' al tipo '<typename2>'
ms.date: 07/20/2015
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
ms.openlocfilehash: b9a38d3eb4e25d5c9ac765adf47df72e45fd082a
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160937"
---
# <a name="bc32053-copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument-narrows-from-type-typename1-to-type-typename2"></a>BC32053: al volver a copiar el valor del parámetro ' ByRef ' ' \<parametername> ' en el argumento coincidente, se reduce el tipo ' \<typename1> ' al tipo ' \<typename2> '

Se llama a un procedimiento con un argumento que se amplía al tipo de parámetro correspondiente, y la conversión del parámetro al argumento es de restricción.

 Al definir una clase o estructura, puede definir uno o varios operadores de conversión para convertir ese tipo de clase o estructura a otros tipos. También puede definir operadores de conversión inversos para convertir esos otros tipos de nuevo a su clase o tipo de estructura. Cuando se usa el tipo de clase o estructura en una llamada a procedimiento, Visual Basic puede usar estos operadores de conversión para convertir el tipo de un argumento al tipo de su parámetro correspondiente.

 Si pasa el argumento [ByRef](../modifiers/byref.md), Visual Basic a veces copia el valor del argumento en una variable local en el procedimiento en lugar de pasar una referencia. En tal caso, cuando el procedimiento vuelve, Visual Basic debe copiar de nuevo el valor de la variable local en el argumento del código de llamada.

 Si un valor de argumento `ByRef` se copia en el procedimiento y el argumento y el parámetro son del mismo tipo, no es necesario realizar ninguna conversión. Pero si los tipos son diferentes, Visual Basic debe convertir en ambas direcciones. Si uno de los tipos es su tipo de clase o estructura, Visual Basic debe convertir ambos en y desde el otro tipo. Si una de estas conversiones es la ampliación, la conversión inversa podría estar restringida.

 **Identificador de error:** BC32053

## <a name="to-correct-this-error"></a>Para corregir este error

- Si es posible, use un argumento de llamada del mismo tipo que el parámetro de procedimiento, por lo que Visual Basic no necesita realizar ninguna conversión.

- Si necesita llamar al procedimiento con un argumento de tipo diferente del tipo de parámetro pero no es necesario devolver un valor al argumento de llamada, defina el parámetro para que sea [ByVal](../modifiers/byval.md) en lugar de `ByRef`.

- Si necesita devolver un valor al argumento de llamada, defina el operador de conversión inversa como [ampliación](../modifiers/widening.md), si es posible.

## <a name="see-also"></a>Vea también

- [Procedimientos](../../programming-guide/language-features/procedures/index.md)
- [Argumentos y parámetros de procedimiento](../../programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Pasar argumentos por valor y por referencia](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [Procedimientos de operador](../../programming-guide/language-features/procedures/operator-procedures.md)
- [Operator Statement](../statements/operator-statement.md)
- [Procedimiento para definir un operador](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Procedimiento para definir un operador de conversión](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Conversiones de tipos en Visual Basic](../../programming-guide/language-features/data-types/type-conversions.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
