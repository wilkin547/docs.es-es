---
title: "Operadores l&#243;gicos y bit a bit en Visual Basic | Microsoft Docs"
ms.custom: ""
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
  - "And (operador) [Visual Basic], operadores lógicos"
  - "AndAlso (operador)"
  - "expresiones booleanas"
  - "expresiones [Visual Basic], booleanas"
  - "operadores lógicos"
  - "operadores lógicos, binaria"
  - "operadores lógicos, expresiones booleanas"
  - "operadores lógicos, cortocircuitar"
  - "operadores lógicos, unarios"
  - "Not (operador) [Visual Basic], expresiones booleanas"
  - "operadores [Visual Basic], lógico"
  - "Or (operador), operadores lógicos"
  - "OrElse (operador) [Visual Basic]"
  - "cortocircuitar"
  - "cortocircuitar, operadores lógicos"
  - "código de Visual Basic, expresiones"
  - "código de Visual Basic, operadores"
  - "Xor (operador) [Visual Basic], expresiones booleanas"
ms.assetid: ca474e13-567d-4b1d-a18b-301433705e57
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Operadores l&#243;gicos y bit a bit en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Los operadores lógicos comparan expresiones `Boolean` y devuelven un resultado `Boolean`.  Los operadores `And`, `Or`, `AndAlso`, `OrElse` y `Xor` son *binarios* porque toman dos operandos, mientras que el operador `Not` es *unario* porque toma un solo operando.  Algunos de estos operadores también pueden realizar operaciones lógicas bit a bit en valores enteros.  
  
## Operador lógico unario  
 El [Not \(Operador\)](../../../../visual-basic/language-reference/operators/not-operator.md) realiza la *negación* lógica en una expresión `Boolean`.  Produce el contrario lógico de su operando.  Si la expresión se evalúa como `True`, `Not` devuelve `False`; si la expresión se evalúa como `False`, `Not` devuelve `True`.  Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrOperators#77](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/logical-and-bitwise-oper_1.vb)]  
  
