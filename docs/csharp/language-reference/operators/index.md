---
title: "operadores de C# | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cs.operators"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "operadores de dirección [C#]"
  - "operadores aritméticos [C#]"
  - "operadores de asignación [C#]"
  - "operadores bit a bit [C#]"
  - "operadores booleanos [C#]"
  - "expresiones [C#], operadores"
  - "operadores de direccionamiento indirecto [C#]"
  - "palabras clave [C#], operadores"
  - "operadores lógicos [C#]"
  - "operadores [C#]"
  - "operadores relacionales [C#]"
  - "operadores de desplazamiento [C#]"
  - "Visual C#, operadores"
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
caps.latest.revision: 40
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 38
---
# operadores de C# #
C\# proporciona muchos operadores, que son símbolos que especifican las operaciones \(matemáticas, indización, llamada de función, etc.\) que se realizan en una expresión.  Puede [sobrecargar](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md) muchos operadores para cambiar su significado al aplicarlos a un tipo definido por el usuario.  
  
 Las operaciones en tipos enteros \(como `==`, `!=`, `<`, `>`, `&`,                   `|` \) se suelen permitir en tipos de enumeración \(`enum`\).  
  
 En las secciones se enumeran los operadores de C\# desde la precedencia más alta a la más baja.  Los operadores de cada sección comparten el mismo nivel de precedencia.  
  
