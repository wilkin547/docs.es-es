---
title: "Expresiones booleanas (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "expresiones booleanas"
  - "evaluación de expresiones, expresiones booleanas"
  - "expresiones [Visual Basic], booleanas"
  - "operadores lógicos, expresiones booleanas"
  - "operadores lógicos, cortocircuitar"
  - "operadores [Visual Basic], booleanos"
  - "operadores [Visual Basic], cortocircuitar"
  - "evaluación cortocircuitada"
  - "cortocircuitar"
  - "código de Visual Basic, expresiones"
  - "código de Visual Basic, operadores"
ms.assetid: d3d90406-55c8-4404-8143-50fd7f0d0d1a
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Expresiones booleanas (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Una *expresión booleana* es una expresión que se evalúa como un valor del [tipo de datos Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md): `True` o `False`.  Las expresiones `Boolean` pueden ser de varias formas.  La más simple es la comparación directa del valor de una variable `Boolean` con un literal `Boolean`, como se muestra en el ejemplo siguiente:  
  
 [!code-vb[VbVbalrOperators#87](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_1.vb)]  
  
## Dos significados del operador \=  
 Tenga en cuenta que la instrucción de asignación `newCustomer = True` tiene la misma apariencia que la expresión del ejemplo anterior, pero realiza funciones diferentes y se utiliza de forma distinta.  En el ejemplo anterior, la expresión `newCustomer = True` representa un valor booleano y el signo `=` se interpreta como un operador de comparación.  En una instrucción independiente, el signo `=` se interpretaría como operador de asignación y asignaría el valor de la derecha a la variable de la izquierda.  Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrOperators#88](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_2.vb)]  
  
 Para obtener más información, vea [Comparaciones de valores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) e [Instrucciones](../../../../visual-basic/language-reference/statements/index.md).  
  
## Operadores de comparación  
 Los operadores de comparación como `=`, `<`, `>`, `<>`, `<=` y `>=` producen expresiones booleanas, comparan la expresión situada a la izquierda del operador con la situada a la derecha y evalúan el resultado como `True` o `False`.  Esto se ilustra en el siguiente ejemplo:  
  
 `42 < 81`  
  
 Dado que 42 es menor que 81, la expresión booleana del ejemplo anterior se evalúa como `True`.  Para obtener más información sobre este tipo de expresión, vea [Comparaciones de valores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md).  
  
### Operadores de comparación combinados con operadores lógicos  
 Las expresiones de comparación se pueden combinar con operadores lógicos para producir expresiones booleanas más complejas.  En el ejemplo siguiente se muestra el uso de operadores de comparación junto con un operador lógico.  
  
 `x > y And x < 1000`  
  
 En el ejemplo anterior, el valor de toda la expresión depende de los valores de las expresiones especificadas a cada lado del operador `And`.  Si las dos expresiones son `True`, toda la expresión se evalúa como `True`.  Si una de las expresiones es `False`, toda la expresión se evalúa como `False`.  
  
## Operadores de evaluación "cortocircuitada"  
 Los operadores lógicos `AndAlso` y `OrElse` exhiben un comportamiento conocido como evaluación *cortocircuitada*.  Un operador de evaluación cortocircuitada evalúa primero el operando de la izquierda.  Si el operando de la izquierda determina el valor de la expresión completa, la ejecución del programa continúa sin evaluar la expresión de la derecha.  Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrOperators#89](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_3.vb)]  
  
 En el ejemplo anterior, el operador evalúa la expresión de la izquierda, `45 < 12`.  Dado que la expresión de la izquierda se evalúa como `False`, la expresión lógica completa se debe evaluar como `False`.  Por tanto el programa pasa por alto la ejecución del código del bloque `If` sin evaluar la expresión de la derecha, `testFunction(3)`.  Este ejemplo no llama a `testFunction()` porque la expresión de la izquierda hace que toda la expresión se evalúe como False.  
  
 De forma similar, si la expresión de la izquierda en una expresión lógica que utiliza `OrElse` se evalúa como `True`, la ejecución prosigue con la siguiente línea de código sin evaluar la expresión de la derecha, puesto que la expresión de la izquierda ya ha validado toda la expresión.  
  
### Comparación con operadores que no cortocircuitan  
 Por el contrario, cuando se utilizan los operadores lógicos `And` y `Or`, se evalúan los dos lados de la expresión.  Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrOperators#90](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_4.vb)]  
  
 El ejemplo anterior llama a `testFunction()` aunque la expresión de la izquierda se evalúe como `False`.  
  
## Expresiones entre paréntesis  
 Pueden utilizarse paréntesis para controlar la evaluación de expresiones booleanas.  Las expresiones entre paréntesis se evalúan primero.  En el caso de múltiples niveles de anidamiento, se garantiza la prioridad de las expresiones anidadas a mayor profundidad.  Dentro de los paréntesis, la evaluación se lleva a cabo según las reglas de prioridad de operador.  Para obtener más información, vea [Prioridad de operador en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## Vea también  
 [Operadores lógicos y bit a bit en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)   
 [Comparaciones de valores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Instrucciones](../../../../visual-basic/programming-guide/language-features/statements.md)   
 [Operadores de comparación](../../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Combinación eficaz de operadores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)   
 [Prioridad de operador en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Boolean \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)