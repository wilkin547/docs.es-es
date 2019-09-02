---
title: Tipos de datos de resultados de operador (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], operator result data types
- result data types [Visual Basic]
- operator result data types [Visual Basic]
- operators [Visual Basic], data types
- data types [Visual Basic], ranges
- operators [Visual Basic], result data types
ms.assetid: 9d524533-e1a1-4aa8-b1b8-622068173d06
ms.openlocfilehash: b0ebdb723df6bdb4f74e1558537c307ddb917f64
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2019
ms.locfileid: "69923275"
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
  
 Si alguno de los operandos `+`de `–`una `*`operación `/`,, `Mod` , o `Decimal` es y el otro no `Single` es `Double`o, Visual Basic amplía el otro operando a `Decimal`. Realiza la operación en `Decimal`y el tipo de datos del resultado es. `Decimal`  
  
## <a name="floating-point-arithmetic"></a>Aritmética de punto flotante  
 Visual Basic realiza la mayoría de la aritmética de punto flotante en [Double](../../../visual-basic/language-reference/data-types/double-data-type.md), que es el tipo de datos más eficaz para dichas operaciones. Sin embargo, si un operando es [único](../../../visual-basic/language-reference/data-types/single-data-type.md) y el otro `Double`no, Visual Basic realiza la operación `Single`en. Amplía cada operando según sea necesario para el tipo de datos adecuado antes de la operación y el resultado tiene ese tipo de datos.  
  
### <a name="-and--operators"></a>Operadores/y ^  
 El `/` operador solo está definido para los tipos de datos [decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)y [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) . Visual Basic amplía cada operando según sea necesario para el tipo de datos adecuado antes de la operación y el resultado tiene ese tipo de datos.  
  
 En la tabla siguiente se muestran los tipos de datos `/` de resultados del operador. Tenga en cuenta que esta tabla es simétrica; para una combinación determinada de tipos de datos de operando, el tipo de datos del resultado es el mismo, independientemente del orden de los operandos.  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|Cualquier tipo entero|  
|`Decimal`|Decimal|Single|Double|Decimal|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|Cualquier tipo entero|Decimal|Single|Double|Double|  
  
 El `^` operador solo se define para el `Double` tipo de datos. Visual Basic amplía cada operando según sea necesario `Double` antes de la operación, y el tipo de datos del `Double`resultado siempre es.  
  
## <a name="integer-arithmetic"></a>Aritmética de enteros  
 El tipo de datos de resultado de una operación de entero depende de los tipos de datos de los operandos. En general, Visual Basic usa las siguientes directivas para determinar el tipo de datos del resultado:  
  
- Si ambos operandos de un operador binario tienen el mismo tipo de datos, el resultado tiene ese tipo de datos. Una excepción es `Boolean`, que se fuerza a `Short`.  
  
- Si un operando sin signo participa con un operando firmado, el resultado tiene un tipo con signo, al menos tan grande como un intervalo.  
  
- De lo contrario, el resultado normalmente tiene el mayor de los dos tipos de datos de operando.  
  
 Tenga en cuenta que el tipo de datos del resultado podría no ser el mismo que el tipo de datos del operando.  
  
> [!NOTE]
> El tipo de datos del resultado no es siempre lo suficientemente grande como para contener todos los valores posibles resultantes de la operación. Se <xref:System.OverflowException> puede producir una excepción si el valor es demasiado grande para el tipo de datos del resultado.  
  
### <a name="unary--and--operators"></a>Operadores unarios + y –  
 En la tabla siguiente se muestran los tipos de datos de resultados de los `+` dos `–`operadores unarios, y.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|Unario`+`|Breve|SByte|Byte|Breve|UShort|Entero|UInteger|long|ULong|  
|Unario`–`|Breve|SByte|Breve|Breve|Entero|Entero|long|long|Decimal|  
  
### <a name="-and--operators"></a><\<Operadores > y >  
 En la tabla siguiente se muestran los tipos de datos de los resultados de los dos `<<` operadores `>>`de desplazamiento de bits, y. Visual Basic trata cada operador de desplazamiento de bits como un operador unario en su operando izquierdo (el patrón de bits que se va a desplazar).  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Breve|SByte|Byte|Breve|UShort|Entero|UInteger|long|ULong|  
  
 Si el operando izquierdo `Decimal`es `Single`, `Double`, o `String`, Visual Basic intenta convertirlo en `Long` antes de la operación y el tipo de datos del resultado `Long`es. El operando derecho (el número de posiciones de bits que se va `Integer` a desplazar) debe ser `Integer`o un tipo que se amplíe a.  
  
### <a name="binary----and-mod-operators"></a>Operadores binarios +, –, * y mod  
 En la tabla siguiente se muestran los tipos de datos de `+` resultados `–` de los operadores `*` binarios y y los `Mod` operadores y. Tenga en cuenta que esta tabla es simétrica; para una combinación determinada de tipos de datos de operando, el tipo de datos del resultado es el mismo, independientemente del orden de los operandos.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Breve|SByte|Breve|Breve|Entero|Entero|long|long|Decimal|  
|`SByte`|SByte|SByte|Breve|Breve|Entero|Entero|long|long|Decimal|  
|`Byte`|Breve|Breve|Byte|Breve|UShort|Entero|UInteger|long|ULong|  
|`Short`|Breve|Breve|Breve|Breve|Entero|Entero|long|long|Decimal|  
|`UShort`|Entero|Entero|UShort|Entero|UShort|Entero|UInteger|long|ULong|  
|`Integer`|Entero|Entero|Entero|Entero|Entero|Entero|long|long|Decimal|  
|`UInteger`|long|long|UInteger|long|UInteger|long|UInteger|long|ULong|  
|`Long`|long|long|long|long|long|long|long|long|Decimal|  
|`ULong`|Decimal|Decimal|ULong|Decimal|ULong|Decimal|ULong|Decimal|ULong|  
  
