---
title: "Tipos de datos de resultados de operador (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "tipos de datos [Visual Basic], tipos de datos resultantes de operadores"
  - "tipos de datos [Visual Basic], intervalos"
  - "tipos de datos resultantes de operadores"
  - "operadores [Visual Basic], tipos de datos"
  - "operadores [Visual Basic], tipos de datos resultantes"
  - "tipos de datos resultantes"
ms.assetid: 9d524533-e1a1-4aa8-b1b8-622068173d06
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# Tipos de datos de resultados de operador (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] determina el tipo de datos del resultado de una operación en función de los tipos de datos de los operandos.  En algunos casos, el tipo de datos del resultado podría tener un intervalo mayor que el de los operandos.  
  
## Intervalos de tipos de datos  
 Los intervalos de los tipos de datos pertinentes, ordenados de menor a mayor, son los siguientes:  
  
-   [Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md) — dos valores posibles  
  
-   [SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md) — 256 valores enteros posibles  
  
-   [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md) — 65,536 \(6.5...E\+4\) valores integrales posibles  
  
-   [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) — 4,294,967,296 \(4.2...E\+9\) valores integrales posibles  
  
-   [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md) — 18,446,744,073,709,551,615 \(1.8...E\+19\) valores integrales posibles  
  
-   [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) — 1.5...E\+29 valores integrales posibles, intervalo máximo 7.9...E\+28 \(valor absoluto\)  
  
-   [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) — intervalo máximo 3.4...E\+38 \(valor absoluto\)  
  
-   [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) — intervalo máximo 1.7...E\+308 \(valor absoluto\)  
  
 Para obtener más información sobre los tipos de datos de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], vea [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
 Si un operando se evalúa como [Nothing](../../../visual-basic/language-reference/nothing.md), los operadores aritméticos de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] lo tratan como si fuera cero.  
  
## Aritmética decimal  
 Tenga en cuenta que el tipo de datos [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) no es un tipo de datos de punto flotante ni un tipo de datos entero.  
  
 Si alguno de los operandos de una operación `+`, `–`, `*`, `/` o `Mod` es `Decimal` y el otro es distinto de `Single` o `Double`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] amplía el otro operando a `Decimal`.  El programa realiza la operación en `Decimal` y el tipo de datos resultante es `Decimal`.  
  
## Aritmética de punto flotante  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] realiza la mayor parte de las operaciones aritméticas de punto flotante en [Double](../../../visual-basic/language-reference/data-types/double-data-type.md), que es el tipo de datos más eficaz para estas operaciones.  Sin embargo, si un operando es [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) y el otro es distinto de `Double`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] realiza la operación en `Single`.  El programa amplía cada operando según sea necesario al tipo de datos adecuado antes de la operación, y el resultado tiene ese tipo de datos.  
  
### \/ y ^ \(Operadores\)  
 El operador `/` solo se define para los tipos de datos [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) y [Double](../../../visual-basic/language-reference/data-types/double-data-type.md).  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] amplía cada operando según sea necesario al tipo de datos adecuado antes de la operación, y el resultado tiene ese tipo de datos.  
  
 En la tabla siguiente se muestran los tipos de datos resultantes para el operador `/`.  Observe que esta tabla es simétrica; para una combinación dada de tipos de datos de los operandos, el tipo de datos del resultado será el mismo independientemente del orden de los operandos.  
  
||||||  
|-|-|-|-|-|  
||`Decimal`|`Single`|`Double`|Cualquier tipo de entero|  
|`Decimal`|Decimal|Simple|Double|Decimal|  
|`Single`|Simple|Simple|Double|Simple|  
|`Double`|Double|Double|Double|Double|  
|Cualquier tipo de entero|Decimal|Simple|Double|Double|  
  
 El operador `^` solo se define para el tipo de datos `Double`.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] amplía cada operando según sea necesario en `Double` antes de la operación, y el tipo de datos resultante es siempre `Double`.  
  
## Aritmética de enteros  
 El tipo de datos resultante de una operación de enteros depende de los tipos de datos de los operandos.  Por lo general, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] utiliza las directivas siguientes para determinar el tipo de datos del resultado:  
  
-   Si ambos operandos de un operador binario tienen el mismo tipo de datos, el resultado tiene ese tipo de datos.  Una excepción es `Boolean`, que forzosamente es `Short`.  
  
-   Si un operando sin signo trabaja con un operando con signo, el resultado tiene un tipo con signo que como mínimo tiene un intervalo tan grande como el de cualquiera de los dos operandos.  
  
-   De lo contrario, el resultado normalmente tiene el tipo de datos más grande de los dos operandos.  
  
 Tenga en cuenta que el tipo de datos del resultado puede diferir del tipo de datos de los operandos.  
  
> [!NOTE]
>  El tipo de datos del resultado no siempre es lo suficientemente grande como para contener todos los valores posibles que resultan de la operación.  Puede iniciarse una excepción <xref:System.OverflowException> si el valor es demasiado grande para el tipo de datos del resultado.  
  
### \+ y – \(Operadores unarios\)  
 En la tabla siguiente se muestran los tipos de datos resultantes para los dos operadores unarios `+` y `–`.  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|Unario `+`|Short|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|Unario `–`|Short|SByte|Short|Short|Integer|Integer|Long|Long|Decimal|  
  
