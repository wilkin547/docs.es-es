---
title: Operadores aritméticos
ms.date: 07/20/2015
helpviewer_keywords:
- type safety
- operators [Visual Basic], bitwise
- operators [Visual Basic], bit-shift
- bitwise operators [Visual Basic]
- bit-shift operators [Visual Basic]
- zero, division by zero
- operators [Visual Basic], arithmetic
- division [Visual Basic], by zero
- Visual Basic code, operators
- arithmetic operators [Visual Basic], about arithmetic operators
ms.assetid: 325dac7a-ea4f-41d5-8b48-f6e904211569
ms.openlocfilehash: d5f79f3e45fc887dcb32c959f04703253ade198c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84389041"
---
# <a name="arithmetic-operators-in-visual-basic"></a>Operadores aritméticos en Visual Basic
Los operadores aritméticos se utilizan para realizar muchas de las operaciones aritméticas conocidas que implican el cálculo de valores numéricos representados por literales, variables, otras expresiones, llamadas a funciones y propiedades, y constantes. También se clasifican con operadores aritméticos los operadores de desplazamiento de bits, que actúan en el nivel de los bits individuales de los operandos y desplazan sus patrones de bits a la izquierda o a la derecha.  
  
## <a name="arithmetic-operations"></a>Operaciones aritméticas  
 Puede agregar dos valores en una expresión junto con el [operador +](../../../language-reference/operators/addition-operator.md)o restar uno de otro con el [operador-(Visual Basic)](../../../language-reference/operators/subtraction-operator.md), como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#57)]  
  
 La negación también utiliza el [operador-(Visual Basic)](../../../language-reference/operators/subtraction-operator.md), pero con un solo operando, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#58)]  
  
 La multiplicación y la división usan el [operador *](../../../language-reference/operators/multiplication-operator.md) y el [operador (Visual Basic)](../../../language-reference/operators/floating-point-division-operator.md), respectivamente, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#59)]  
  
 La exponenciación utiliza el [operador ^](../../../language-reference/operators/exponentiation-operator.md), como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#60)]  
  
 La división de enteros se realiza mediante el [operador \ (Visual Basic)](../../../language-reference/operators/integer-division-operator.md). División de enteros devuelve el cociente, es decir, el entero que representa el número de veces que el divisor puede dividir en el dividendo sin tener en cuenta el resto. Tanto el divisor como el dividendo deben ser tipos enteros ( `SByte` , `Byte` , `Short` , `UShort` , `Integer` , `UInteger` , `Long` y `ULong` ) para este operador. Todos los demás tipos deben convertirse primero a un tipo entero. En el ejemplo siguiente se muestra la división de enteros.  
  
 [!code-vb[VbVbalrOperators#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#61)]  
  
 El módulo aritmético se realiza mediante el [operador mod](../../../language-reference/operators/mod-operator.md). Este operador devuelve el resto después de dividir el divisor en el dividendo un número entero de veces. Si el divisor y el dividendo son tipos enteros, el valor devuelto es integral. Si el divisor y el dividendo son tipos de punto flotante, el valor devuelto también es de punto flotante. El siguiente ejemplo demuestra este comportamiento.  
  
 [!code-vb[VbVbalrOperators#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbalrOperators#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#63)]  
  
### <a name="attempted-division-by-zero"></a>División intentada por cero  
 La división por cero tiene resultados diferentes en función de los tipos de datos implicados. En las divisiones enteras ( `SByte` , `Byte` , `Short` , `UShort` , `Integer` , `UInteger` , `Long` , `ULong` ), el .NET Framework produce una <xref:System.DivideByZeroException> excepción. En las operaciones de división en el `Decimal` `Single` tipo de datos o, el .NET Framework también produce una <xref:System.DivideByZeroException> excepción.  
  
 En las divisiones de punto flotante que implican el `Double` tipo de datos, no se produce ninguna excepción y el resultado es el miembro de clase que representa <xref:System.Double.NaN> , <xref:System.Double.PositiveInfinity> o <xref:System.Double.NegativeInfinity> , en función del dividendo. En la tabla siguiente se resumen los distintos resultados de intentar dividir un `Double` valor por cero.  
  
|Tipo de datos de dividendo|Divisor, tipo de datos|Valor del dividendo|Resultado|  
|---|---|---|---|  
|`Double`|`Double`|0|<xref:System.Double.NaN>(no es un número definido matemáticamente)|  
|`Double`|`Double`|> 0|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity>|  
  
 Al detectar una <xref:System.DivideByZeroException> excepción, puede utilizar sus miembros para ayudarle a controlarla. Por ejemplo, la <xref:System.Exception.Message%2A> propiedad contiene el texto del mensaje para la excepción. Para obtener más información, vea [Instrucción Try...Catch...Finally (Visual Basic)](../../../language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="bit-shift-operations"></a>Operaciones de desplazamiento de bits  
 Una operación de desplazamiento de bits realiza un cambio aritmético en un patrón de bits. El patrón se encuentra en el operando de la izquierda, mientras que el operando de la derecha especifica el número de posiciones para desplazar el patrón. Puede desplazar el patrón a la derecha con el [operador>> ](../../../language-reference/operators/right-shift-operator.md) o a la izquierda con el [operador<< ](../../../language-reference/operators/left-shift-operator.md).  
  
 El tipo de datos del operando de patrón debe ser `SByte` , `Byte` , `Short` , `UShort` , `Integer` , `UInteger` , `Long` o `ULong` . El tipo de datos del operando de la cantidad de desplazamiento debe ser `Integer` o debe ampliarse a `Integer` .  
  
 Los turnos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se reintroducen en el otro extremo. Las posiciones de bits que quedan vacantes con un turno se establecen de la siguiente manera:  
  
- 0 para un desplazamiento aritmético a la izquierda  
  
- 0 para un desplazamiento aritmético a la derecha de un número positivo  
  
- 0 para un desplazamiento aritmético a la derecha de un tipo de datos sin signo ( `Byte` , `UShort` , `UInteger` , `ULong` )  
  
- 1 para un desplazamiento aritmético a la derecha de un número negativo ( `SByte` , `Short` , `Integer` o `Long` )  
  
 En el ejemplo siguiente se desplaza un `Integer` valor a la izquierda y a la derecha.  
  
 [!code-vb[VbVbalrOperators#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#64)]  
  
 Los desplazamientos aritméticos nunca generan excepciones de desbordamiento.  
  
## <a name="bitwise-operations"></a>Operaciones bit a bit  
 Además de ser operadores lógicos, `Not` , `Or` , `And` y `Xor` también realizan operaciones aritméticas bit a bit cuando se usan en valores numéricos. Para obtener más información, vea "operaciones bit a bit" en [operadores lógicos y bit a bit en Visual Basic](logical-and-bitwise-operators.md).  
  
## <a name="type-safety"></a>Seguridad de tipos  
 Normalmente, los operandos deben ser del mismo tipo. Por ejemplo, si está realizando sumas con una `Integer` variable, debe agregarla a otra `Integer` variable y debe asignar el resultado a una variable de tipo `Integer` también.  
  
 Una manera de garantizar una buena práctica de codificación con seguridad de tipos es usar la [instrucción Option Strict](../../../language-reference/statements/option-strict-statement.md). Si establece `Option Strict On` , Visual Basic realiza automáticamente las conversiones *con seguridad de tipos* . Por ejemplo, si intenta agregar una `Integer` variable a una `Double` variable y asignar el valor a una `Double` variable, la operación continúa normalmente, porque un `Integer` valor se puede convertir en `Double` sin pérdida de datos. Las conversiones no seguras, por otro lado, producen un error del compilador con `Option Strict On` . Por ejemplo, si intenta agregar una `Integer` variable a una `Double` variable y asignar el valor a una `Integer` variable, se produce un error del compilador, porque una `Double` variable no se puede convertir implícitamente al tipo `Integer` .  
  
 Sin embargo, si establece `Option Strict Off` Visual Basic permite que se lleven a cabo conversiones de restricción implícitas, aunque pueden provocar la pérdida inesperada de datos o precisión. Por esta razón, se recomienda usar `Option Strict On` al escribir código de producción. Para obtener más información, consulta [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md).  
  
## <a name="see-also"></a>Consulte también

- [Operadores aritméticos](../../../language-reference/operators/arithmetic-operators.md)
- [Operadores de desplazamiento de bits](../../../language-reference/operators/bit-shift-operators.md)
- [Comparison Operators in Visual Basic](comparison-operators.md)
- [Operadores de concatenación en Visual Basic](concatenation-operators.md)
- [Operadores lógicos y bit a bit en Visual Basic](logical-and-bitwise-operators.md)
- [Combinación eficaz de operadores](efficient-combination-of-operators.md)
