---
title: Tipos de datos de resultados de operador (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- data types [Visual Basic], operator result data types
- result data types
- operator result data types
- operators [Visual Basic], data types
- data types [Visual Basic], ranges
- operators [Visual Basic], result data types
ms.assetid: 9d524533-e1a1-4aa8-b1b8-622068173d06
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 577be6330cb76da436470c383841a717dd6e3200
ms.lasthandoff: 03/13/2017

---
# <a name="data-types-of-operator-results-visual-basic"></a>Tipos de datos de resultados de operador (Visual Basic)
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Determina el tipo de datos de resultado de una operación basándose en los tipos de datos de los operandos. En algunos casos, esto podría ser un tipo de datos con un intervalo mayor que el de cualquiera de los operandos.  
  
## <a name="data-type-ranges"></a>Intervalos de tipos de datos  
 Los intervalos de los tipos de datos relevantes, en orden de menor a mayor, son los siguientes:  
  
-   [Booleano](../../../visual-basic/language-reference/data-types/boolean-data-type.md) : dos valores posibles  
  
-   [SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [bytes](../../../visual-basic/language-reference/data-types/byte-data-type.md) — 256 valores enteros posibles  
  
-   [Corto](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md) : 65.536 (6.5... E + 4) valores integrales posibles  
  
-   [Entero](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) : 4.294.967.296 (4.2... E + 9) valores integrales posibles  
  
-   [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md) : 18.446.744.073.709.551.615 (1.8... e+19) valores integrales posibles  
  
-   [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) — 1.5... E + 29 valores integrales posibles, máximos intervalo 7.9... e+28 (valor absoluto)  
  
-   [Solo](../../../visual-basic/language-reference/data-types/single-data-type.md) : intervalo máximo 3.4... E + 38 (valor absoluto)  
  
-   [Doble](../../../visual-basic/language-reference/data-types/double-data-type.md) — intervalo máximo 1.7... E + 308 (valor absoluto)  
  
 Para obtener más información sobre [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] tipos de datos, vea [tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
 Si un operando se evalúa como [nada](../../../visual-basic/language-reference/nothing.md), el [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] operadores aritméticos tratan como cero.  
  
## <a name="decimal-arithmetic"></a>Aritmética decimal  
 Tenga en cuenta que el [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) es de tipo de datos ni punto flotante ni entero.  
  
 Si alguno de los operandos de una `+`, `–`, `*`, `/`, o `Mod` operación es `Decimal` y el otro no `Single` o `Double`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] amplía el otro operando a `Decimal`. Realiza la operación en `Decimal`, y el tipo de datos del resultado es `Decimal`.  
  
## <a name="floating-point-arithmetic"></a>Aritmética de punto flotante  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]realiza la mayoría aritmética de punto flotante en [doble](../../../visual-basic/language-reference/data-types/double-data-type.md), que es el más eficaz de datos escriba para esas operaciones. Sin embargo, si un operando es [único](../../../visual-basic/language-reference/data-types/single-data-type.md) y el otro no `Double`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] realiza la operación en `Single`. Amplía cada operando según sea necesario para el tipo de datos adecuado antes de la operación, y el resultado tiene ese tipo de datos.  
  
### <a name="-and--operators"></a>/ y ^ operadores  
 El `/` operador solo se define para la [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [único](../../../visual-basic/language-reference/data-types/single-data-type.md), y [doble](../../../visual-basic/language-reference/data-types/double-data-type.md) tipos de datos. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]amplía cada operando según sea necesario para el tipo de datos adecuado antes de la operación y el resultado tiene ese tipo de datos.  
  
 En la tabla siguiente muestra el resultado de tipos de datos para el `/` operador. Tenga en cuenta que esta tabla es simétrica; para una combinación determinada de tipos de datos de operando, el tipo de datos del resultado es el mismo independientemente del orden de los operandos.  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|Cualquier tipo entero|  
|`Decimal`|Decimal|Single|Doble|Decimal|  
|`Single`|Single|Single|Doble|Single|  
|`Double`|Doble|Double|Double|Doble|  
|Cualquier tipo entero|Decimal|Single|Doble|Doble|  
  
 El `^` operador solo se define para el `Double` el tipo de datos. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]amplía cada operando según sea necesario para `Double` antes de la operación y el resultado siempre es el tipo de datos `Double`.  
  
## <a name="integer-arithmetic"></a>Aritmética de enteros  
 El tipo de datos de resultado de una operación de enteros depende de los tipos de datos de los operandos. En general, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] utiliza las directivas siguientes para determinar el tipo de datos del resultado:  
  
