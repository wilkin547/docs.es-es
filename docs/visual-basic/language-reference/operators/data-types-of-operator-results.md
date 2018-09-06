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
ms.openlocfilehash: 135c44217debcddb15fd4cef7e73ca2f98903c43
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43872587"
---
# <a name="data-types-of-operator-results-visual-basic"></a>Tipos de datos de resultados de operador (Visual Basic)
Visual Basic determina el tipo de datos de resultado de una operación basada en los tipos de datos de los operandos. En algunos casos, esto podría ser un tipo de datos con un intervalo mayor que el de alguno de los operandos.  
  
## <a name="data-type-ranges"></a>Intervalos de tipos de datos  
 Los intervalos de los tipos de datos pertinentes, en orden de menor a mayor, son los siguientes:  
  
-   [Booleano](../../../visual-basic/language-reference/data-types/boolean-data-type.md) , dos valores posibles  
  
-   [SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [bytes](../../../visual-basic/language-reference/data-types/byte-data-type.md) : 256 valores posibles de enteros  
  
-   [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md) : 65.536 (6.5 … E + 4) valores integrales posibles  
  
-   [Entero](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) : 4.294.967.296 (4.2 … E + 9) valores integrales posibles  
  
-   [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md) : 18.446.744.073.709.551.615 (1.8 … E + 19) valores integrales posibles  
  
-   [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) : 1.5 … E + 29 posibles valores enteros, máximos rango 7.9 … E + 28 (valor absoluto)  
  
-   [Solo](../../../visual-basic/language-reference/data-types/single-data-type.md) : intervalo máximo 3.4 … E + 38 (valor absoluto)  
  
-   [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) : intervalo máximo 1.7 … E + 308 (valor absoluto)  
  
 Para obtener más información sobre los tipos de datos de Visual Basic, vea [tipos de datos](../../../visual-basic/language-reference/data-types/index.md).  
  
 Si un operando se evalúa como [nada](../../../visual-basic/language-reference/nothing.md), los operadores aritméticos de Visual Basic tratan como cero.  
  
## <a name="decimal-arithmetic"></a>Aritmética decimal  
 Tenga en cuenta que el [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) es de tipo de datos ni punto flotante ni entero.  
  
 Si alguno de los operandos de un `+`, `–`, `*`, `/`, o `Mod` operación es `Decimal` y el otro no lo es `Single` o `Double`, Visual Basic se amplía el otro operando a `Decimal`. Realiza la operación en `Decimal`, y el tipo de datos resultante es `Decimal`.  
  
## <a name="floating-point-arithmetic"></a>Aritmética de punto flotante  
 Visual Basic realiza la mayoría aritmética de punto flotante en [doble](../../../visual-basic/language-reference/data-types/double-data-type.md), que es el más eficaz de los datos de tipo para dichas operaciones. Sin embargo, si un operando es [único](../../../visual-basic/language-reference/data-types/single-data-type.md) y el otro no lo es `Double`, Visual Basic realiza la operación en `Single`. Amplía cada operando según sea necesario para el tipo de datos adecuado antes de la operación, y el resultado tiene ese tipo de datos.  
  
### <a name="-and--operators"></a>/ y ^ operadores  
 El `/` operador está definido solo para el [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [único](../../../visual-basic/language-reference/data-types/single-data-type.md), y [doble](../../../visual-basic/language-reference/data-types/double-data-type.md) tipos de datos. Visual Basic amplía cada operando según sea necesario para el tipo de datos adecuado antes de la operación, y el resultado tiene ese tipo de datos.  
  
 En la tabla siguiente se muestra el resultado de los tipos de datos para el `/` operador. Tenga en cuenta que esta tabla es simétrica; para una combinación determinada de tipos de datos del operando, el tipo de datos del resultado es el mismo independientemente del orden de los operandos.  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|Cualquier tipo entero|  
|`Decimal`|Decimal|Single|Doble|Decimal|  
|`Single`|Single|Single|Doble|Single|  
|`Double`|Doble|Doble|Doble|Doble|  
|Cualquier tipo entero|Decimal|Single|Doble|Doble|  
  
 El `^` operador está definido solo para el `Double` tipo de datos. Visual Basic amplía cada operando según sea necesario para `Double` antes de la operación y el resultado siempre es el tipo de datos `Double`.  
  
## <a name="integer-arithmetic"></a>Aritmética de enteros  
 El tipo de datos de resultado de una operación de enteros depende de los tipos de datos de los operandos. En general, Visual Basic utiliza las siguientes directivas para determinar el tipo de datos de resultado:  
  
-   Si ambos operandos de un operador binario tienen el mismo tipo de datos, el resultado tiene ese tipo de datos. Una excepción es `Boolean`, que se ve obligado a `Short`.  
  
-   Si participa un operando sin signo con un operando con signo, el resultado tiene un tipo con signo con al menos tan grande un intervalo como uno de los operandos.  
  
-   En caso contrario, el resultado normalmente tiene el mayor de los dos tipos de datos de operando.  
  
 Observe que el tipo de datos resultante podría no ser igual que cualquier tipo de datos de operando.  
  
> [!NOTE]
>  El tipo de datos de resultado no siempre es lo suficientemente grande como para contener todos los posibles valores resultantes de la operación. Un <xref:System.OverflowException> puede producirse una excepción si el valor es demasiado grande para el tipo de datos de resultado.  
  
### <a name="unary--and--operators"></a>Unarios + y – operadores  
 En la tabla siguiente se muestra el resultado los tipos de datos para los dos operadores unarios, `+` y `–`.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|Unario `+`|Short|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|Unario `–`|Short|SByte|Short|Short|Entero|Integer|Long|Long|Decimal|  
  
### <a name="-and--operators"></a><\< y >> operadores  
 En la tabla siguiente se muestra el resultado los tipos de datos para los dos operadores de desplazamiento de bits, `<<` y `>>`. Visual Basic trata a cada operador de desplazamiento de bits como un operador unario de su operando izquierdo (el patrón de bits que se desplazarán).  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
  
 Si el operando izquierdo es `Decimal`, `Single`, `Double`, o `String`, Visual Basic intenta convertirlo a `Long` antes de la operación y el resultado es de tipo de datos `Long`. El operando derecho (el número de posiciones de bit a desplazar) debe ser `Integer` o un tipo que se amplía a `Integer`.  
  
### <a name="binary----and-mod-operators"></a>Binarios +, -, * y los operadores Mod  
 En la tabla siguiente muestra el resultado de los tipos de datos para el archivo binario `+` y `–` operadores y `*` y `Mod` operadores. Tenga en cuenta que esta tabla es simétrica; para una combinación determinada de tipos de datos del operando, el tipo de datos del resultado es el mismo independientemente del orden de los operandos.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Entero|Integer|Long|Long|Decimal|  
|`SByte`|SByte|SByte|Short|Short|Entero|Integer|Long|Long|Decimal|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Entero|Integer|Long|Long|Decimal|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|Long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|Long|Long|Decimal|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Decimal|  
|`ULong`|Decimal|Decimal|ULong|Decimal|ULong|Decimal|ULong|Decimal|ULong|  
  
### <a name="-operator"></a>\ (Operador)  
 En la tabla siguiente se muestra el resultado de los tipos de datos para el `\` operador. Tenga en cuenta que esta tabla es simétrica; para una combinación determinada de tipos de datos del operando, el tipo de datos del resultado es el mismo independientemente del orden de los operandos.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Entero|Integer|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Entero|Integer|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Entero|Integer|Long|Long|Long|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|Long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 Si alguno de los operandos de la `\` operador es [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [único](../../../visual-basic/language-reference/data-types/single-data-type.md), o [doble](../../../visual-basic/language-reference/data-types/double-data-type.md), Visual Basic intenta convertirlo a [prolongada](../../../visual-basic/language-reference/data-types/long-data-type.md)antes de la operación y el resultado es de tipo de datos `Long`.  
  
## <a name="relational-and-bitwise-comparisons"></a>Comparaciones relacionales y bit a bit  
 El tipo de datos de resultado de una operación relacional (`=`, `<>`, `<`, `>`, `<=`, `>=`) siempre es `Boolean` [tipo de datos Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Lo mismo puede decirse de operaciones lógicas (`And`, `AndAlso`, `Not`, `Or`, `OrElse`, `Xor`) en `Boolean` operandos.  
  
 El tipo de datos de resultado de una operación bit a bit lógica depende de los tipos de datos de los operandos. Tenga en cuenta que `AndAlso` y `OrElse` sólo se definen para `Boolean`, y Visual Basic convierte cada operando según sea necesario para `Boolean` antes de realizar la operación.  
  
### <a name="-----and--operators"></a>= <>, \<, >, \<= y > = operadores  
 Si ambos operandos son `Boolean`, Visual Basic considera `True` sea inferior a `False`. Si se compara con un tipo numérico con un `String`, Visual Basic intenta convertir la `String` a `Double` antes de la operación. Un `Char` o `Date` operando puede compararse solo con el otro operando del mismo tipo de datos. El tipo de datos de resultado siempre es `Boolean`.  
  
### <a name="bitwise-not-operator"></a>Bit a bit no operador  
 En la tabla siguiente se muestra el resultado de tipos de datos para el bit a bit `Not` operador.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Booleano|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
  
 Si el operando es `Decimal`, `Single`, `Double`, o `String`, Visual Basic intenta convertirlo a `Long` antes de la operación y el resultado es de tipo de datos `Long`.  
  
### <a name="bitwise-and-or-and-xor-operators"></a>Bit a bit y, o bien y los operadores de Xor  
 En la tabla siguiente se muestra el resultado de tipos de datos para el bit a bit `And`, `Or`, y `Xor` operadores. Tenga en cuenta que esta tabla es simétrica; para una combinación determinada de tipos de datos del operando, el tipo de datos del resultado es el mismo independientemente del orden de los operandos.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Booleano|SByte|Short|Short|Entero|Integer|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Entero|Integer|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Entero|Integer|Long|Long|Long|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|Long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 Si es un operando `Decimal`, `Single`, `Double`, o `String`, Visual Basic intenta convertirlo a `Long` antes de la operación y los datos de resultado el tipo es el mismo que el del operando ya había sido `Long`.  
  
## <a name="miscellaneous-operators"></a>Operadores varios  
 El `&` operador está definido para la concatenación de `String` operandos. Visual Basic convierte cada operando según sea necesario para `String` antes de la operación y el resultado siempre es el tipo de datos `String`. Para los fines de la `&` operador, todas las conversiones a `String` se consideran de ampliación, incluso si `Option Strict` es `On`.  
  
 El `Is` y `IsNot` operadores requieren que ambos operandos de un tipo de referencia. El `TypeOf`... `Is` expresión requiere que el primer operando de un tipo de referencia y el segundo operando en el nombre de un tipo de datos. En estos casos los datos del resultado es de tipo `Boolean`.  
  
 El `Like` operador está definido solo para la coincidencia de patrones de `String` operandos. Visual Basic intenta convertir cada operando según sea necesario para `String` antes de la operación. El tipo de datos de resultado siempre es `Boolean`.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)  
 [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Operadores de comparación en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Operadores](../../../visual-basic/language-reference/operators/index.md)  
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Operadores de comparación](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)