### \<\< y \>\> \(Operadores\)  
 En la tabla siguiente se muestran los tipos de datos resultantes para dos operadores de desplazamiento de bits. `<<` y `>>`.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] trata cada operador de desplazamiento de bits como un operador unario en su operando izquierdo \(el modelo de bits que se va a desplazar\).  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
  
 Si el operando izquierdo es `Decimal`, `Single`, `Double` o `String`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] intenta convertirlo en `Long` antes de la operación, y el tipo de datos del resultado es `Long`.  El operando derecho \(el número de posiciones en bits que se va a desplazar\) debe ser `Integer` o un tipo que se amplíe a `Integer`.  
  
### \+, –, \* y Mod \(Operadores binarios\)  
 En la tabla siguiente se muestran los tipos de datos resultantes para los operadores `+` y `–` binarios y los operadores `*` y `Mod`.  Observe que esta tabla es simétrica; para una combinación dada de tipos de datos de los operandos, el tipo de datos del resultado será el mismo independientemente del orden de los operandos.  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Integer|Integer|Long|Long|Decimal|  
|`SByte`|SByte|SByte|Short|Short|Integer|Integer|Long|Long|Decimal|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|Integer|Long|Long|Decimal|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|Long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|Long|Long|Decimal|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Decimal|  
|`ULong`|Decimal|Decimal|ULong|Decimal|ULong|Decimal|ULong|Decimal|ULong|  
  
### \\ \(Operador\)  
 En la tabla siguiente se muestran los tipos de datos resultantes para el operador `\`.  Observe que esta tabla es simétrica; para una combinación dada de tipos de datos de los operandos, el tipo de datos del resultado será el mismo independientemente del orden de los operandos.  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|Integer|Long|Long|Long|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|Long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 Si alguno de los operandos del operador `\` es [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) o [Double](../../../visual-basic/language-reference/data-types/double-data-type.md), [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] intenta convertirlo a [Long](../../../visual-basic/language-reference/data-types/long-data-type.md) antes de la operación, y el tipo de datos del resultado es `Long`.  
  
## Comparaciones relacionales y bit a bit  
 El tipo de datos resultante de una operación relacional \(`=`, `<>`, `<`, `>`, `<=`, `>=`\) siempre es `Boolean`[Boolean \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/boolean-data-type.md).  Esto se aplica también a las operaciones lógicas \(`And`, `AndAlso`, `Not`, `Or`, `OrElse`, `Xor`\) de operandos `Boolean`.  
  
 El tipo de datos resultante de una operación lógica bit a bit depende de los tipos de datos de los operandos.  Tenga en cuenta que `AndAlso` y `OrElse` sólo se definen para `Boolean`, y [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] convierte cada operando según sea necesario en `Boolean` antes de realizar la operación.  
  
### \=, \<\>, \<, \>, \<\= y \>\= \(Operadores\)  
 Si ambos operandos son `Boolean`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] considera que `True` es menor que `False`.  Si un tipo numérico se compara con un tipo `String`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] intenta convertir el tipo `String` a `Double` antes de la operación.  Un operando `Char` o `Date` sólo se puede comparar con otro operando del mismo tipo de datos.  El tipo de datos resultante siempre es `Boolean`.  
  
### Not \(Operador bit a bit\)  
 En la tabla siguiente se muestran los tipos de datos resultantes para el operador `Not` bit a bit.  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Boolean|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
  
 Si el operando es `Decimal`, `Single`, `Double` o `String`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] intenta convertirlo a `Long` antes de la operación, y el tipo de datos resultante es `Long`.  
  
### And, Or y Xor \(Operadores bit a bit\)  
 En la tabla siguiente se muestran los tipos de datos resultantes para los operadores `And`, `Or` y `Xor` bit a bit.  Observe que esta tabla es simétrica; para una combinación dada de tipos de datos de los operandos, el tipo de datos del resultado será el mismo independientemente del orden de los operandos.  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Boolean|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|Integer|Long|Long|Long|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|Long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 Si un operando es `Decimal`, `Single`, `Double` o `String`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] intenta convertirlo a `Long` antes de la operación, y el tipo de datos resultante es el mismo que el del operando que ya había sido `Long`.  
  
## Operadores varios  
 El operador `&` sólo se define para la concatenación de operandos `String`.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] convierte cada operando según sea necesario en `String` antes de la operación y el tipo de datos resultante es siempre `String`.  Para los propósitos del operador `&`, se considera que todas las conversiones a `String` se están ampliando, aun cuando `Option Strict` es `On`.  
  
 Los operadores `Is` y `IsNot` requieren que ambos operandos pertenezcan a un tipo de referencia.  La expresión `TypeOf`...`Is` requiere que el primer operando pertenezca a un tipo de referencia y el segundo operando sea el nombre de un tipo de datos.  En todos estos casos, el tipo de datos resultante es `Boolean`.  
  
 El operador `Like` sólo se define para la coincidencia de modelos de operandos `String`.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] intenta convertir cada operando como requisito en `String` antes de la operación.  El tipo de datos resultante siempre es `Boolean`.  
  
## Vea también  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Operadores de comparación en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Operadores](../../../visual-basic/language-reference/operators/index.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operadores de comparación](../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Option Strict \(Instrucción\)](../../../visual-basic/language-reference/statements/option-strict-statement.md)