-   Si ambos operandos de un operador binario tienen el mismo tipo de datos, el resultado tiene ese tipo de datos. Una excepción es `Boolean`, que se ve obligado a `Short`.  
  
-   Si un operando sin signo trabaja con un operando con signo, el resultado tiene un tipo con signo con al menos tan grande un intervalo como uno de los operandos.  
  
-   De lo contrario, el resultado normalmente tiene el mayor de los dos tipos de datos de operando.  
  
 Observe que el tipo de datos resultante puede no ser el mismo que cualquier tipo de datos de operando.  
  
> [!NOTE]
>  El tipo de datos de resultado no siempre es lo suficientemente grande como para contener todos los valores posibles resultantes de la operación. Un <xref:System.OverflowException>excepción puede producirse si el valor es demasiado grande para el tipo de datos de resultado.</xref:System.OverflowException>  
  
### <a name="unary--and--operators"></a>Unario + y – operadores  
 En la tabla siguiente muestra el resultado de tipos de datos para los dos operadores unarios, `+` y `–`.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|Unario`+`|Short|SByte|Byte|Short|UShort|Entero|UInteger|Long|ULong|  
|Unario`–`|Short|SByte|Short|Short|Entero|Entero|Long|Long|Decimal|  
  
### <a name="-and--operators"></a><\<y >> operadores  
 En la tabla siguiente muestra el resultado de tipos de datos para los dos operadores de desplazamiento de bits, `<<` y `>>`. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]trata a cada operador de desplazamiento de bits como un operador unario de su operando izquierdo (el modelo de bits que se va a desplazar).  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|Entero|UInteger|Long|ULong|  
  
 Si el operando izquierdo es `Decimal`, `Single`, `Double`, o `String`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] intenta convertirlo a `Long` antes de la operación y el resultado es el tipo de datos `Long`. El operando derecho (el número de posiciones de bits de desplazamiento) debe ser `Integer` o un tipo que se amplía a `Integer`.  
  
### <a name="binary----and-mod-operators"></a>Binarios +, -, * y operadores Mod  
 En la tabla siguiente muestra el resultado de tipos de datos para el archivo binario `+` y `–` operadores y `*` y `Mod` operadores. Tenga en cuenta que esta tabla es simétrica; para una combinación determinada de tipos de datos de operando, el tipo de datos del resultado es el mismo independientemente del orden de los operandos.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Entero|Entero|Long|Long|Decimal|  
|`SByte`|SByte|SByte|Short|Short|Entero|Entero|Long|Long|Decimal|  
|`Byte`|Short|Short|Byte|Short|UShort|Entero|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Entero|Entero|Long|Long|Decimal|  
|`UShort`|Integer|Entero|UShort|Entero|UShort|Entero|UInteger|Long|ULong|  
|`Integer`|Integer|Entero|Entero|Entero|Entero|Entero|Long|Long|Decimal|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Decimal|  
|`ULong`|Decimal|Decimal|ULong|Decimal|ULong|Decimal|ULong|Decimal|ULong|  
  
