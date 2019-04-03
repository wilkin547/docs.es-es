---
title: Operadores aritméticos en Visual Basic
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
ms.openlocfilehash: 635c791f81107a1800e2ef381f6bea78cbc18e18
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58820781"
---
# <a name="arithmetic-operators-in-visual-basic"></a>Operadores aritméticos en Visual Basic
Operadores aritméticos se usan para realizar muchas de las operaciones aritméticas habituales que implican el cálculo de valores numéricos representados por literales, variables, otras expresiones, función y las llamadas de propiedad y constantes. También se clasifican los operadores aritméticos son los operadores de desplazamiento de bits, que actúan en el nivel de los bits individuales de los operandos- and -shift sus patrones de bits hacia la izquierda o derecha.  
  
## <a name="arithmetic-operations"></a>Operaciones aritméticas  
 Puede agregar dos valores en una expresión junto con el [+ (operador)](../../../../visual-basic/language-reference/operators/addition-operator.md), o restar uno a otro con el [-(operador) (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), tal y como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#57)]  
  
 Negación también utiliza el [-(operador) (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), pero con un solo operando, como en el ejemplo siguiente se muestra.  
  
 [!code-vb[VbVbalrOperators#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#58)]  
  
 Uso de multiplicación y división el [* operador](../../../../visual-basic/language-reference/operators/multiplication-operator.md) y [/ (operador) (Visual Basic)](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md), respectivamente, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#59)]  
  
 Exponenciación utiliza el [^ Operator](../../../../visual-basic/language-reference/operators/exponentiation-operator.md), tal y como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#60)]  
  
 División de enteros se lleva a cabo utilizando la [\ (operador) (Visual Basic)](../../../../visual-basic/language-reference/operators/integer-division-operator.md). División de enteros devuelve el cociente, es decir, el entero que representa el número de veces que el divisor puede dividir el dividendo sin tener en cuenta cualquier resto. El divisor como el dividendo deben ser de tipos enteros (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, y `ULong`) para este operador. En primer lugar todos los demás tipos deben convertirse a un tipo entero. El ejemplo siguiente muestra la división de enteros.  
  
 [!code-vb[VbVbalrOperators#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#61)]  
  
 MODULUS aritmético se realiza mediante el [Mod (operador)](../../../../visual-basic/language-reference/operators/mod-operator.md). Este operador devuelve el resto después de dividir el divisor por el dividendo un número entero de veces. Si el divisor y el dividendo son tipos enteros, el valor devuelto es de tipo integral. Si el divisor y el dividendo son tipos de punto flotante, el valor devuelto también es un punto flotante. El ejemplo siguiente muestra este comportamiento.  
  
 [!code-vb[VbVbalrOperators#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbalrOperators#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#63)]  
  
### <a name="attempted-division-by-zero"></a>División por cero intentada  
 División por cero produce resultados diferentes en función de los tipos de datos implicados. En divisiones de enteros (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`), el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] produce una <xref:System.DivideByZeroException> excepción. En operaciones de división en el `Decimal` o `Single` tipo de datos, el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] también produce un <xref:System.DivideByZeroException> excepción.  
  
 En las divisiones de punto flotante que implica la `Double` tipo de datos, se produce ninguna excepción y el resultado es el miembro de clase que representa <xref:System.Double.NaN>, <xref:System.Double.PositiveInfinity>, o <xref:System.Double.NegativeInfinity>, según el dividendo. En la tabla siguiente resume los diferentes resultados de intentar dividir un `Double` valor por cero.  
  
|Tipo de datos del dividendo|Tipo de datos del divisor|Valor del dividendo|Resultado|  
|---|---|---|---|  
|`Double`|`Double`|0|<xref:System.Double.NaN> (no un número definido matemáticamente)|  
|`Double`|`Double`|> 0|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity>|  
  
 Cuando se detecta un <xref:System.DivideByZeroException> excepción, puede utilizar sus miembros para ayudar a controlarlo. Por ejemplo, el <xref:System.Exception.Message%2A> propiedad contiene el texto del mensaje para la excepción. Para obtener más información, vea [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally [Instrucción, Visual Basic]).  
  
## <a name="bit-shift-operations"></a>Operaciones de desplazamiento de bits  
 Una operación de desplazamiento de bits realiza un desplazamiento aritmético en un patrón de bits. El patrón está contenido en el operando de la izquierda, mientras que el operando de la derecha especifica el número de posiciones que va a desplazar el modelo. Puede desplazar el modelo a la derecha con el [>> operador](../../../../visual-basic/language-reference/operators/right-shift-operator.md) o a la izquierda con el [<< operador](../../../../visual-basic/language-reference/operators/left-shift-operator.md).  
  
 El tipo de datos del operando del modelo debe ser `SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`. El tipo de datos del operando de cantidad de desplazamiento debe ser `Integer` o debe ampliarse a `Integer`.  
  
 Los desplazamientos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se vuelve a insertar en el otro extremo. Las posiciones de bits que quedan vacantes debidas a un cambio se establecen como sigue:  
  
-   0 para un desplazamiento aritmético a la izquierda  
  
-   0 para un desplazamiento aritmético a la derecha de un número positivo  
  
-   0 para un desplazamiento aritmético a la derecha de un tipo de datos sin signo (`Byte`, `UShort`, `UInteger`, `ULong`)  
  
-   1 para un desplazamiento aritmético a la derecha de un número negativo (`SByte`, `Short`, `Integer`, o `Long`)  
  
 El siguiente ejemplo se desplaza una `Integer` valor left y right.  
  
 [!code-vb[VbVbalrOperators#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#64)]  
  
 Los desplazamientos aritméticos nunca generan excepciones de desbordamiento.  
  
## <a name="bitwise-operations"></a>Operaciones bit a bit  
 Además de los operadores lógicos, `Not`, `Or`, `And`, y `Xor` también realizan operaciones aritméticas bit a bit cuando se usa en valores numéricos. Para obtener más información, vea "Operaciones bit a bit" en [operadores lógicos y bit a bit en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md).  
  
## <a name="type-safety"></a>Seguridad de tipos  
 Operandos normalmente deben ser del mismo tipo. Por ejemplo, si está realizando la inclusión de un `Integer` variable, debe agregarlo a otro `Integer` variable y se debe asignar el resultado a una variable de tipo `Integer` también.  
  
 Una forma de garantizar la seguridad de tipos de buena práctica de codificación es usar el [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md). Si establece `Option Strict On`, Visual Basic realiza automáticamente *con seguridad de tipos* conversiones. Por ejemplo, si se intenta agregar un `Integer` variable a un `Double` variable y asigne el valor a un `Double` variable, la operación continúa con normalidad, porque un `Integer` valor puede convertirse en `Double` sin pérdida de datos. Las conversiones de tipos, por otro lado, provocar un error del compilador con `Option Strict On`. Por ejemplo, si se intenta agregar un `Integer` variable a un `Double` variable y asigne el valor a un `Integer` variable, un error del compilador da como resultado, porque un `Double` variable no se puede convertir implícitamente al tipo `Integer`.  
  
 Si establece `Option Strict Off`, sin embargo, Visual Basic permite conversiones de restricción implícitas que tenga lugar, aunque puede dar como resultado la pérdida de datos o de precisión. Por este motivo, recomendamos que use `Option Strict On` al escribir código de producción. Para obtener más información, consulta [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="see-also"></a>Vea también

- [Operadores aritméticos](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operadores de desplazamiento de bits](../../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Operadores de comparación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operadores de concatenación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Operadores lógicos y bit a bit en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Combinación eficaz de operadores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
