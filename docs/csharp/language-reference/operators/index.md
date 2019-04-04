---
title: Operadores de C#
ms.date: 04/04/2018
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
ms.openlocfilehash: 7666918cbff7a395a93a274629fe574ff20e170c
ms.sourcegitcommit: 4a8c2b8d0df44142728b68ebc842575840476f6d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2019
ms.locfileid: "58545694"
---
# <a name="c-operators"></a>Operadores de C#

C# proporciona muchos operadores, que son símbolos que especifican las operaciones (matemáticas, indización, llamada de función, etc.) que se realizan en una expresión. Puede [sobrecargar](../../programming-guide/statements-expressions-operators/overloadable-operators.md) muchos operadores para cambiar su significado al aplicarlos a un tipo definido por el usuario.

Las operaciones de tipos enteros (como `==`, `!=`, `<`, `>`, `&` y `|`) suelen estar permitidas en los tipos de enumeración (`enum`).

En las secciones siguientes se enumeran los operadores de C# desde la precedencia más alta a la más baja. Los operadores de cada sección comparten el mismo nivel de precedencia.

## <a name="primary-operators"></a>Operadores principales

Estos son los operadores de precedencia más alta.

[x.y](member-access-operator.md): acceso a miembros.

[x?.y](null-conditional-operators.md): acceso a miembros condicionales nulos. Devuelve `null` si el operando izquierdo se evalúa como `null`.

[x?[y]](null-conditional-operators.md): acceso a índices condicionales nulos. Devuelve `null` si el operando izquierdo se evalúa como `null`.

[f(x)](invocation-operator.md): invocación de función.

