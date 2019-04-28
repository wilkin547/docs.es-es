---
title: La acción de volver a copiar el valor del parámetro 'ByRef' '<parametername>' en el argumento coincidente restringe del tipo '<typename1>' al tipo '<typename2>'
ms.date: 07/20/2015
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
ms.openlocfilehash: fa8607bf72dfb344048ec82514182dcb6810274d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803862"
---
# <a name="copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument-narrows-from-type-typename1-to-type-typename2"></a>Copiar el valor del parámetro 'ByRef' '\<parametername >' en el argumento coincidente restringe del tipo '\<typename1 >' al tipo '\<nombredetipo2 >'
Se llama a un procedimiento con un argumento que se amplía al tipo de parámetro correspondiente, y la conversión de parámetro para el argumento es de restricción.  
  
 Al definir una clase o estructura, puede definir uno o varios operadores de conversión para convertir ese tipo de clase o estructura a otros tipos. También puede definir operadores de conversión inversos para convertir esos otros tipos de nuevo a su clase o tipo de estructura. Cuando se usa el tipo de clase o estructura en una llamada a procedimiento, Visual Basic puede utilizar estos operadores de conversión para convertir al tipo de un argumento al tipo del parámetro correspondiente.  
  
 Si se pasa el argumento [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic a veces copia el valor del argumento en una variable local en el procedimiento en lugar de pasar una referencia. En tal caso, cuando el procedimiento vuelve, Visual Basic debe, a continuación, copiar el valor de la variable local en el argumento en el código de llamada.  
  
 Si un valor de argumento `ByRef` se copia en el procedimiento y el argumento y el parámetro son del mismo tipo, no es necesario realizar ninguna conversión. Pero si los tipos son diferentes, Visual Basic debe convertir en ambas direcciones. Si uno de los tipos es su tipo de clase o estructura, Visual Basic debe convertir a y desde el otro tipo. Si es una de estas conversiones de ampliación, la conversión inversa podría ser de restricción.  
  
 **Identificador de error:** BC32053  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Si es posible, utilice un argumento de llamada del mismo tipo como el parámetro de procedimiento, por lo que no es necesario realizar ninguna conversión de Visual Basic.  
  
- Si necesita llamar al procedimiento con un argumento de tipo diferente del tipo de parámetro pero no es necesario devolver un valor al argumento de llamada, defina el parámetro para que sea [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) en lugar de `ByRef`.  
  
- Si tiene que devolver un valor al argumento de llamada, defina el operador de conversión inversa como [Widening](../../../visual-basic/language-reference/modifiers/widening.md), si es posible.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Argumentos y parámetros de procedimiento](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Paso de argumentos por valor y por referencia](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [Procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Cómo: Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Cómo: Definir un operador de conversión](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Conversiones de tipos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
