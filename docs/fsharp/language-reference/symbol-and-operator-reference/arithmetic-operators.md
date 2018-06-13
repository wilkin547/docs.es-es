---
title: Operadores aritméticos (F#)
description: 'Obtenga información acerca de los operadores aritméticos que están disponibles en el lenguaje de programación de F #.'
ms.date: 04/04/2018
ms.openlocfilehash: ead0bbd7fdad528b322f99eaf0f73638f060eb51
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565943"
---
# <a name="arithmetic-operators"></a>Operadores aritméticos

Este tema describe los operadores aritméticos que están disponibles en el lenguaje F #.

## <a name="summary-of-binary-arithmetic-operators"></a>Resumen de operadores aritméticos binarios
En la tabla siguiente se resume los operadores aritméticos binarios que están disponibles para tipos enteros y de punto flotante conversión unboxing.

|Operador binario|Notas|
|---------------|-----|
|`+` (suma, más)|No está activada. Puede producirse desbordamiento cuando se suman los números y la suma supera el valor absoluto máximo admitido por el tipo.|
|`-` (resta, menos)|No está activada. Puede producirse un subdesbordamiento al restan tipos sin signo o cuando son demasiado pequeños para ser representado por el tipo de valores de punto flotante.|
|`*` (multiplicación, por)|No está activada. Puede producirse desbordamiento cuando los números se multiplican y el producto supera el valor absoluto máximo admitido por el tipo.|
|`/` (división, dividido por)|División por cero, se produce un <xref:System.DivideByZeroException> para los tipos enteros. Para tipos de punto flotante, división por cero da los valores de punto flotante especiales `+Infinity` o `-Infinity`. También hay una condición de subdesbordamiento posibles cuando un número de punto flotante es demasiado pequeño para representarlo mediante el tipo.|
|`%` (resto, rem)|Devuelve el resto de una operación de división. El signo del resultado es el mismo que el signo del primer operando.|
|`**` (a la potencia de exponenciación)|Puede producirse desbordamiento cuando el resultado supera el máximo valor absoluto para el tipo.<br /><br />El operador de exponenciación solo funciona con tipos de punto flotante.|

## <a name="summary-of-unary-arithmetic-operators"></a>Resumen de los operadores aritméticos unarios
En la tabla siguiente se resume los operadores aritméticos unarios que están disponibles para tipos enteros y de punto flotante.


|Operador unario|Notas|
|--------------|-----|
|`+` (positivo)|Puede aplicarse a cualquier expresión aritmética. No cambia el signo del valor.|
|`-` (negación, negativo)|Puede aplicarse a cualquier expresión aritmética. Cambia el signo del valor.|
Es el comportamiento en el desbordamiento o subdesbordamiento de tipos enteros se ajuste alrededor. Esto hace que un resultado incorrecto. Desbordamiento de enteros es un problema potencialmente grave que puede contribuir a problemas de seguridad cuando software no se escribe en la cuenta para el mismo. Si se trata de un problema para la aplicación, considere la posibilidad de usar los operadores en `Microsoft.FSharp.Core.Operators.Checked`.


## <a name="summary-of-binary-comparison-operators"></a>Resumen de operadores de comparación binaria
La siguiente tabla muestra los operadores de comparación binaria que están disponibles para tipos enteros y de punto flotante. Estos operadores devuelven valores de tipo `bool`.

Números de punto flotante no deben compararse nunca directamente para la igualdad, ya que la representación de punto flotante de IEEE no admite una operación de igualdad exacta. Dos números que se pueden comprobar fácilmente para que sea igual al examinar el código podrían tener realmente diferentes representaciones de bits.



|Operador|Notas|
|--------|-----|
|`=` (igualdad, igual a)|Esto no es un operador de asignación. Se usa únicamente para la comparación. Se trata de un operador genérico.|
|`>` (mayor que)|Se trata de un operador genérico.|
|`<` (menor que)|Se trata de un operador genérico.|
|`>=` (mayor o igual que)|Se trata de un operador genérico.|
|`<=` (menor o igual que)|Se trata de un operador genérico.|
|`<>` (no es igual)|Se trata de un operador genérico.|

## <a name="overloaded-and-generic-operators"></a>Operadores sobrecargados y genéricos
Todos los operadores descritos en este tema se definen en el **Microsoft.FSharp.Core.Operators** espacio de nombres. Algunos de los operadores se definen mediante el uso de parámetros de tipo resueltos estáticamente. Esto significa que hay definiciones individuales para cada tipo específico que funciona con ese operador. Todos los operadores unarios y binarios aritméticos y bit a bit se encuentran en esta categoría. Los operadores de comparación son genéricos y, por tanto, funcionan con cualquier tipo, no solo primitivos tipos aritméticos. Unión discriminada y tipos de registro tienen sus propias implementaciones personalizadas generadas por el compilador de F #. Tipos de clase usan el método <xref:System.Object.Equals%2A>.

Los operadores genéricos son personalizables. Para personalizar las funciones de comparación, invalidar <xref:System.Object.Equals%2A> para proporcionar su propios comparación de igualdad personalizada y, a continuación, implementar <xref:System.IComparable>. El <xref:System.IComparable?displayProperty=nameWithType> interfaz tiene un método único, el <xref:System.IComparable.CompareTo%2A> método.


## <a name="operators-and-type-inference"></a>Inferencia de tipos y operadores
El uso de un operador en una expresión restringe la inferencia de tipos en ese operador. Además, el uso de operadores impide la generalización automática, ya que el uso de operadores implica un tipo aritmético. En ausencia de cualquier otra información, el compilador de F # infiere `int` como el tipo de expresiones aritméticas. Puede invalidar este comportamiento mediante la especificación de otro tipo. Por lo tanto los tipos de argumento y el tipo de valor devuelto de `function1` en el código siguiente se deducen como `int`, pero los tipos de `function2` se deducen como `float`.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3501.fs)]
    
## <a name="see-also"></a>Vea también
[Referencia de símbolos y operadores](index.md)

[Sobrecarga de operadores](../operator-overloading.md)

[Operadores bit a bit](bitwise-operators.md)

[Operadores booleanos](boolean-operators.md)
