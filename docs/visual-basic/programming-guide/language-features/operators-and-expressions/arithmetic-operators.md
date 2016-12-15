---
title: "Operadores aritm&#233;ticos en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "operadores aritméticos, acerca de los operadores aritméticos"
  - "operadores de desplazamiento de bits"
  - "operadores bit a bit"
  - "división, entre cero"
  - "operadores [Visual Basic], aritméticos"
  - "operadores [Visual Basic], desplazamiento de bits"
  - "operadores [Visual Basic], bit a bit"
  - "seguridad de tipos"
  - "código de Visual Basic, operadores"
  - "cero, división por cero"
ms.assetid: 325dac7a-ea4f-41d5-8b48-f6e904211569
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Operadores aritm&#233;ticos en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Los operadores aritméticos se utilizan para realizar muchas de las operaciones aritméticas habituales que implican el cálculo de valores numéricos representados por literales, variables, otras expresiones, llamadas a funciones y propiedades, y constantes.  También se clasifican como operadores aritméticos los operadores de desplazamiento de bits, que actúan al nivel de bits individuales de los operandos y cambian sus modelos de bits a la izquierda o la derecha.  
  
## Operaciones aritméticas  
 Puede sumar dos valores en una expresión con el [\+ \(Operador\)](../../../../visual-basic/language-reference/operators/addition-operator.md) o restar un valor de otro con el [\- \(Operador\)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), como se muestra en el siguiente ejemplo.  
  
 [!code-vb[VbVbalrOperators#57](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_1.vb)]  
  
 La negación también utiliza el [\- \(Operador\)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), pero con un solo operando, como se puede ver en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#58](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_2.vb)]  
  
 La multiplicación y la división utilizan los [\* \(Operador\)](../../../../visual-basic/language-reference/operators/multiplication-operator.md) y [\/ \(Operador\)](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md), respectivamente, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#59](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_3.vb)]  
  
 La exponenciación utiliza el [^ \(Operador\)](../../../../visual-basic/language-reference/operators/exponentiation-operator.md), como se puede ver en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#60](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_4.vb)]  
  
 La división de enteros se lleva a cabo con el [\\ \(Operador\)](../../../../visual-basic/language-reference/operators/integer-division-operator.md).  La división de enteros devuelve el cociente, es decir, el número entero que representa el número de veces que puede se puede dividir dividendo entre el divisor sin tener en cuenta el valor del resto.  El divisor y el dividendo deben ser tipos enteros \(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` y `ULong`\) para este operador.  Todos los demás tipos deben convertirse antes a tipos enteros.  El ejemplo siguiente ilustra la división de enteros.  
  
 [!code-vb[VbVbalrOperators#61](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_5.vb)]  
  
 El módulo aritmético se calcula con el [Mod \(Operador\)](../../../../visual-basic/language-reference/operators/mod-operator.md).  Este operador devuelve el resto después de dividir el divisor por el dividendo un número integral de veces.  Si tanto el divisor como el dividendo son tipos enteros, el valor devuelto es entero.  Si el divisor y el dividendo son tipos de punto flotante, el valor devuelto es una variable de punto flotante.  En el siguiente ejemplo se muestra este comportamiento.  
  
 [!code-vb[VbVbalrOperators#62](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_6.vb)]  
  
 [!code-vb[VbVbalrOperators#63](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_7.vb)]  
  
### Intento de dividir por cero  
 La división por cero produce resultados diferentes dependiendo de los tipos de datos que se utilicen.  En divisiones de enteros \(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`\), [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] inicia una excepción <xref:System.DivideByZeroException>.  En operaciones de división del tipo de datos `Decimal` o `Single`, [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] también produce una excepción <xref:System.DivideByZeroException>.  
  
 En las divisiones de punto flotante que impliquen el tipo de datos `Double`, no se produce ninguna excepción y el resultado es el miembro de clase que representa <xref:System.Double.NaN>, <xref:System.Double.PositiveInfinity> o <xref:System.Double.NegativeInfinity>, dependiendo del dividendo.  La siguiente tabla resume los diferentes resultados de intentar dividir un valor `Double` por cero.  
  
|||||  
|-|-|-|-|  
|Tipo de datos del dividendo|Tipo de datos del divisor|Valor del dividendo|Resultado|  
|`Double`|`Double`|0|<xref:System.Double.NaN> \(no es un número definido matemáticamente\)|  
|`Double`|`Double`|\> 0|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity>|  
  
 Cuando se detecta una excepción <xref:System.DivideByZeroException>, puede utilizar los miembros de la excepción para controlarla.  Por ejemplo, la propiedad <xref:System.Exception.Message%2A> contiene el texto del mensaje de la excepción.  Para obtener más información, vea [Try...Catch...Finally \(Instrucción\)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## Operaciones de desplazamiento de bits  
 Una operación de desplazamiento de bits realiza un desplazamiento aritmético sobre un modelo de bits.  El patrón está contenido en el operando de la izquierda, mientras que el operando de la derecha especifica el número de posiciones que debe desplazarse el modelo.  Puede desplazar el modelo a la derecha con [\>\> \(Operador\)](../../../../visual-basic/language-reference/operators/right-shift-operator.md) o a la izquierda con [\<\< \(Operador\)](../../../../visual-basic/language-reference/operators/left-shift-operator.md).  
  
 El tipo de datos del operando del modelo debe ser `SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` o `ULong`.  El tipo de datos del operando de cantidad de desplazamiento debe ser `Integer` o se debe ampliar a `Integer`.  
  
 Los desplazamientos aritméticos no son circulares, lo que significa que los bits desplazados a un extremo del resultado no se vuelven a introducir en el otro extremo.  Las posiciones de bits que quedan vacantes debido a un desplazamiento se establecen de la siguiente manera:  
  
-   0 para un desplazamiento aritmético a la izquierda  
  
-   0 para un desplazamiento aritmético a la derecha de un número positivo  
  
-   0 para un desplazamiento aritmético a la derecha de un tipo de datos sin signo \(`Byte`, `UShort`, `UInteger`, `ULong`\)  
  
-   1 para un desplazamiento aritmético a la derecha de un número negativo \(`SByte`, `Short`, `Integer` o `Long`\)  
  
 El ejemplo siguiente desplaza un valor `Integer` tanto a la izquierda como a la derecha.  
  
 [!code-vb[VbVbalrOperators#64](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_8.vb)]  
  
 Los desplazamientos aritméticos nunca generan excepciones de desbordamiento.  
  
## Operaciones bit a bit  
 Además de ser operadores lógicos, `Not`, `Or`, `And` y `Xor` también realizan operaciones aritméticas bit a bit cuando se utilizan en valores numéricos.  Para obtener más información, vea "Operaciones bit a bit" en [Operadores lógicos y bit a bit en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md).  
  
## Seguridad de tipos  
 Normalmente, los operandos deben ser del mismo tipo.  Por ejemplo, si está realizando sumas con una variable `Integer`, debe sumarla a otra variable `Integer` y asignar el resultado a una variable que también sea del tipo `Integer`.  
  
 Una manera de asegurar unas buenas prácticas de codificación con seguridad de tipos consiste en usar la [Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md).  Si establece `Option Strict On`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] realiza automáticamente las conversiones *con seguridad de tipos*.  Por ejemplo, si intenta agregar una variable `Integer` a una variable `Double` y asignar el valor a una variable de tipo `Double`, la operación se realizará normalmente, porque un valor `Integer` puede convertirse a `Double` sin pérdida de datos.  Por otra parte, las conversiones no seguras de tipos, causan un error del compilador con `Option Strict On`.  Por ejemplo, si intenta agregar una variable `Integer` a una variable `Double` y asignar el valor a la variable `Integer`, se produce un error del compilador, porque una variable `Double` no se puede convertir implícitamente al tipo `Integer`.  
  
 Sin embargo, si establece `Option Strict Off`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] permite que se efectúen conversiones implícitas de restricción, aunque pueden dar como resultado la pérdida inesperada de datos o de precisión.  Por esta razón, es recomendable utilizar `Option Strict On` al escribir el código de producción.  Para obtener más información, vea [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## Vea también  
 [Operadores aritméticos](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operadores de desplazamiento](../../../../visual-basic/language-reference/operators/bit-shift-operators.md)   
 [Operadores de comparación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Operadores de concatenación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)   
 [Operadores lógicos y bit a bit en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)   
 [Combinación eficaz de operadores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)