[a&#91;x&#93;](index-operator.md): indización de objeto agregado.

[x++](arithmetic-operators.md#increment-operator-): incremento de postfijo. Devuelve el valor de x y, a continuación, actualiza la ubicación de almacenamiento con el valor de x que es uno mayor (normalmente agrega el entero 1).

[x--](arithmetic-operators.md#decrement-operator---): decremento de postfijo. Devuelve el valor de x; a continuación, actualiza la ubicación de almacenamiento con el valor de x que es uno menos (normalmente resta el entero 1).

[new](../keywords/new-operator.md): creación de instancias de tipo.

[typeof](../keywords/typeof.md): devuelve el objeto <xref:System.Type> que representa el operando.

[checked](../keywords/checked.md): habilita la comprobación de desbordamiento para operaciones con enteros.

[unchecked](../keywords/unchecked.md): deshabilita la comprobación de desbordamiento para operaciones con enteros. Este es el comportamiento predeterminado del compilador.

[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) genera el valor predeterminado del tipo T.

[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md): declara y devuelve una instancia de delegado.

[sizeof](../keywords/sizeof.md): devuelve el tamaño en bytes del operando de tipo.

[->](dereference-operator.md): desreferenciación del puntero combinada con acceso a miembros.

## <a name="unary-operators"></a>Operadores unarios

Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.

[+x](addition-operator.md): devuelve el valor de x.

[-x](subtraction-operator.md): negación numérica.

[\!x](logical-negation-operator.md): negación lógica.

[~x](bitwise-complement-operator.md): complemento bit a bit.

[++x](arithmetic-operators.md#increment-operator-): incremento de prefijo. Devuelve el valor de x después de actualizar la ubicación de almacenamiento con el valor de x que es uno mayor (normalmente agrega el entero 1).

[--x](arithmetic-operators.md#decrement-operator---): decremento de prefijo. Devuelve el valor de x después de actualizar la ubicación de almacenamiento con el valor de x que es uno menos (normalmente resta el entero 1).

[(T)x](invocation-operator.md): conversión de tipos.

[await](../keywords/await.md): espera una `Task`.

[&x](and-operator.md): dirección de.

[*x](multiplication-operator.md): desreferenciación.

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

[x <\<  y](left-shift-operator.md): desplaza los bits a la izquierda y rellena con cero a la derecha.

[x >> y](right-shift-operator.md): desplaza los bits a la derecha. Si el operando izquierdo es `int` o `long`, los bits de la izquierda se rellenan con el bit de signo. Si el operando izquierdo es `uint` o `ulong`, los bits de la izquierda se rellenan con cero.

## <a name="relational-and-type-testing-operators"></a>Operadores de comprobación de tipos y relacionales

Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.

[x \< y](less-than-operator.md): menor que (true si x es menor que y).

[x > y](greater-than-operator.md): mayor que (true si x es mayor que y).

[x \<= y](less-than-equal-operator.md): menor o igual que.

[x >= y](greater-than-equal-operator.md): mayor o igual que.

[is](../keywords/is.md): compatibilidad de tipos. Devuelve true si el operando izquierdo evaluado se puede convertir al tipo especificado en el operando derecho (un tipo estático).

[as](../keywords/as.md): conversión de tipos. Devuelve el operando izquierdo convertido al tipo especificado por el operando derecho (un tipo estático), pero `as` devuelve `null` donde `(T)x` produciría una excepción.

## <a name="equality-operators"></a>Operadores de igualdad

Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.

[x == y](equality-operators.md#equality-operator-): igualdad. De forma predeterminada, para los tipos de referencia distintos de `string`, devuelve igualdad de referencia (prueba de identidad). Sin embargo, los tipos pueden sobrecargar `==`, por lo que si su intención es probar la identidad, es mejor usar el método `ReferenceEquals` en `object`.

[x != y](equality-operators.md#inequality-operator-): distinto de. Vea el comentario de `==`. Si un tipo sobrecarga `==`, debe sobrecargar `!=`.

## <a name="logical-and-operator"></a>AND lógico (operador)

Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.

[x & y](and-operator.md): AND lógico o bit a bit. Por lo general puede usarlo con tipos enteros y tipos `enum`.

## <a name="logical-xor-operator"></a>Operador lógico XOR

Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.

[x ^ y](xor-operator.md): XOR lógico o bit a bit. Por lo general puede usarlo con tipos enteros y tipos `enum`.

## <a name="logical-or-operator"></a>Operador lógico OR (||)

Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.

[x &#124; y](or-operator.md): OR lógico o bit a bit. Por lo general puede usarlo con tipos enteros y tipos `enum`.

## <a name="conditional-and-operator"></a>Operador condicional AND

Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.

[x && y](conditional-and-operator.md): AND lógico. Si el primer operando se evalúa como false, C# no evalúa el segundo operando.

## <a name="conditional-or-operator"></a>Operador condicional OR

Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.

[x &#124;&#124; y](conditional-or-operator.md): OR lógico. Si el primer operando se evalúa como true, C# no evalúa el segundo operando.

## <a name="null-coalescing-operator"></a>Operador de uso combinado de null

Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.

[x ?? y](null-coalescing-operator.md): devuelve `x` si no es `null`; de lo contrario, devuelve `y`.

## <a name="conditional-operator"></a>Operador condicional

Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.

[t ? x : y](conditional-operator.md): si la prueba `t` se evalúa como true, evalúa y devuelve `x`; en caso contrario, evalúa y devuelve `y`.

## <a name="assignment-and-lambda-operators"></a>Operadores de asignación y Lambda

Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.

[x = y](assignment-operator.md): asignación.

[x += y](addition-assignment-operator.md): incremento. Agregue el valor de `y` al valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor. Si `x` designa un `event`, `y` debe ser una función adecuada que C# agregue como un controlador de eventos.

[x -= y](subtraction-assignment-operator.md): decremento. Reste el valor de `y` del valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor. Si `x` designa un `event`, `y` debe ser una función adecuada que C# quite como un controlador de eventos.

[x *= y](multiplication-assignment-operator.md): asignación de multiplicación. Multiplique el valor de `y` por el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.

[x /= y](arithmetic-operators.md#compound-assignment): asignación de división. Divida el valor de `x` por el valor de `y`, almacene el resultado en `x` y devuelva el nuevo valor.

[x %= y](arithmetic-operators.md#compound-assignment): asignación del resto. Divida el valor de `x` por el valor de `y`, almacene el resto en `x` y devuelva el nuevo valor.

[x &= y](and-assignment-operator.md): asignación de AND. AND el valor de `y` con el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.

[x &#124;= y](or-assignment-operator.md): asignación de OR. OR el valor de `y` con el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.

[x ^= y](xor-assignment-operator.md): asignación de XOR. XOR el valor de `y` con el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.

[x <<= y](left-shift-assignment-operator.md): asignación de desplazamiento a la izquierda. Desplace el valor de `x` a la izquierda `y` lugares, almacene el resultado en `x` y devuelva el nuevo valor.

[x >>= y](right-shift-assignment-operator.md): asignación de desplazamiento a la derecha. Desplace el valor de `x` a la derecha `y` posiciones, almacene el resultado en `x` y devuelva el nuevo valor.

[=>](lambda-operator.md): declaración lambda.

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [C#](../../index.md)
- [Operadores sobrecargables](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [Palabras clave de C#](../keywords/index.md)