## Operadores lógicos binarios  
 El [And \(Operador\)](../../../../visual-basic/language-reference/operators/and-operator.md) realiza la *conjunción* lógica de dos expresiones `Boolean`.  Si ambas expresiones se evalúan como `True`, `And` devuelve `True`.  Si al menos una de las expresiones se evalúa como `False`, `And` devuelve `False`.  
  
 El [Or \(Operador\)](../../../../visual-basic/language-reference/operators/or-operator.md) realiza la *disyunción* o *inclusión* lógicas de dos expresiones `Boolean`.  Si una de las expresiones o ambas se evalúan como `True`, `Or` devuelve `True`.  Si ninguna de las expresiones se evalúa como `True`, `Or` devuelve `False`.  
  
 [Xor \(Operador\)](../../../../visual-basic/language-reference/operators/xor-operator.md) realiza la *exclusión* lógica de dos expresiones `Boolean`.  Si exactamente una expresión, pero no ambas, se evalúa como `True`, `Xor` devuelve `True`.  Si ambas expresiones se evalúan como `True` o como `False`, `Xor` devuelve `False`.  
  
 En el siguiente ejemplo se muestra cómo utilizar los operadores `And`, `Or` y `Xor`.  
  
 [!code-vb[VbVbalrOperators#78](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/logical-and-bitwise-oper_2.vb)]  
  
## Cortocircuitar las operaciones lógicas  
 El [AndAlso \(Operador\)](../../../../visual-basic/language-reference/operators/andalso-operator.md) es muy similar al operador `And`, ya que también realiza la conjunción lógica de dos expresiones `Boolean`.  La diferencia clave entre ambos es que `AndAlso` presenta un comportamiento de evaluación "*cortocircuitada*".  Si la primera parte de una expresión `AndAlso` se evalúa como `False`, la segunda parte de la expresión no se evalúa porque no puede modificar el resultado final y `AndAlso` devuelve `False`.  
  
 De igual forma, el [OrElse \(Operador\)](../../../../visual-basic/language-reference/operators/orelse-operator.md) realiza la disyunción lógica de evaluación cortocircuitada de dos expresiones `Boolean`.  Si la primera parte de una expresión `OrElse` se evalúa como `True`, la segunda parte de la expresión no se evalúa porque no puede modificar el resultado final y `OrElse` devuelve `True`.  
  
### Inconvenientes de las evaluaciones cortocircuitadas  
 Cortocircuitar puede mejorar el rendimiento ya que no se evalúa una expresión que no puede modificar el resultado de la operación lógica.  Sin embargo, si esa expresión realiza acciones adicionales, al cortocircuitar se pasan por alto esas acciones.  Por ejemplo, si la expresión incluye una llamada a un procedimiento `Function`, no se llama a ese procedimiento si la expresión se cortocircuita y el código adicional incluido en `Function` no se ejecuta.  Por consiguiente, la función únicamente se puede ejecutar de vez en cuando y no se puede probar correctamente.  También, la lógica del programa puede depender del código en la `Function`.  
  
 En el ejemplo siguiente se muestra la diferencia entre `And`, `Or` y sus homólogos de evaluación cortocircuitada.  
  
 [!code-vb[VbVbalrOperators#81](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/logical-and-bitwise-oper_3.vb)]  
  
 [!code-vb[VbVbalrOperators#80](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/logical-and-bitwise-oper_4.vb)]  
  
 [!code-vb[VbVbalrOperators#79](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/logical-and-bitwise-oper_5.vb)]  
  
 En el ejemplo anterior, observe que una parte de código importante dentro de `checkIfValid()` no se ejecuta cuando se cortocircuita la llamada.  La primera instrucción `If` llama a `checkIfValid()` aunque `12 > 45` devuelve `False`, porque `And` no cortocircuita.  La segunda instrucción `If` no llama a `checkIfValid()`, porque cuando `12 > 45` devuelve `False`, `AndAlso` cortocircuita la segunda expresión.  La tercera instrucción `If` llama a `checkIfValid()` aunque `12 < 45` devuelve `True`, porque `Or` no cortocircuita.  La cuarta instrucción `If` no llama a `checkIfValid()`, porque cuando `12 < 45` devuelve `True`, `OrElse` cortocircuita la segunda expresión.  
  
## Operaciones bit a bit  
 Las operaciones bit a bit evalúan dos valores enteros en formato binario \(base 2\).  Comparan los bits en las posiciones correspondientes y, a continuación, asignan valores basados en la comparación.  En el siguiente ejemplo se muestra cómo se utiliza el operador `And`.  
  
 [!code-vb[VbVbalrConcepts#2](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/visualbasic/logical-and-bitwise-oper_6.vb)]  
  
 En el ejemplo anterior se establece el valor de `x` en 1.  Esto pasa por las siguientes razones:  
  
-   Los valores se tratan como binarios:  
  
     3 en formato binario \= 011  
  
     5 en formato binario \= 101  
  
-   El operador `And` compara las representaciones binarias, una posición binaria \(bit\) a la vez.  Si los dos bits en una posición dada son 1, entonces se coloca un 1 en esa posición del resultado.  Si uno de los dos bits es 0, entonces se coloca un 0 en esa posición del resultado.  En el ejemplo anterior, esto funciona como sigue:  
  
     011 \(3 en formato binario\)  
  
     101 \(5 en formato binario\)  
  
     001 \(el resultado, en formato binario\)  
  
-   El resultado se trata como decimal.  El valor 001 es la representación binaria de 1, por lo que `x` \= 1.  
  
 La operación `Or` bit a bit es similar, excepto en que se asigna 1 al bit resultante si cualquiera de los bits comparados es 1.  `Xor` asigna 1 al bit del resultado si exclusivamente uno de los bits comparados \(no ambos\) es 1.  `Not` toma un solo operando e invierte todos los bits, incluido el bit de signo, y asigna ese valor al resultado.  Esto significa que para números positivos sin signo, `Not` siempre devuelve un valor negativo y, para números negativos, `Not` siempre devuelve un valor positivo o cero.  
  
 Los operadores `AndAlso` y `OrElse` no admiten las operaciones bit a bit.  
  
> [!NOTE]
>  Las operaciones bit a bit sólo se pueden realizar en tipos enteros.  Los valores de punto flotante deben convertirse a tipos enteros para que la operación bit a bit pueda proseguir.  
  
## Vea también  
 [Operadores lógicos y operadores bit a bit](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Expresiones booleanas](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)   
 [Operadores aritméticos en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Operadores de comparación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Operadores de concatenación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)   
 [Combinación eficaz de operadores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)