### <a name="-operator"></a>\ (Operador)  
 En la tabla siguiente se muestran los tipos de datos `\` de resultados del operador. Tenga en cuenta que esta tabla es simétrica; para una combinación determinada de tipos de datos de operando, el tipo de datos del resultado es el mismo, independientemente del orden de los operandos.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Breve|SByte|Breve|Breve|Entero|Entero|long|long|long|  
|`SByte`|SByte|SByte|Breve|Breve|Entero|Entero|long|long|long|  
|`Byte`|Breve|Breve|Byte|Breve|UShort|Entero|UInteger|long|ULong|  
|`Short`|Breve|Breve|Breve|Breve|Entero|Entero|long|long|long|  
|`UShort`|Entero|Entero|UShort|Entero|UShort|Entero|UInteger|long|ULong|  
|`Integer`|Entero|Entero|Entero|Entero|Entero|Entero|long|long|long|  
|`UInteger`|long|long|UInteger|long|UInteger|long|UInteger|long|ULong|  
|`Long`|long|long|long|long|long|long|long|long|long|  
|`ULong`|long|long|ULong|long|ULong|long|ULong|long|ULong|  
  
 Si alguno de `\` los operandos del operador es [decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)o [Double](../../../visual-basic/language-reference/data-types/double-data-type.md), Visual Basic intenta convertirlo a [Long](../../../visual-basic/language-reference/data-types/long-data-type.md) antes de la operación y el tipo de datos del resultado `Long`es.  
  
## <a name="relational-and-bitwise-comparisons"></a>Comparaciones relacionales y bit a bit  
 El tipo de datos de resultado de una operación`=`relacional `<`( `>`, `<=` `<>`, `>=`,,, `Boolean`) siempre es un [tipo de datos booleano](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Lo mismo se aplica a las operaciones lógicas `AndAlso`( `Not``And`, `Or`, `OrElse`, `Xor`,, `Boolean` ) en los operandos.  
  
 El tipo de datos de resultado de una operación lógica bit a bit depende de los tipos de datos de los operandos. Tenga en `AndAlso` cuenta `OrElse` que y se definen `Boolean`solo para, y Visual Basic convierte cada operando según `Boolean` sea necesario en antes de realizar la operación.  
  
### <a name="-----and--operators"></a>=, < >, \<, >, \<= y > = operadores  
 Si ambos operandos son, `Boolean`Visual Basic considera `True` que son menores que `False`. Si un tipo numérico se compara con un `String`, Visual Basic intenta `String` convertir en `Double` antes de la operación. Un `Char` operando o `Date` solo se puede comparar con otro operando del mismo tipo de datos. El tipo de datos del resultado `Boolean`es siempre.  
  
### <a name="bitwise-not-operator"></a>Operador not bit a bit  
 En la tabla siguiente se muestran los tipos de datos de `Not` resultado para el operador bit a bit.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Boolean|SByte|Byte|Breve|UShort|Entero|UInteger|long|ULong|  
  
 Si el operando `Decimal`es `Single`, `Double`, o `String`, Visual Basic intenta convertirlo en `Long` antes de la operación y el tipo de datos del resultado `Long`es.  
  
### <a name="bitwise-and-or-and-xor-operators"></a>Operadores bit a bit and, or y XOR  
 En la tabla siguiente se muestran los tipos de datos de `And`resultados `Or`para los `Xor` operadores bit a bit, y. Tenga en cuenta que esta tabla es simétrica; para una combinación determinada de tipos de datos de operando, el tipo de datos del resultado es el mismo, independientemente del orden de los operandos.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Boolean|SByte|Breve|Breve|Entero|Entero|long|long|long|  
|`SByte`|SByte|SByte|Breve|Breve|Entero|Entero|long|long|long|  
|`Byte`|Breve|Breve|Byte|Breve|UShort|Entero|UInteger|long|ULong|  
|`Short`|Breve|Breve|Breve|Breve|Entero|Entero|long|long|long|  
|`UShort`|Entero|Entero|UShort|Entero|UShort|Entero|UInteger|long|ULong|  
|`Integer`|Entero|Entero|Entero|Entero|Entero|Entero|long|long|long|  
|`UInteger`|long|long|UInteger|long|UInteger|long|UInteger|long|ULong|  
|`Long`|long|long|long|long|long|long|long|long|long|  
|`ULong`|long|long|ULong|long|ULong|long|ULong|long|ULong|  
  
 Si un operando `Decimal`es `Single`, `Double`, o `String`, Visual Basic intenta convertirlo en `Long` antes de la operación y el tipo de datos del resultado es el mismo que si el operando ya `Long`hubiera sido.  
  
## <a name="miscellaneous-operators"></a>Operadores varios  
 El `&` operador solo se define para la concatenación `String` de operandos. Visual Basic convierte cada operando según sea necesario `String` antes de la operación y el tipo de datos del resultado `String`siempre es. `&` Para los fines del operador, se considera que todas las conversiones a `String` son de ampliación, incluso si `Option Strict` es `On`.  
  
 Los `Is` operadores `IsNot` y requieren que ambos operandos sean de un tipo de referencia. `TypeOf`... `Is` la expresión requiere que el primer operando sea de un tipo de referencia y el segundo operando sea el nombre de un tipo de datos. En todos estos casos, el tipo de datos `Boolean`del resultado es.  
  
 El `Like` operador solo se define para la coincidencia de `String` patrones de operandos. Visual Basic intenta convertir cada operando según sea necesario `String` antes de la operación. El tipo de datos del resultado `Boolean`es siempre.  
  
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
