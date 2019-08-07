---
title: 'Operadores de C#: referencia de C#'
ms.date: 04/30/2019
f1_keywords:
- cs.operators
helpviewer_keywords:
- boolean operators [C#]
- expressions [C#], operators
- logical operators [C#]
- operators [C#]
- Visual C#, operators
- indirection operators [C#]
- assignment operators [C#]
- shift operators [C#]
- relational operators [C#]
- bitwise operators [C#]
- address operators [C#]
- keywords [C#], operators
- arithmetic operators [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: bc5e2c88314c2f590aeddcfd37bd04c3a7400804
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796482"
---
# <a name="c-operators-c-reference"></a>Operadores de C# (referencia de C#)

C# proporciona una serie de operadores predefinidos compatibles con los tipos integrados. Por ejemplo, los [operadores aritméticos](arithmetic-operators.md) realizan operaciones aritméticas con operandos de tipos numéricos integrados, y los [operadores lógicos booleanos](boolean-logical-operators.md) realizan operaciones lógicas con los operandos [bool](../keywords/bool.md).

Un tipo definido por el usuario puede sobrecargar determinados operadores para definir el comportamiento correspondiente para los operandos de ese tipo. Para obtener más información, vea [Sobrecarga de operadores](operator-overloading.md).

En las secciones siguientes se enumeran los operadores de C# desde la precedencia más alta a la más baja. Los operadores de cada sección comparten el mismo nivel de precedencia.

## <a name="primary-operators"></a>Operadores principales

Estos son los operadores de precedencia más alta.

[x.y](member-access-operators.md#member-access-operator-): acceso a miembros.

[x?.y](member-access-operators.md#null-conditional-operators--and-): acceso a miembros condicionales nulos. Devuelve `null` si el operando izquierdo se evalúa como `null`.

[x?[y]](member-access-operators.md#null-conditional-operators--and-): elemento de matriz condicional NULL o acceso al indizador de tipos. Devuelve `null` si el operando izquierdo se evalúa como `null`.

[f(x)](member-access-operators.md#invocation-operator-): llamada de método o invocación de delegado.

[a&#91;x&#93;](member-access-operators.md#indexer-operator-): elemento de matriz o acceso al indizador de tipos.

[x++](arithmetic-operators.md#increment-operator-): incremento de postfijo. Devuelve el valor de x y, a continuación, actualiza la ubicación de almacenamiento con el valor de x que es uno mayor (normalmente agrega el entero 1).

[x--](arithmetic-operators.md#decrement-operator---): decremento de postfijo. Devuelve el valor de x; a continuación, actualiza la ubicación de almacenamiento con el valor de x que es uno menos (normalmente resta el entero 1).

[new](new-operator.md): creación de instancias de tipo.

[typeof](type-testing-and-conversion-operators.md#typeof-operator): devuelve el objeto <xref:System.Type> que representa el operando.

[checked](../keywords/checked.md): habilita la comprobación de desbordamiento para operaciones con enteros.

[unchecked](../keywords/unchecked.md): deshabilita la comprobación de desbordamiento para operaciones con enteros. Este es el comportamiento predeterminado del compilador.

[default(T)](default.md) genera el valor predeterminado del tipo T.

[nameof](nameof.md): obtiene el nombre simple (incompleto) de una variable, tipo o miembro como una cadena constante.

[delegate](delegate-operator.md): declara y devuelve una instancia de delegado.

[sizeof](sizeof.md): devuelve el tamaño en bytes del operando de tipo.

[stackalloc](stackalloc.md): asigna un bloque de memoria en la pila.

[->](pointer-related-operators.md#pointer-member-access-operator--): direccionamiento indirecto del puntero combinado con acceso a miembros.

## <a name="unary-operators"></a>Operadores unarios

Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.

[+x](addition-operator.md): devuelve el valor de x.

[-x](subtraction-operator.md): negación numérica.

[\!x](boolean-logical-operators.md#logical-negation-operator-): negación lógica.

[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-): complemento bit a bit.

[++x](arithmetic-operators.md#increment-operator-): incremento de prefijo. Devuelve el valor de x después de actualizar la ubicación de almacenamiento con el valor de x que es uno mayor (normalmente agrega el entero 1).

[--x](arithmetic-operators.md#decrement-operator---): decremento de prefijo. Devuelve el valor de x después de actualizar la ubicación de almacenamiento con el valor de x que es uno menos (normalmente resta el entero 1).

[(T)x](type-testing-and-conversion-operators.md#cast-operator-): conversión de tipos.

[await](../keywords/await.md): espera una `Task`.

[&x](pointer-related-operators.md#address-of-operator-): dirección de una variable.

[*x](pointer-related-operators.md#pointer-indirection-operator-): direccionamiento indirecto del puntero o desreferenciación.

El [operador true](true-false-operators.md) devuelve el valor [bool](../keywords/bool.md) `true` para indicar que un operando es definitivamente true.

El [operador false](true-false-operators.md) devuelve el valor [bool](../keywords/bool.md) `true` para indicar que un operado es definitivamente "false".

## <a name="multiplicative-operators"></a>Operadores de multiplicación

Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.

[x * y](arithmetic-operators.md#multiplication-operator-): multiplicación.

[x / y](arithmetic-operators.md#division-operator-): división. Si los operandos son enteros, el resultado es un entero que se trunca hacia cero (por ejemplo, `-7 / 2 is -3`).

[x % y](arithmetic-operators.md#remainder-operator-): resto. Si los operandos son enteros, devuelve el resto de dividir x entre y.  Si `q = x / y` y `r = x % y`, entonces `x = q * y + r`.

## <a name="additive-operators"></a>Operadores aditivos

Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.

[x + y](arithmetic-operators.md#addition-operator-): suma.

[x – y](arithmetic-operators.md#subtraction-operator--): resta.

## <a name="shift-operators"></a>Operadores de desplazamiento

Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.

[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-): desplaza los bits a la izquierda y rellena con cero a la derecha.

[x >> y](bitwise-and-shift-operators.md#right-shift-operator-): desplaza los bits a la derecha. Si el operando izquierdo es `int` o `long`, los bits de la izquierda se rellenan con el bit de signo. Si el operando izquierdo es `uint` o `ulong`, los bits de la izquierda se rellenan con cero.

## <a name="relational-and-type-testing-operators"></a>Operadores de comprobación de tipos y relacionales

Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.

[x \< y](comparison-operators.md#less-than-operator-): menor que (true si x es menor que y).

[x > y](comparison-operators.md#greater-than-operator-): mayor que (true si x es mayor que y).

[x \<= y](comparison-operators.md#less-than-or-equal-operator-): menor o igual que.

[x >= y](comparison-operators.md#greater-than-or-equal-operator-): mayor o igual que.

[is](type-testing-and-conversion-operators.md#is-operator): compatibilidad de tipos. Devuelve `true` si el operando izquierdo evaluado se puede convertir al tipo especificado en el operando derecho.

[as](type-testing-and-conversion-operators.md#as-operator): conversión de tipos. Devuelve el operando izquierdo convertido al tipo especificado por el operando derecho, pero `as` devuelve `null` donde `(T)x` iniciaría una excepción.

## <a name="equality-operators"></a>Operadores de igualdad

Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.

[x == y](equality-operators.md#equality-operator-): igualdad. De forma predeterminada, para los tipos de referencia distintos de `string`, devuelve igualdad de referencia (prueba de identidad). Sin embargo, los tipos pueden sobrecargar `==`, por lo que si su intención es probar la identidad, es mejor usar el método `ReferenceEquals` en `object`.

[x != y](equality-operators.md#inequality-operator-): distinto de. Vea el comentario de `==`. Si un tipo sobrecarga `==`, debe sobrecargar `!=`.

## <a name="logical-and-operator"></a>AND lógico (operador)

Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.

`x & y` – [AND lógico](boolean-logical-operators.md#logical-and-operator-) para los operandos `bool` o [AND lógico bit a bit](bitwise-and-shift-operators.md#logical-and-operator-) para los operandos de los tipos integrales.

## <a name="logical-xor-operator"></a>Operador lógico XOR

Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.

`x ^ y` – [XOR lógico](boolean-logical-operators.md#logical-exclusive-or-operator-) para los operandos `bool` o [XOR lógico bit a bit](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) para los operandos de los tipos integrales.

## <a name="logical-or-operator"></a>Operador lógico OR (||)

Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.

`x | y` – [OR lógico](boolean-logical-operators.md#logical-or-operator-) para los operandos `bool` o [OR lógico bit a bit](bitwise-and-shift-operators.md#logical-or-operator-) para los operandos de los tipos integrales.

## <a name="conditional-and-operator"></a>Operador condicional AND

Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.

[x && y](boolean-logical-operators.md#conditional-logical-and-operator-): AND lógico. Si `x` se evalúa como `false`, `y` no se evalúa.

## <a name="conditional-or-operator"></a>Operador condicional OR

Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.

[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-): OR lógico. Si `x` se evalúa como `true`, `y` no se evalúa.

## <a name="null-coalescing-operator"></a>Operador de uso combinado de null

Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.

[x ?? y](null-coalescing-operator.md): devuelve `x` si no es `null`; de lo contrario, devuelve `y`.

## <a name="conditional-operator"></a>Operador condicional

Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.

[t ? x : y](conditional-operator.md): si la prueba `t` se evalúa como true, evalúa y devuelve `x`; en caso contrario, evalúa y devuelve `y`.

## <a name="assignment-and-lambda-operators"></a>Operadores de asignación y lambda

Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.

[x = y](assignment-operator.md): asignación.

[x += y](arithmetic-operators.md#compound-assignment): incremento. Agregue el valor de `y` al valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor. Si `x` designa un [evento](../keywords/event.md), `y` debe ser un método adecuado que C# agregue como un controlador de eventos.

[x -= y](arithmetic-operators.md#compound-assignment): decremento. Reste el valor de `y` del valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor. Si `x` designa un [evento](../keywords/event.md), `y` debe ser un método adecuado que C# quite como un controlador de eventos.

[x *= y](arithmetic-operators.md#compound-assignment): asignación de multiplicación. Multiplique el valor de `y` por el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.

[x /= y](arithmetic-operators.md#compound-assignment): asignación de división. Divida el valor de `x` por el valor de `y`, almacene el resultado en `x` y devuelva el nuevo valor.

[x %= y](arithmetic-operators.md#compound-assignment): asignación del resto. Divida el valor de `x` por el valor de `y`, almacene el resto en `x` y devuelva el nuevo valor.

[x &= y](boolean-logical-operators.md#compound-assignment): asignación de AND. AND el valor de `y` con el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.

[x &#124;= y](boolean-logical-operators.md#compound-assignment): asignación de OR. OR el valor de `y` con el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.

[x ^= y](boolean-logical-operators.md#compound-assignment): asignación de XOR. XOR el valor de `y` con el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.

[x <<= y](bitwise-and-shift-operators.md#compound-assignment): asignación de desplazamiento a la izquierda. Desplace el valor de `x` a la izquierda `y` lugares, almacene el resultado en `x` y devuelva el nuevo valor.

[x >>= y](bitwise-and-shift-operators.md#compound-assignment): asignación de desplazamiento a la derecha. Desplace el valor de `x` a la derecha `y` posiciones, almacene el resultado en `x` y devuelva el nuevo valor.

[=>](lambda-operator.md): declaración lambda.

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores](../../programming-guide/statements-expressions-operators/operators.md)
