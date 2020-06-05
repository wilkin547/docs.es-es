---
title: Tipos de datos de los resultados de los operadores
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], operator result data types
- result data types [Visual Basic]
- operator result data types [Visual Basic]
- operators [Visual Basic], data types
- data types [Visual Basic], ranges
- operators [Visual Basic], result data types
ms.assetid: 9d524533-e1a1-4aa8-b1b8-622068173d06
ms.openlocfilehash: b80508c5619770da0c7dc78003ff9d4847dd94d8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371432"
---
# <a name="data-types-of-operator-results-visual-basic"></a>Tipos de datos de resultados de operador (Visual Basic)
Visual Basic determina el tipo de datos de resultado de una operación en función de los tipos de datos de los operandos. En algunos casos, podría tratarse de un tipo de datos con un intervalo mayor que el de uno de los operandos.  
  
## <a name="data-type-ranges"></a>Intervalos de tipo de datos  
 Los intervalos de los tipos de datos pertinentes, en orden de menor a mayor, son los siguientes:  
  
- [Booleano](../data-types/boolean-data-type.md) : dos valores posibles  
  
- [SByte](../data-types/sbyte-data-type.md), [byte](../data-types/byte-data-type.md) : 256 posibles valores integrales  
  
- [Short](../data-types/short-data-type.md), [ushort](../data-types/ushort-data-type.md) : 65.536 (6.5... E + 4) posibles valores integrales  
  
- [Entero](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md) : 4.294.967.296 (4.2... E + 9) posibles valores integrales  
  
- [Long](../data-types/long-data-type.md), [ULong](../data-types/ulong-data-type.md) : 18446744073709551615 (1.8... E + 19) posibles valores integrales  
  
- [Decimal](../data-types/decimal-data-type.md) : 1,5... e + 29 posibles valores integrales, intervalo máximo de 7,9... e + 28 (valor absoluto)  
  
- [Único](../data-types/single-data-type.md) : intervalo máximo 3.4... E + 38 (valor absoluto)  
  
- [Double](../data-types/double-data-type.md) : intervalo máximo 1.7... E + 308 (valor absoluto)  
  
 Para obtener más información sobre los tipos de datos de Visual Basic, vea [tipos de datos](../data-types/index.md).  
  
 Si un operando se evalúa como [Nothing](../nothing.md), los operadores aritméticos Visual Basic lo consideran como cero.  
  
## <a name="decimal-arithmetic"></a>Aritmética decimal  
 Tenga en cuenta que el tipo de datos [decimal](../data-types/decimal-data-type.md) no es ningún punto flotante ni entero.  
  
 Si alguno de los operandos de una `+` `–` operación,,, `*` `/` o `Mod` es `Decimal` y el otro no es `Single` o `Double` , Visual Basic amplía el otro operando a `Decimal` . Realiza la operación en `Decimal` y el tipo de datos del resultado es `Decimal` .  
  
## <a name="floating-point-arithmetic"></a>Aritmética de punto flotante  
 Visual Basic realiza la mayoría de la aritmética de punto flotante en [Double](../data-types/double-data-type.md), que es el tipo de datos más eficaz para dichas operaciones. Sin embargo, si un operando es [único](../data-types/single-data-type.md) y el otro no `Double` , Visual Basic realiza la operación en `Single` . Amplía cada operando según sea necesario para el tipo de datos adecuado antes de la operación y el resultado tiene ese tipo de datos.  
  
### <a name="-and--operators"></a>Operadores/y ^  
 El `/` operador solo está definido para los tipos de datos [decimal](../data-types/decimal-data-type.md), [Single](../data-types/single-data-type.md)y [Double](../data-types/double-data-type.md) . Visual Basic amplía cada operando según sea necesario para el tipo de datos adecuado antes de la operación y el resultado tiene ese tipo de datos.  
  
 En la tabla siguiente se muestran los tipos de datos de resultados del `/` operador. Tenga en cuenta que esta tabla es simétrica; para una combinación determinada de tipos de datos de operando, el tipo de datos del resultado es el mismo, independientemente del orden de los operandos.  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|Cualquier tipo entero|  
