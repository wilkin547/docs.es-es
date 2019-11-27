---
title: Tipos de datos de resultados de operador
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], operator result data types
- result data types [Visual Basic]
- operator result data types [Visual Basic]
- operators [Visual Basic], data types
- data types [Visual Basic], ranges
- operators [Visual Basic], result data types
ms.assetid: 9d524533-e1a1-4aa8-b1b8-622068173d06
ms.openlocfilehash: 3867d433ea5f9a6effe70db0ff4162390fb50b5c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331466"
---
# <a name="data-types-of-operator-results-visual-basic"></a>Tipos de datos de resultados de operador (Visual Basic)
Visual Basic determina el tipo de datos de resultado de una operación en función de los tipos de datos de los operandos. En algunos casos, podría tratarse de un tipo de datos con un intervalo mayor que el de uno de los operandos.  
  
## <a name="data-type-ranges"></a>Intervalos de tipo de datos  
 Los intervalos de los tipos de datos pertinentes, en orden de menor a mayor, son los siguientes:  
  
- [Booleano](../../../visual-basic/language-reference/data-types/boolean-data-type.md) : dos valores posibles  
  
- [SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [byte](../../../visual-basic/language-reference/data-types/byte-data-type.md) : 256 posibles valores integrales  
  
- [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [ushort](../../../visual-basic/language-reference/data-types/ushort-data-type.md) : 65.536 (6.5... E + 4) posibles valores integrales  
  
- [Entero](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) : 4.294.967.296 (4.2... E + 9) posibles valores integrales  
  
- [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md) : 18446744073709551615 (1.8... E + 19) posibles valores integrales  
  
- [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) : 1,5... e + 29 posibles valores integrales, intervalo máximo de 7,9... e + 28 (valor absoluto)  
  
- [Único](../../../visual-basic/language-reference/data-types/single-data-type.md) : intervalo máximo 3.4... E + 38 (valor absoluto)  
  
- [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) : intervalo máximo 1.7... E + 308 (valor absoluto)  
  
 Para obtener más información sobre los tipos de datos de Visual Basic, vea [tipos de datos](../../../visual-basic/language-reference/data-types/index.md).  
  
 Si un operando se evalúa como [Nothing](../../../visual-basic/language-reference/nothing.md), los operadores aritméticos Visual Basic lo consideran como cero.  
  
## <a name="decimal-arithmetic"></a>Aritmética decimal  
 Tenga en cuenta que el tipo de datos [decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) no es ningún punto flotante ni entero.  
  
 Si uno de los operandos de una `+`, `–`, `*`, `/`o `Mod` es `Decimal` y el otro no `Single` o `Double`, Visual Basic amplía el otro operando a `Decimal`. Realiza la operación en `Decimal`y el tipo de datos del resultado es `Decimal`.  
  
## <a name="floating-point-arithmetic"></a>Aritmética de punto flotante  
 Visual Basic realiza la mayoría de la aritmética de punto flotante en [Double](../../../visual-basic/language-reference/data-types/double-data-type.md), que es el tipo de datos más eficaz para dichas operaciones. Sin embargo, si un operando es [único](../../../visual-basic/language-reference/data-types/single-data-type.md) y el otro no se `Double`, Visual Basic realiza la operación en `Single`. Amplía cada operando según sea necesario para el tipo de datos adecuado antes de la operación y el resultado tiene ese tipo de datos.  
  
### <a name="-and--operators"></a>Operadores/y ^  
 El operador `/` solo está definido para los tipos de datos [decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)y [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) . Visual Basic amplía cada operando según sea necesario para el tipo de datos adecuado antes de la operación y el resultado tiene ese tipo de datos.  
  
 En la tabla siguiente se muestran los tipos de datos de resultados del operador `/`. Tenga en cuenta que esta tabla es simétrica; para una combinación determinada de tipos de datos de operando, el tipo de datos del resultado es el mismo, independientemente del orden de los operandos.  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|Cualquier tipo entero|  
|`Decimal`|Decimal|único|Doble|Decimal|  
|`Single`|único|único|Doble|único|  
|`Double`|Doble|Doble|Doble|Doble|  
|Cualquier tipo entero|Decimal|único|Doble|Doble|  
  
 El operador `^` solo se define para el tipo de datos `Double`. Visual Basic amplía cada operando según sea necesario para `Double` antes de la operación, y el tipo de datos del resultado siempre es `Double`.  
  
## <a name="integer-arithmetic"></a>Aritmética de enteros  
 El tipo de datos de resultado de una operación de entero depende de los tipos de datos de los operandos. En general, Visual Basic usa las siguientes directivas para determinar el tipo de datos del resultado:  
  
- Si ambos operandos de un operador binario tienen el mismo tipo de datos, el resultado tiene ese tipo de datos. Una excepción es `Boolean`, que se fuerza a `Short`.  
  
- Si un operando sin signo participa con un operando firmado, el resultado tiene un tipo con signo, al menos tan grande como un intervalo.  
  
- De lo contrario, el resultado normalmente tiene el mayor de los dos tipos de datos de operando.  
  
 Tenga en cuenta que el tipo de datos del resultado podría no ser el mismo que el tipo de datos del operando.  
  
> [!NOTE]
> El tipo de datos del resultado no es siempre lo suficientemente grande como para contener todos los valores posibles resultantes de la operación. Se puede producir una excepción <xref:System.OverflowException> si el valor es demasiado grande para el tipo de datos del resultado.  
  
### <a name="unary--and--operators"></a>Operadores unarios + y –  
 En la tabla siguiente se muestran los tipos de datos de resultados de los dos operadores unarios, `+` y `–`.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`+` unario|Short|SByte|Byte|Short|UShort|Entero|UInteger|Long|ULong|  
|`–` unario|Short|SByte|Short|Short|Entero|Entero|Long|Long|Decimal|  
  
### <a name="-and--operators"></a>Operadores <\< y > >  
 En la tabla siguiente se muestran los tipos de datos de resultados de los dos operadores de desplazamiento de bits, `<<` y `>>`. Visual Basic trata cada operador de desplazamiento de bits como un operador unario en su operando izquierdo (el patrón de bits que se va a desplazar).  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|Entero|UInteger|Long|ULong|  
  
 Si el operando izquierdo es `Decimal`, `Single`, `Double`o `String`, Visual Basic intenta convertirlo en `Long` antes de la operación y el tipo de datos del resultado es `Long`. El operando derecho (el número de posiciones de bits que se va a desplazar) debe ser `Integer` o un tipo que se amplíe a `Integer`.  
  
### <a name="binary----and-mod-operators"></a>Operadores binarios +, –, \*y mod  
 En la tabla siguiente se muestran los tipos de datos de resultado de los operadores `+` y `–` binarios y los operadores `*` y `Mod`. Tenga en cuenta que esta tabla es simétrica; para una combinación determinada de tipos de datos de operando, el tipo de datos del resultado es el mismo, independientemente del orden de los operandos.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Entero|Entero|Long|Long|Decimal|  
|`SByte`|SByte|SByte|Short|Short|Entero|Entero|Long|Long|Decimal|  
|`Byte`|Short|Short|Byte|Short|UShort|Entero|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Entero|Entero|Long|Long|Decimal|  
|`UShort`|Entero|Entero|UShort|Entero|UShort|Entero|UInteger|Long|ULong|  
|`Integer`|Entero|Entero|Entero|Entero|Entero|Entero|Long|Long|Decimal|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Decimal|  
|`ULong`|Decimal|Decimal|ULong|Decimal|ULong|Decimal|ULong|Decimal|ULong|  
  
### <a name="-operator"></a>Operador \\  
 En la tabla siguiente se muestran los tipos de datos de resultados del operador `\`. Tenga en cuenta que esta tabla es simétrica; para una combinación determinada de tipos de datos de operando, el tipo de datos del resultado es el mismo, independientemente del orden de los operandos.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Entero|Entero|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Entero|Entero|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Entero|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Entero|Entero|Long|Long|Long|  
|`UShort`|Entero|Entero|UShort|Entero|UShort|Entero|UInteger|Long|ULong|  
|`Integer`|Entero|Entero|Entero|Entero|Entero|Entero|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 Si alguno de los operandos del operador `\` es [decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)o [Double](../../../visual-basic/language-reference/data-types/double-data-type.md), Visual Basic intenta convertirlo a [Long](../../../visual-basic/language-reference/data-types/long-data-type.md) antes de la operación y el tipo de datos del resultado es `Long`.  
  
## <a name="relational-and-bitwise-comparisons"></a>Comparaciones relacionales y bit a bit  
 El tipo de datos de resultado de una operación relacional (`=`, `<>`, `<`, `>`, `<=`, `>=`) siempre es `Boolean`[tipo de datos booleano](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Lo mismo se aplica a las operaciones lógicas (`And`, `AndAlso`, `Not`, `Or`, `OrElse`, `Xor`) en los operandos de `Boolean`.  
  
 El tipo de datos de resultado de una operación lógica bit a bit depende de los tipos de datos de los operandos. Tenga en cuenta que `AndAlso` y `OrElse` se definen solo para `Boolean`y Visual Basic convierte cada operando según sea necesario para `Boolean` antes de realizar la operación.  
  
### <a name="-----and--operators"></a>=, < >, \<, >, \<= y > = operadores  
 Si ambos operandos son `Boolean`, Visual Basic considera que `True` es menor que `False`. Si un tipo numérico se compara con un `String`, Visual Basic intenta convertir el `String` en `Double` antes de la operación. Un operando `Char` o `Date` se puede comparar solo con otro operando del mismo tipo de datos. El tipo de datos del resultado siempre es `Boolean`.  
  
### <a name="bitwise-not-operator"></a>Operador not bit a bit  
 En la tabla siguiente se muestran los tipos de datos de resultados para el operador bit a bit `Not`.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Booleano|SByte|Byte|Short|UShort|Entero|UInteger|Long|ULong|  
  
 Si el operando es `Decimal`, `Single`, `Double`o `String`Visual Basic intenta convertirlo en `Long` antes de la operación y el tipo de datos del resultado es `Long`.  
  
### <a name="bitwise-and-or-and-xor-operators"></a>Operadores bit a bit and, or y XOR  
 En la tabla siguiente se muestran los tipos de datos de resultado de los operadores bit a bit `And`, `Or`y `Xor`. Tenga en cuenta que esta tabla es simétrica; para una combinación determinada de tipos de datos de operando, el tipo de datos del resultado es el mismo, independientemente del orden de los operandos.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Booleano|SByte|Short|Short|Entero|Entero|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Entero|Entero|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Entero|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Entero|Entero|Long|Long|Long|  
|`UShort`|Entero|Entero|UShort|Entero|UShort|Entero|UInteger|Long|ULong|  
|`Integer`|Entero|Entero|Entero|Entero|Entero|Entero|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 Si un operando es `Decimal`, `Single`, `Double`o `String`, Visual Basic intenta convertirlo en `Long` antes de la operación y el tipo de datos del resultado es el mismo que si ese operando ya se hubiera `Long`.  
  
## <a name="miscellaneous-operators"></a>Operadores varios  
 El operador `&` solo se define para la concatenación de operandos `String`. Visual Basic convierte cada operando según sea necesario para `String` antes de la operación, y el tipo de datos del resultado siempre es `String`. En el caso del operador `&`, se considera que todas las conversiones a `String` se amplían, incluso si se `On``Option Strict`.  
  
 Los operadores `Is` y `IsNot` requieren que ambos operandos sean de un tipo de referencia. La expresión `TypeOf`...`Is` requiere que el primer operando sea de un tipo de referencia y el segundo operando sea el nombre de un tipo de datos. En todos estos casos, el tipo de datos del resultado es `Boolean`.  
  
 El operador `Like` solo se define para la coincidencia de patrones de `String` operandos. Visual Basic intenta convertir cada operando según sea necesario para `String` antes de la operación. El tipo de datos del resultado siempre es `Boolean`.  
  
## <a name="see-also"></a>Vea también

- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Operadores de comparación en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operadores](../../../visual-basic/language-reference/operators/index.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operadores de comparación](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)
