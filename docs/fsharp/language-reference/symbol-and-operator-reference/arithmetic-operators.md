---
title: Operadores aritméticos (F#)
description: Obtenga información sobre los operadores aritméticos que están disponibles en el F# lenguaje de programación.
ms.date: 04/04/2018
ms.openlocfilehash: 2c0e2e25a4f79d00455d978e235e4bef16b52586
ms.sourcegitcommit: 6ae7cdd0437a32884556dd4826ca90e957b7a4e3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2018
ms.locfileid: "45597445"
---
# <a name="arithmetic-operators"></a>Operadores aritméticos

En este tema se describe los operadores aritméticos que están disponibles en el F# lenguaje.

## <a name="summary-of-binary-arithmetic-operators"></a>Resumen de operadores aritméticos binarios

En la tabla siguiente se resume los operadores aritméticos binarios que están disponibles para los tipos de punto flotante e integrales conversión unboxing.

|Operador binario|Notas|
|---------------|-----|
|`+` (Además, además de)|Desactivada. Condición del desbordamiento posibles cuando se suman los números y la suma supera el valor absoluto máximo admitido por el tipo.|
|`-` (resta, menos)|Desactivada. Puede producirse un subdesbordamiento cuando se restan tipos sin signo, o cuando son demasiado pequeños para ser representado por el tipo de valores de punto flotante.|
|`*` (multiplicación, veces)|Desactivada. Posible desbordamiento cuando se multiplican los números de producto supera el valor absoluto máximo admitido por el tipo.|
|`/` (división, dividido por)|División por cero, se produce un <xref:System.DivideByZeroException> para los tipos enteros. Para tipos de punto flotante, división por cero proporciona a los valores de punto flotante especiales `+Infinity` o `-Infinity`. También hay una condición de subdesbordamiento posibles cuando es demasiado pequeño para representarlo mediante el tipo de un número de punto flotante.|
|`%` (resto, rem)|Devuelve el resto de una operación de división. El signo del resultado es el mismo que el inicio de sesión del primer operando.|
|`**` (a la potencia de exponenciación)|Posible desbordamiento cuando el resultado supera el máximo valor absoluto para el tipo.<br /><br />El operador de exponenciación solo funciona con tipos de punto flotante.|

## <a name="summary-of-unary-arithmetic-operators"></a>Resumen de operadores aritméticos unarios

En la tabla siguiente se resume los operadores aritméticos unarios que están disponibles para los tipos enteros y de punto flotante.

|Operador unario|Notas|
|--------------|-----|
|`+` (positivo)|Pueden aplicarse a cualquier expresión aritmética. No cambia el signo del valor.|
|`-` (negación, negativo)|Pueden aplicarse a cualquier expresión aritmética. Cambia el signo del valor.|

Es el comportamiento de desbordamiento o subdesbordamiento de tipos enteros ajustarlo. Esto hace que un resultado incorrecto. Desbordamiento de enteros es un problema potencialmente grave que puede contribuir a problemas de seguridad cuando software no se escribe en la cuenta para él. Si esto constituye un problema para la aplicación, considere la posibilidad de usar los operadores en `Microsoft.FSharp.Core.Operators.Checked`.

## <a name="summary-of-binary-comparison-operators"></a>Resumen de operadores de comparación binaria

En la tabla siguiente se muestra los operadores de comparación binaria que están disponibles para los tipos enteros y de punto flotante. Estos operadores devuelven valores de tipo `bool`.

Números de punto flotante no deben compararse nunca directamente para la igualdad, porque la representación de punto flotante de IEEE no admite una operación de igualdad exacta. Dos números que se pueden comprobar fácilmente para que sea igual al inspeccionar el código realmente podrían tener diferentes representaciones de bits.

|Operador|Notas|
|--------|-----|
|`=` (igualdad, igual a)|Esto no es un operador de asignación. Se usa para la comparación. Se trata de un operador genérico.|
|`>` (mayor que)|Se trata de un operador genérico.|
|`<` (menor que)|Se trata de un operador genérico.|
|`>=` (mayor o igual que)|Se trata de un operador genérico.|
|`<=` (menor o igual que)|Se trata de un operador genérico.|
|`<>` (no igual)|Se trata de un operador genérico.|

## <a name="overloaded-and-generic-operators"></a>Operadores sobrecargados y genéricos

Todos los operadores descritos en este tema se definen en el **Microsoft.FSharp.Core.Operators** espacio de nombres. Algunos de los operadores se definen mediante el uso de parámetros de tipo resueltos estáticamente. Esto significa que hay definiciones individuales para cada tipo específico que funcione con ese operador. Todos los operadores unarios y binarios aritméticos y bit a bit son de esta categoría. Los operadores de comparación son genéricos y, por tanto, funcionan con cualquier tipo, primitivos no solo tipos aritméticos. Tipos de registro y de unión discriminada tienen sus propias implementaciones personalizadas generadas por el F# compilador. Tipos de clase usan el método <xref:System.Object.Equals%2A>.

Los operadores genéricos son personalizables. Para personalizar las funciones de comparación, invalidar <xref:System.Object.Equals%2A> para proporcionar su propia comparación de igualdad personalizada y, a continuación, implementar <xref:System.IComparable>. El <xref:System.IComparable?displayProperty=nameWithType> interfaz tiene un método único, el <xref:System.IComparable.CompareTo%2A> método.

## <a name="operators-and-type-inference"></a>Inferencia de tipos y operadores

El uso de un operador en una expresión restringe la inferencia de tipos en ese operador. Además, el uso de operadores impide la generalización automática, ya que el uso de operadores implica un tipo aritmético. En ausencia de cualquier otra información, el F# deduce el compilador `int` como el tipo de expresiones aritméticas. Puede invalidar este comportamiento mediante la especificación de otro tipo. Por lo tanto los tipos de argumento y el tipo de valor devuelto de `function1` en el código siguiente se infiere para ser `int`, pero los tipos de `function2` se infiere para ser `float`.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3501.fs)]

## <a name="see-also"></a>Vea también

- [Referencia de símbolos y operadores](index.md)
- [Sobrecarga de operadores](../operator-overloading.md)
- [Operadores bit a bit](bitwise-operators.md)
- [Operadores booleanos](boolean-operators.md)
