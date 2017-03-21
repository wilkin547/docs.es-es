---
title: "Operadores aritméticos en Visual Basic | Documentos de Microsoft"
ms.custom: 
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
- type safety
- operators [Visual Basic], bitwise
- operators [Visual Basic], bit-shift
- bitwise operators
- bit-shift operators
- zero, division by zero
- operators [Visual Basic], arithmetic
- division, by zero
- Visual Basic code, operators
- arithmetic operators, about arithmetic operators
ms.assetid: 325dac7a-ea4f-41d5-8b48-f6e904211569
caps.latest.revision: 20
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: c724bf8b6794e71d49b32c7d3ce9e010f541f68f
ms.lasthandoff: 03/13/2017

---
# <a name="arithmetic-operators-in-visual-basic"></a>Operadores aritméticos en Visual Basic
Operadores aritméticos se utilizan para realizar muchas de las operaciones aritméticas habituales que implican el cálculo de valores numéricos representados por literales, variables, otras expresiones, función y llamadas de propiedad y constantes. También se clasifican los operadores aritméticos son los operadores de desplazamiento de bits, que actúan en el nivel de los bits individuales de los operandos y los patrones de bits de desplazamiento a la izquierda o derecha.  
  
## <a name="arithmetic-operations"></a>Operaciones aritméticas  
 Puede sumar dos valores en una expresión con la [+ (operador)](../../../../visual-basic/language-reference/operators/addition-operator.md), o restar un valor de otro con el [-(operador, Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators&#57;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_1.vb)]  
  
 Negación también utiliza el [-(operador, Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), pero con un solo operando, como en el ejemplo siguiente se muestra.  
  
 [!code-vb[VbVbalrOperators&#58;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_2.vb)]  
  
 Multiplicación y división utilizan el [* (operador)](../../../../visual-basic/language-reference/operators/multiplication-operator.md) y [/ (operador, Visual Basic)](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md), respectivamente, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators&#59;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_3.vb)]  
  
 Exponenciación utiliza el [^ (operador)](../../../../visual-basic/language-reference/operators/exponentiation-operator.md), como se muestra en el ejemplo siguiente.  
  
 [!code-vb[60 VbVbalrOperators](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_4.vb)]  
  
 División de enteros se lleva a cabo utilizando la [\ (operador, Visual Basic)](../../../../visual-basic/language-reference/operators/integer-division-operator.md). División de enteros devuelve el cociente, es decir, el entero que representa el número de veces que el divisor puede dividir el dividendo sin tener en cuenta cualquier resto. El divisor y el dividendo deben ser tipos integrales (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, y `ULong`) para este operador. Todos los demás tipos se deben convertir primero a un tipo entero. En el ejemplo siguiente se muestra la división de enteros.  
  
 [!code-vb[VbVbalrOperators&#61;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_5.vb)]  
  
 El módulo aritmético se realiza mediante el [Mod (operador)](../../../../visual-basic/language-reference/operators/mod-operator.md). Este operador devuelve el resto después de dividir el divisor por el dividendo un número integral de veces. Si el divisor y el dividendo son tipos enteros, el valor devuelto es integral. Si el divisor y el dividendo son tipos de punto flotante, el valor devuelto también es de punto flotante. En el ejemplo siguiente se muestra este comportamiento.  
  
 [!code-vb[VbVbalrOperators&#62;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_6.vb)]  
  
 [!code-vb[VbVbalrOperators&#63;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_7.vb)]  
  
### <a name="attempted-division-by-zero"></a>División por cero intentada  
 División por cero produce resultados diferentes en función de los tipos de datos implicados. In integral divisions (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`), the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] throws a <xref:System.DivideByZeroException> exception.</xref:System.DivideByZeroException> En operaciones de división de la `Decimal` o `Single` tipo de datos, el [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] también produce un <xref:System.DivideByZeroException>excepción.</xref:System.DivideByZeroException>  
  
 En divisiones de punto flotante que implican la `Double` tipo de datos, se inicia ninguna excepción y el resultado es el miembro de clase que representa <xref:System.Double.NaN>, <xref:System.Double.PositiveInfinity>, o <xref:System.Double.NegativeInfinity>, dependiendo del dividendo.</xref:System.Double.NegativeInfinity> </xref:System.Double.PositiveInfinity> </xref:System.Double.NaN> La siguiente tabla resume los diferentes resultados de intentar dividir un `Double` valor por cero.  
  
|Tipo de datos del dividendo|Tipo de datos del divisor|Valor del dividendo|Resultado|  
|---|---|---|---|  
|`Double`|`Double`|0|<xref:System.Double.NaN>(no un número definido matemáticamente)</xref:System.Double.NaN>|  
|`Double`|`Double`|> 0|<xref:System.Double.PositiveInfinity></xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity></xref:System.Double.NegativeInfinity>|  
  
 Cuando se detecta una <xref:System.DivideByZeroException>que excepción, puede utilizar sus miembros para ayudarle a controlar lo</xref:System.DivideByZeroException> Por ejemplo, el <xref:System.Exception.Message%2A>propiedad contiene el texto del mensaje para la excepción.</xref:System.Exception.Message%2A> Para obtener más información, consulte [intente... Catch... Finally (instrucción)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="bit-shift-operations"></a>Operaciones de desplazamiento de bits  
 Una operación de desplazamiento de bits realiza un desplazamiento aritmético en un patrón de bits. El patrón está contenido en el operando de la izquierda, mientras que el operando de la derecha especifica el número de posiciones que desea desplazar el modelo. Puede desplazar el modelo a la derecha con el [>> operador](../../../../visual-basic/language-reference/operators/right-shift-operator.md) o a la izquierda con el [ <> </> ](../../../../visual-basic/language-reference/operators/left-shift-operator.md).  
  
 El tipo de datos del operando del modelo debe ser `SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`. El tipo de datos del operando de cantidad de desplazamiento debe ser `Integer` o se debe ampliar a `Integer`.  
  
 Los desplazamientos aritméticos no son circulares, lo que significa que los bits desplazados a un extremo del resultado no vuelven a introducirse en el otro extremo. Las posiciones de bits que quedan vacantes debidas a un desplazamiento se establecen como sigue:  
  
-   0 para un desplazamiento aritmético a la izquierda  
  
-   0 para un desplazamiento aritmético a la derecha de un número positivo  
  
-   0 para un desplazamiento aritmético a la derecha de un tipo de datos sin signo (`Byte`, `UShort`, `UInteger`, `ULong`)  
  
-   1 para un desplazamiento aritmético a la derecha de un número negativo (`SByte`, `Short`, `Integer`, o `Long`)  
  
 El siguiente ejemplo se desplaza un `Integer` valor izquierdo y derecho.  
  
 [!code-vb[VbVbalrOperators&#64;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_8.vb)]  
  
 Los desplazamientos aritméticos nunca generan excepciones de desbordamiento.  
  
## <a name="bitwise-operations"></a>Operaciones bit a bit  
 Además de ser operadores lógicos, `Not`, `Or`, `And`, y `Xor` también realizan operaciones aritméticas bit a bit cuando se utilizan en valores numéricos. Para obtener más información, vea "Operaciones bit a bit" en [operadores lógicos y bit a bit en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md).  
  
## <a name="type-safety"></a>Seguridad de tipos  
 Normalmente, operandos deben ser del mismo tipo. Por ejemplo, si está realizando sumas con una `Integer` variable, debe agregarla a otra `Integer` variable y se debe asignar el resultado a una variable de tipo `Integer` también.  
  
 Una manera de garantizar el buen con seguridad de tipos de codificación recomendado es usar el [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md). Si establece `Option Strict On`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] realiza automáticamente *con seguridad de tipos* conversiones. Por ejemplo, si intenta agregar una `Integer` variable a un `Double` variable y asigna el valor a un `Double` variable, la operación continúa normalmente, porque un `Integer` valor se puede convertir en `Double` sin pérdida de datos. Las conversiones de tipos insegura, por otro lado, producen un error del compilador con `Option Strict On`. Por ejemplo, si intenta agregar una `Integer` variable a un `Double` variable y asigna el valor a un `Integer` variable, compilador produce un error, porque un `Double` variable no se puede convertir implícitamente al tipo `Integer`.  
  
 Si establece `Option Strict Off`, sin embargo, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] permite conversiones de restricción implícitas que tenga lugar, aunque puede dar como resultado la pérdida de datos o de precisión. Por este motivo, se recomienda que use `Option Strict On` al escribir código de producción. Para obtener más información, consulte [conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="see-also"></a>Vea también  
 [Operadores aritméticos](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operadores de desplazamiento](../../../../visual-basic/language-reference/operators/bit-shift-operators.md)   
 [Operadores de comparación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Operadores de concatenación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)   
 [Operadores lógicos y bit a bit en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)   
 [Combinación eficaz de operadores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