|`Decimal`|Decimal|Single|Double|Decimal|  
|`Single`|Single|Single|Doble|Single|  
|`Double`|Doble|Double|Double|Double|  
|Cualquier tipo entero|Decimal|Single|Doble|Double|  
  
 El `^` operador solo se define para el `Double` tipo de datos. Visual Basic amplía cada operando según sea necesario `Double` antes de la operación, y el tipo de datos del resultado siempre es `Double` .  
  
## <a name="integer-arithmetic"></a>Aritmética de enteros  
 El tipo de datos de resultado de una operación de entero depende de los tipos de datos de los operandos. En general, Visual Basic usa las siguientes directivas para determinar el tipo de datos del resultado:  
  
- Si ambos operandos de un operador binario tienen el mismo tipo de datos, el resultado tiene ese tipo de datos. Una excepción es `Boolean` , que se fuerza a `Short` .  
  
- Si un operando sin signo participa con un operando firmado, el resultado tiene un tipo con signo, al menos tan grande como un intervalo.  
  
- De lo contrario, el resultado normalmente tiene el mayor de los dos tipos de datos de operando.  
  
 Tenga en cuenta que el tipo de datos del resultado podría no ser el mismo que el tipo de datos del operando.  
  
> [!NOTE]
> El tipo de datos del resultado no es siempre lo suficientemente grande como para contener todos los valores posibles resultantes de la operación. Se <xref:System.OverflowException> puede producir una excepción si el valor es demasiado grande para el tipo de datos del resultado.  
  
### <a name="unary--and--operators"></a>Operadores unarios + y –  
 En la tabla siguiente se muestran los tipos de datos de resultados de los dos operadores unarios, `+` y `–` .  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|Unario`+`|Short|SByte|Byte|Short|UShort|Integer|UInteger|long|ULong|  
|Unario`–`|Short|SByte|Short|Short|Integer|Integer|long|long|Decimal|  
  
### <a name="-and--operators"></a><\< and >Operadores de>  
 En la tabla siguiente se muestran los tipos de datos de los resultados de los dos operadores de desplazamiento de bits, `<<` y `>>` . Visual Basic trata cada operador de desplazamiento de bits como un operador unario en su operando izquierdo (el patrón de bits que se va a desplazar).  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|Integer|UInteger|long|ULong|  
  
 Si el operando izquierdo es `Decimal` , `Single` , `Double` o `String` , Visual Basic intenta convertirlo en `Long` antes de la operación y el tipo de datos del resultado es `Long` . El operando derecho (el número de posiciones de bits que se va a desplazar) debe ser `Integer` o un tipo que se amplíe a `Integer` .  
  
### <a name="binary----and-mod-operators"></a>Operadores binarios +, –, \* y mod  
 En la tabla siguiente se muestran los tipos de datos de resultados de los operadores binarios `+` y y `–` los `*` operadores y `Mod` . Tenga en cuenta que esta tabla es simétrica; para una combinación determinada de tipos de datos de operando, el tipo de datos del resultado es el mismo, independientemente del orden de los operandos.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Integer|Integer|long|long|Decimal|  
|`SByte`|SByte|SByte|Short|Short|Integer|Integer|long|long|Decimal|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|Integer|long|long|Decimal|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|long|long|Decimal|  
|`UInteger`|long|long|UInteger|long|UInteger|long|UInteger|long|ULong|  
|`Long`|long|long|long|long|long|long|long|long|Decimal|  
|`ULong`|Decimal|Decimal|ULong|Decimal|ULong|Decimal|ULong|Decimal|ULong|  
  
