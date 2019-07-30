---
title: Operadores aritméticos
description: Obtenga información acerca de los operadores aritméticos que están F# disponibles en el lenguaje de programación.
ms.date: 04/04/2018
ms.openlocfilehash: b783a0134541f11f06dde83af97676699b797da1
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630783"
---
# <a name="arithmetic-operators"></a>Operadores aritméticos

En este tema se describen los operadores aritméticos que F# están disponibles en el lenguaje.

## <a name="summary-of-binary-arithmetic-operators"></a>Resumen de operadores aritméticos binarios

En la tabla siguiente se resumen los operadores aritméticos binarios que están disponibles para los tipos enteros y de punto flotante con conversión unboxing.

|Operador binario|Notas|
|---------------|-----|
|`+`(suma, más)|Desactivada. Posible condición de desbordamiento cuando se suman números y la suma supera el valor absoluto máximo admitido por el tipo.|
|`-`(resta, menos)|Desactivada. Posible condición de subdesbordamiento cuando se restan tipos sin signo o cuando los valores de punto flotante son demasiado pequeños para representarlos mediante el tipo.|
|`*`(multiplicación, veces)|Desactivada. Posible condición de desbordamiento cuando se multiplican los números y el producto supera el valor absoluto máximo admitido por el tipo.|
|`/`(división, dividido por)|La división por cero produce <xref:System.DivideByZeroException> una para los tipos enteros. En el caso de los tipos de punto flotante, la división por cero le proporciona los `+Infinity` valores `-Infinity`de punto flotante especiales o. También hay una posible condición de subdesbordamiento cuando un número de punto flotante es demasiado pequeño para representarlo mediante el tipo.|
|`%`(resto, REM)|Devuelve el resto de una operación de división. El signo del resultado es el mismo que el del primer operando.|
|`**`(exponenciación, a la potencia de)|Posible condición de desbordamiento cuando el resultado supera el valor absoluto máximo para el tipo.<br /><br />El operador de exponenciación solo funciona con tipos de punto flotante.|

## <a name="summary-of-unary-arithmetic-operators"></a>Resumen de operadores aritméticos unarios

En la tabla siguiente se resumen los operadores aritméticos unarios que están disponibles para los tipos enteros y de punto flotante.

|Unario (operador)|Notas|
|--------------|-----|
|`+`positivo|Se puede aplicar a cualquier expresión aritmética. No cambia el signo del valor.|
|`-`(negación, negativo)|Se puede aplicar a cualquier expresión aritmética. Cambia el signo del valor.|

El comportamiento en caso de desbordamiento o subdesbordamiento para los tipos enteros es ajustar. Esto produce un resultado incorrecto. El desbordamiento de enteros es un problema potencialmente grave que puede contribuir a problemas de seguridad cuando no se escribe el software en su cuenta. Si esto supone un problema para su aplicación, considere la posibilidad de usar los `Microsoft.FSharp.Core.Operators.Checked`operadores comprobados en.

## <a name="summary-of-binary-comparison-operators"></a>Resumen de operadores de comparación binaria

En la tabla siguiente se muestran los operadores de comparación binarios que están disponibles para los tipos enteros y de punto flotante. Estos operadores devuelven valores `bool`de tipo.

Los números de punto flotante nunca deben compararse directamente para comprobar si son iguales, porque la representación de punto flotante de IEEE no admite una operación de igualdad exacta. Dos números que se pueden comprobar fácilmente para ser iguales mediante la inspección del código puede tener realmente representaciones de bits diferentes.

|Operador|Notas|
|--------|-----|
|`=`(igualdad, es igual a)|No es un operador de asignación. Se usa solo para la comparación. Este es un operador genérico.|
|`>`(mayor que)|Este es un operador genérico.|
|`<`(menor que)|Este es un operador genérico.|
|`>=`(mayor o igual que)|Este es un operador genérico.|
|`<=`(menor o igual que)|Este es un operador genérico.|
|`<>`(no igual)|Este es un operador genérico.|

## <a name="overloaded-and-generic-operators"></a>Operadores genéricos y sobrecargados

Todos los operadores descritos en este tema se definen en el espacio de nombres **Microsoft. FSharp. Core. Operators** . Algunos de los operadores se definen mediante parámetros de tipo resueltos estáticamente. Esto significa que hay definiciones individuales para cada tipo específico que funciona con ese operador. Todos los operadores aritméticos y bit a bit binarios y binarios se encuentran en esta categoría. Los operadores de comparación son genéricos y, por tanto, funcionan con cualquier tipo, no solo con tipos aritméticos primitivos. Los tipos de registro y Unión discriminada tienen sus propias implementaciones personalizadas generadas por F# el compilador. Los tipos de clase usan <xref:System.Object.Equals%2A>el método.

Los operadores genéricos son personalizables. Para personalizar las funciones de comparación, <xref:System.Object.Equals%2A> invalide para proporcionar su propia comparación de igualdad personalizada <xref:System.IComparable>y, a continuación, implemente. La <xref:System.IComparable?displayProperty=nameWithType> interfaz tiene un método único, el <xref:System.IComparable.CompareTo%2A> método.

## <a name="operators-and-type-inference"></a>Operadores e inferencia de tipos

El uso de un operador en una expresión restringe la inferencia de tipos en dicho operador. Además, el uso de operadores evita la generalización automática, porque el uso de operadores implica un tipo aritmético. En ausencia de otra información, el F# compilador deduce `int` como el tipo de expresiones aritméticas. Puede invalidar este comportamiento especificando otro tipo. Por lo tanto `int`, los tipos de argumento `function1` y el tipo de valor devuelto de en el código siguiente se deducen como, pero `float`los tipos de `function2` se deducen como.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3501.fs)]

## <a name="see-also"></a>Vea también

- [Referencia de símbolos y operadores](index.md)
- [Sobrecarga de operadores](../operator-overloading.md)
- [Operadores bit a bit](bitwise-operators.md)
- [Operadores booleanos](boolean-operators.md)