### <a name="-operator"></a>\ (Operador)  
 En la tabla siguiente muestra el resultado de tipos de datos para el `\` operador. Tenga en cuenta que esta tabla es simétrica; para una combinación determinada de tipos de datos de operando, el tipo de datos del resultado es el mismo independientemente del orden de los operandos.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Entero|Entero|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Entero|Entero|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Entero|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Entero|Entero|Long|Long|Long|  
|`UShort`|Integer|Entero|UShort|Entero|UShort|Entero|UInteger|Long|ULong|  
|`Integer`|Integer|Entero|Entero|Entero|Entero|Entero|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 Si alguno de los operandos de la `\` operador es [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [único](../../../visual-basic/language-reference/data-types/single-data-type.md), o [doble](../../../visual-basic/language-reference/data-types/double-data-type.md), [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] intenta convertirlo a [largo](../../../visual-basic/language-reference/data-types/long-data-type.md) antes de la operación y el resultado es el tipo de datos `Long`.  
  
## <a name="relational-and-bitwise-comparisons"></a>Comparaciones relacionales y bit a bit  
 El tipo de datos de resultado de una operación relacional (`=`, `<>`, `<`, `>`, `<=`, `>=`) es siempre `Boolean` [tipo de datos Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Lo mismo puede decirse de operaciones lógicas (`And`, `AndAlso`, `Not`, `Or`, `OrElse`, `Xor`) en `Boolean` operandos.  
  
 El tipo de datos de resultado de una operación lógica bit a bit depende de los tipos de datos de los operandos. Tenga en cuenta que `AndAlso` y `OrElse` sólo se definen para `Boolean`, y [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] convierte cada operando según sea necesario para `Boolean` antes de realizar la operación.  
  
### <a name="-----and--operators"></a>=, <>, \<, >, \<=, and >= Operators  
 Si ambos operandos son `Boolean`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] considera `True` sea inferior a `False`. Si se compara con un tipo numérico con un `String`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] intenta convertir la `String` a `Double` antes de la operación. Un `Char` o `Date` operando se puede comparar con otro operando del mismo tipo de datos. El tipo de datos resultante es siempre `Boolean`.  
  
### <a name="bitwise-not-operator"></a>Bit a bit no (operador)  
 En la tabla siguiente muestra el resultado de tipos de datos de bit a bit `Not` operador.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Booleano|SByte|Byte|Short|UShort|Entero|UInteger|Long|ULong|  
  
 Si el operando es `Decimal`, `Single`, `Double`, o `String`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] intenta convertirlo a `Long` antes de la operación y el resultado es el tipo de datos `Long`.  
  
### <a name="bitwise-and-or-and-xor-operators"></a>Bit a bit y, o y los operadores de Xor  
 En la tabla siguiente muestra el resultado de tipos de datos de bit a bit `And`, `Or`, y `Xor` operadores. Tenga en cuenta que esta tabla es simétrica; para una combinación determinada de tipos de datos de operando, el tipo de datos del resultado es el mismo independientemente del orden de los operandos.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Booleano|SByte|Short|Short|Entero|Entero|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Entero|Entero|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Entero|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Entero|Entero|Long|Long|Long|  
|`UShort`|Integer|Entero|UShort|Entero|UShort|Entero|UInteger|Long|ULong|  
|`Integer`|Integer|Entero|Entero|Entero|Entero|Entero|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 Si un operando es `Decimal`, `Single`, `Double`, o `String`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] intenta convertirlo a `Long` antes de la operación y los datos de resultado el tipo es el mismo que el del operando ya había sido `Long`.  
  
## <a name="miscellaneous-operators"></a>Operadores varios  
 El `&` operador se define para la concatenación de `String` operandos. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Convierte cada operando según sea necesario para `String` antes de la operación y el resultado siempre es el tipo de datos `String`. Para los fines de la `&` operador, todas las conversiones a `String` se consideran de ampliación, aunque `Option Strict` es `On`.  
  
 El `Is` y `IsNot` operadores requieren que ambos operandos de un tipo de referencia. The `TypeOf`... `Is` expresión requiere que el primer operando de un tipo de referencia y el segundo operando en el nombre de un tipo de datos. En todos estos casos los datos del resultado es de tipo `Boolean`.  
  
 El `Like` operador solo se define para la coincidencia de patrones de `String` operandos. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]intenta convertir cada operando según sea necesario para `String` antes de la operación. El tipo de datos resultante es siempre `Boolean`.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Operadores de comparación en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Operadores](../../../visual-basic/language-reference/operators/index.md)   
 [Precedencia de operadores en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operadores de comparación](../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)