### <a name="-operator"></a>Operador \\  
 En la tabla siguiente se muestran los tipos de datos de resultados del `\` operador. Tenga en cuenta que esta tabla es simétrica; para una combinación determinada de tipos de datos de operando, el tipo de datos del resultado es el mismo, independientemente del orden de los operandos.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Integer|Integer|long|long|long|  
|`SByte`|SByte|SByte|Short|Short|Integer|Integer|long|long|long|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|Integer|long|long|long|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|long|long|long|  
|`UInteger`|long|long|UInteger|long|UInteger|long|UInteger|long|ULong|  
|`Long`|long|long|long|long|long|long|long|long|long|  
|`ULong`|long|long|ULong|long|ULong|long|ULong|long|ULong|  
  
 Si alguno de los operandos `\` del operador [es decimal](../data-types/decimal-data-type.md), [Single](../data-types/single-data-type.md)o [Double](../data-types/double-data-type.md), Visual Basic intenta convertirlo a [Long](../data-types/long-data-type.md) antes de la operación y el tipo de datos del resultado es `Long` .  
  
## <a name="relational-and-bitwise-comparisons"></a>Comparaciones relacionales y bit a bit  
 El tipo de datos de resultado de una operación relacional ( `=` , `<>` , `<` , `>` , `<=` , `>=` ) siempre es un `Boolean` [tipo de datos booleano](../data-types/boolean-data-type.md). Lo mismo se aplica a las operaciones lógicas ( `And` , `AndAlso` , `Not` , `Or` , `OrElse` , `Xor` ) en los `Boolean` operandos.  
  
 El tipo de datos de resultado de una operación lógica bit a bit depende de los tipos de datos de los operandos. Tenga en cuenta que `AndAlso` y `OrElse` se definen solo para `Boolean` , y Visual Basic convierte cada operando según sea necesario en `Boolean` antes de realizar la operación.  
  
### <a name="-----and--operators"></a>Operadores =,  <>, \<, > , \<=, and > =  
 Si ambos operandos son `Boolean` , Visual Basic considera `True` que son menores que `False` . Si un tipo numérico se compara con un `String` , Visual Basic intenta convertir `String` en `Double` antes de la operación. Un `Char` `Date` operando o solo se puede comparar con otro operando del mismo tipo de datos. El tipo de datos del resultado es siempre `Boolean` .  
  
### <a name="bitwise-not-operator"></a>Operador not bit a bit  
 En la tabla siguiente se muestran los tipos de datos de resultado para el operador bit a bit `Not` .  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Boolean|SByte|Byte|Short|UShort|Integer|UInteger|long|ULong|  
  
 Si el operando es `Decimal` , `Single` , `Double` o `String` , Visual Basic intenta convertirlo en `Long` antes de la operación y el tipo de datos del resultado es `Long` .  
  
### <a name="bitwise-and-or-and-xor-operators"></a>Operadores bit a bit and, or y XOR  
 En la tabla siguiente se muestran los tipos de datos de resultados para los `And` operadores bit a bit, `Or` y `Xor` . Tenga en cuenta que esta tabla es simétrica; para una combinación determinada de tipos de datos de operando, el tipo de datos del resultado es el mismo, independientemente del orden de los operandos.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Boolean|SByte|Short|Short|Integer|Integer|long|long|long|  
|`SByte`|SByte|SByte|Short|Short|Integer|Integer|long|long|long|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|Integer|long|long|long|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|long|long|long|  
|`UInteger`|long|long|UInteger|long|UInteger|long|UInteger|long|ULong|  
|`Long`|long|long|long|long|long|long|long|long|long|  
|`ULong`|long|long|ULong|long|ULong|long|ULong|long|ULong|  
  
 Si un operando es `Decimal` , `Single` , `Double` o `String` , Visual Basic intenta convertirlo en `Long` antes de la operación y el tipo de datos del resultado es el mismo que si el operando ya hubiera sido `Long` .  
  
## <a name="miscellaneous-operators"></a>Operadores varios  
 El `&` operador solo se define para la concatenación de `String` operandos. Visual Basic convierte cada operando según sea necesario `String` antes de la operación y el tipo de datos del resultado siempre es `String` . Para los fines del `&` operador, se considera que todas las conversiones a `String` son de ampliación, incluso si `Option Strict` es `On` .  
  
 Los `Is` `IsNot` operadores y requieren que ambos operandos sean de un tipo de referencia. La `TypeOf` expresión... `Is` requiere que el primer operando sea de un tipo de referencia y el segundo operando sea el nombre de un tipo de datos. En todos estos casos, el tipo de datos del resultado es `Boolean` .  
  
 El `Like` operador solo se define para la coincidencia de patrones de `String` operandos. Visual Basic intenta convertir cada operando según sea necesario `String` antes de la operación. El tipo de datos del resultado es siempre `Boolean` .  
  
## <a name="see-also"></a>Consulte también

- [Tipos de datos](../data-types/index.md)
- [Operadores y expresiones](../../programming-guide/language-features/operators-and-expressions/index.md)
- [Operadores aritméticos en Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Comparison Operators in Visual Basic](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operadores](index.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Operadores aritméticos](arithmetic-operators.md)
- [Operadores de comparación](comparison-operators.md)
- [Option Strict (instrucción)](../statements/option-strict-statement.md)