## Operadores principales  
 Estos son los operadores de precedencia más alta.  Tenga en cuenta que puede hacer clic en los operadores para ir a las páginas de detalles con ejemplos.  
  
 [x.y](../../../csharp/language-reference/operators/member-access-operator.md): acceso a miembros.  
  
 [x?.y](../../../csharp/language-reference/operators/null-conditional-operators.md): acceso a miembros condicional null.  Devuelve null si el operando izquierdo es null.  
  
 [f\(x\)](../../../csharp/language-reference/operators/invocation-operator.md): invocación de función.  
  
 [a&#91;x&#93;](../../../csharp/language-reference/operators/index-operator.md): indización de objeto agregado.  
  
 [a?&#91;x&#93;](../../../csharp/language-reference/operators/null-conditional-operators.md): indización condicional null.  Devuelve null si el operando izquierdo es null.  
  
 [x\+\+](../../../csharp/language-reference/operators/increment-operator.md): incremento de postfijo.  Devuelve el valor de x y, a continuación, actualiza la ubicación de almacenamiento con el valor de x que es uno mayor \(normalmente agrega el entero 1\).  
  
 [x\-\-](../../../csharp/language-reference/operators/decrement-operator.md): decremento de postfijo.  Devuelve el valor de x; a continuación, actualiza la ubicación de almacenamiento con el valor de x que es uno menos \(normalmente resta el entero 1\).  
  
 [New](../../../csharp/language-reference/keywords/new-operator.md): creación de instancias de tipo.  
  
 [Typeof](../../../csharp/language-reference/keywords/typeof.md): devuelve el objeto System.Type que representa el operando.  
  
 [Checked](../../../csharp/language-reference/keywords/checked.md): habilita la comprobación de desbordamiento para operaciones con enteros.  
  
 [Unchecked](../../../csharp/language-reference/keywords/unchecked.md): deshabilita la comprobación de desbordamiento para operaciones con enteros.  Este es el comportamiento predeterminado del compilador.  
  
 [default\(T\)](../../../csharp/programming-guide/generics/default-keyword-in-generic-code.md): devuelve el valor inicializado predeterminado de tipo T, null para tipos de referencia, cero para tipos numéricos y cero o null en miembros para tipos de struct.  
  
 [Delegate](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md): declara y devuelve una instancia de delegado.  
  
 [Sizeof](../../../csharp/language-reference/keywords/sizeof.md): devuelve el tamaño en bytes del operando de tipo.  
  
 [\-\>](../../../csharp/language-reference/operators/dereference-operator.md): desreferenciación del puntero combinada con acceso a miembros.  
  
## Operadores unarios  
 Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que los de la anterior.  Tenga en cuenta que puede hacer clic en los operadores para ir a las páginas de detalles con ejemplos.  
  
 [\+x](../../../csharp/language-reference/operators/addition-operator.md): devuelve el valor de x.  
  
 [\-x](../../../csharp/language-reference/operators/subtraction-operator.md): negación numérica.  
  
 [\!x](../../../csharp/language-reference/operators/logical-negation-operator.md): negación lógica.  
  
 [~x](../../../csharp/language-reference/operators/bitwise-complement-operator.md): complemento bit a bit.  
  
 [\+\+x](../../../csharp/language-reference/operators/increment-operator.md): incremento de prefijo.  Devuelve el valor de x después de actualizar la ubicación de almacenamiento con el valor de x que es uno mayor \(normalmente agrega el entero 1\).  
  
 [\-\-x](../../../csharp/language-reference/operators/decrement-operator.md): decremento de prefijo.  Devuelve el valor de x después de actualizar la ubicación de almacenamiento con el valor de x que es uno menos \(normalmente resta el entero 1\).  
  
 [\(T\)x](../../../csharp/language-reference/operators/invocation-operator.md): conversión de tipos.  
  
 [Await](../../../csharp/language-reference/keywords/await.md): espera una `Task`.  
  
 [&x](../../../csharp/language-reference/operators/and-operator.md): dirección de.  
  
 [\*x](../../../csharp/language-reference/operators/multiplication-operator.md): desreferenciación.  
  
## Operadores multiplicativos  
 Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que los de la anterior.  Tenga en cuenta que puede hacer clic en los operadores para ir a las páginas de detalles con ejemplos.  
  
 [x \* y](../../../csharp/language-reference/operators/multiplication-operator.md): multiplicación.  
  
 [x \/ y](../../../csharp/language-reference/operators/division-operator.md): división.  Si los operandos son enteros, el resultado es un entero que se trunca hacia cero \(por ejemplo, `-7 / 2 is -3`\).  
  
 [x % y](../../../csharp/language-reference/operators/modulus-operator.md): módulo.  Si los operandos son enteros, devuelve el resto de dividir x entre y.  Si `q = x / y` y `r = x % y`, entonces `x = q * y + r`.  
  
## Operadores aditivos  
 Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que los de la anterior.  Tenga en cuenta que puede hacer clic en los operadores para ir a las páginas de detalles con ejemplos.  
  
 [x \+ y](../../../csharp/language-reference/operators/addition-operator.md): suma.  
  
 [x – y](../../../csharp/language-reference/operators/subtraction-operator.md): resta.  
  
## Operadores de desplazamiento  
 Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que los de la anterior.  Tenga en cuenta que puede hacer clic en los operadores para ir a las páginas de detalles con ejemplos.  
  
 [x \<\<  y](../../../csharp/language-reference/operators/left-shift-operator.md): desplaza los bits a la izquierda y rellena con cero a la derecha.  
  
 [x \>\> y](../../../csharp/language-reference/operators/right-shift-operator.md): desplaza los bits a la derecha.  Si el operando izquierdo es `int` o `long`, los bits de la izquierda se rellenan con el bit de signo.  Si el operando izquierdo es `uint` o `ulong`, los bits de la izquierda se rellenan con cero.  
  
## Operadores de comprobación de tipos y relacionales  
 Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que los de la anterior.  Tenga en cuenta que puede hacer clic en los operadores para ir a las páginas de detalles con ejemplos.  
  
 [x \< y](../../../csharp/language-reference/operators/less-than-operator.md): menor que \(true si x es menor que y\).  
  
 [x \> y](../../../csharp/language-reference/operators/greater-than-operator.md): mayor que \(true si x es mayor que y\).  
  
 [x \<\= y](../../../csharp/language-reference/operators/less-than-equal-operator.md): menor o igual que.  
  
 [x \>\= y](../../../csharp/language-reference/operators/greater-than-equal-operator.md): menor o igual que.  
  
 [Is](../../../csharp/language-reference/keywords/is.md): compatibilidad de tipos.  Devuelve true si el operando izquierdo evaluado se puede convertir al tipo especificado en el operando derecho \(un tipo estático\).  
  
 [As](../../../csharp/language-reference/keywords/as.md): conversión de tipos.  Devuelve el operando izquierdo convertido al tipo especificado por el operando derecho \(un tipo estático\), pero `as` devuelve `null` donde `(T)x` produciría una excepción.  
  
## Operadores de igualdad  
 Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que los de la anterior.  Tenga en cuenta que puede hacer clic en los operadores para ir a las páginas de detalles con ejemplos.  
  
 [x \=\= y](../../../csharp/language-reference/operators/equality-comparison-operator.md): igualdad.  De forma predeterminada, para los tipos de referencia distintos de `string`, devuelve igualdad de referencia \(prueba de identidad\).  Sin embargo, los tipos pueden sobrecargar `==`, por lo que si su intención es probar la identidad, es mejor usar el método `ReferenceEquals` en `object`.  
  
 [x \!\= y](../../../csharp/language-reference/operators/not-equal-operator.md): distinto de.  Vea el comentario de `==`.  Si un tipo sobrecarga `==`, debe sobrecargar `!=`.  
  
## Operador lógico AND  
 Este operador tiene mayor precedencia que el de la sección siguiente y menor que los de la anterior.  Tenga en cuenta que puede hacer clic en el operador para ir a la página de detalles con ejemplos.  
  
 [x & y](../../../csharp/language-reference/operators/and-operator.md): AND lógico o bit a bit.  El uso con tipos enteros y tipos `enum` suele estar permitido.  
  
## Operador lógico XOR  
 Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.  Tenga en cuenta que puede hacer clic en el operador para ir a la página de detalles con ejemplos.  
  
 [x ^ y](../../../csharp/language-reference/operators/xor-operator.md): XOR lógico o bit a bit.  Por lo general puede usarlo con tipos enteros y tipos `enum`.  
  
## Operador lógico OR  
 Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.  Tenga en cuenta que puede hacer clic en el operador para ir a la página de detalles con ejemplos.  
  
 [x &#124; y](../../../csharp/language-reference/operators/or-operator.md): OR lógico o bit a bit.  El uso con tipos enteros y tipos `enum` suele estar permitido.  
  
## Operador condicional AND  
 Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.  Tenga en cuenta que puede hacer clic en el operador para ir a la página de detalles con ejemplos.  
  
 [x && y](../../../csharp/language-reference/operators/conditional-and-operator.md): AND lógico.  Si el primer operando es false, C\# no evalúa el segundo operando.  
  
## Operador condicional OR  
 Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.  Tenga en cuenta que puede hacer clic en el operador para ir a la página de detalles con ejemplos.  
  
 [x &#124;&#124; y](../../../csharp/language-reference/operators/conditional-or-operator.md): OR lógico.  Si el primer operando es true, C\# no evalúa el segundo operando.  
  
## Operador de uso combinado de null  
 Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.  Tenga en cuenta que puede hacer clic en el operador para ir a la página de detalles con ejemplos.  
  
 [x ?? y](../../../csharp/language-reference/operators/null-conditional-operator.md): devuelve `x` si no es `null`; de lo contrario, devuelve `y`.  
  
## Operador condicional  
 Este operador tiene mayor precedencia que el de la sección siguiente y menor que el de la anterior.  Tenga en cuenta que puede hacer clic en el operador para ir a la página de detalles con ejemplos.  
  
 [t ? x : y](../../../csharp/language-reference/operators/conditional-operator.md): si la prueba `t` es true, evalúa y devuelve `x`; en caso contrario, evalúa y devuelve `y`.  
  
## Operadores de asignación y Lambda  
 Estos operadores tienen mayor precedencia que los de la sección siguiente y menor que el de la anterior.  Tenga en cuenta que puede hacer clic en los operadores para ir a las páginas de detalles con ejemplos.  
  
 [x \= y](../../../csharp/language-reference/operators/assignment-operator.md): asignación.  
  
 [x \+\= y](../../../csharp/language-reference/operators/addition-assignment-operator.md): incremento.  Agregue el valor de `y` al valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.  Si `x` designa un `event`, `y` debe ser una función adecuada que C\# agregue como un controlador de eventos.  
  
 [x \-\= y](../../../csharp/language-reference/operators/subtraction-assignment-operator-1.md): decremento.  Reste el valor de `y` del valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.  Si `x` designa un `event`, `y` debe ser una función adecuada que C\# quite como un controlador de eventos.  
  
 [x \*\= y](../../../csharp/language-reference/operators/multiplication-assignment-operator.md): asignación y multiplicación.  Multiplique el valor de `y` por el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.  
  
 [x \/\= y](../../../csharp/language-reference/operators/subtraction-assignment-operator.md): asignación y división.  Divida el valor de `x` por el valor de `y`, almacene el resultado en `x` y devuelva el nuevo valor.  
  
 [x %\= y](../../../csharp/language-reference/operators/modulus-assignment-operator.md): asignación y módulo.  Divida el valor de `x` por el valor de `y`, almacene el resto en `x` y devuelva el nuevo valor.  
  
 [x &\= y](../../../csharp/language-reference/operators/and-assignment-operator.md): asignación y AND.  AND el valor de `y` con el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.  
  
 [x &#124;\= y](../../../csharp/language-reference/operators/or-assignment-operator.md): asignación y OR.  OR el valor de `y` con el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.  
  
 [x ^\= y](../../../csharp/language-reference/operators/xor-assignment-operator.md): asignación y XOR.  XOR el valor de `y` con el valor de `x`, almacene el resultado en `x` y devuelva el nuevo valor.  
  
 [x \<\<\= y](../../../csharp/language-reference/operators/left-shift-assignment-operator.md): asignación y desplazamiento a la izquierda.  Desplace el valor de `x` a la izquierda `y` lugares, almacene el resultado en `x` y devuelva el nuevo valor.  
  
 [x \>\>\= y](../../../csharp/language-reference/operators/right-shift-assignment-operator.md): asignación y desplazamiento a la derecha.  Desplace el valor de `x` a la derecha `y` posiciones, almacene el resultado en `x` y devuelva el nuevo valor.  
  
 [\=\>](../../../csharp/language-reference/operators/lambda-operator.md): declaración lambda.  
  
## Desbordamiento aritmético  
 Los operadores aritméticos \([\+](../../../csharp/language-reference/operators/addition-operator.md), [\-](../../../csharp/language-reference/operators/subtraction-operator.md), [\*](../../../csharp/language-reference/operators/multiplication-operator.md), [\/](../../../csharp/language-reference/operators/division-operator.md)\) pueden producir resultados fuera del rango de valores posibles para el tipo numérico implicado.  Para obtener detalles debe ir a la sección del operador en cuestión, pero en general:  
  
-   El desbordamiento aritmético de enteros produce una <xref:System.OverflowException> o descarta los bits más significativos del resultado.  La división de enteros por cero siempre produce una `DivideByZeroException`.  
  
-   El desbordamiento aritmético de punto flotante o la división por cero nunca producen una excepción, porque los tipos de punto flotante se basan en el estándar IEEE 754 y por tanto tienen disposiciones para representar el infinito y NaN \(No es un número\).  
  
-   El desbordamiento aritmético [decimal](../../../csharp/language-reference/keywords/decimal.md) siempre produce una <xref:System.OverflowException>.  La división decimal por cero siempre produce una <xref:System.DivideByZeroException>.  
  
 Cuando se produce el desbordamiento de enteros, lo que suceda dependerá del contexto de ejecución, que puede ser [comprobado o no comprobado](../../../csharp/language-reference/keywords/checked-and-unchecked.md).  En un contexto comprobado, se produce una <xref:System.OverflowException>.  En un contexto no comprobado, se descartan los bits más significativos del resultado y la ejecución continúa.  Por lo tanto, C\# ofrece la posibilidad de controlar u omitir el desbordamiento.  
  
 Además de los operadores aritméticos, las conversiones de tipo entero a tipo entero también pueden provocar un desbordamiento \(por ejemplo, la conversión de un [long](../../../csharp/language-reference/keywords/long.md) a un [int](../../../csharp/language-reference/keywords/int.md)\) y están sujetas a ejecución comprobada o no comprobada.  Sin embargo, los operadores bit a bit y los de desplazamiento nunca producen desbordamiento.  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [C\#](../../../csharp/csharp.md)   
 [Operadores sobrecargables](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)