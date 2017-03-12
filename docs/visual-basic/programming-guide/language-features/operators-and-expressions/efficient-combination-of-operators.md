---
title: "Combinaci&#243;n eficaz de operadores (Visual Basic) | Microsoft Docs"
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
  - "expresiones [Visual Basic], complejo"
  - "expresiones [Visual Basic], operadores"
  - "expresiones [Visual Basic], paréntesis"
  - "expresiones numéricas"
  - "operadores [Visual Basic], asociatividad"
  - "operadores [Visual Basic], expresiones complejas"
  - "operadores [Visual Basic], prioridad"
  - "paréntesis, expresiones complejas"
  - "código de Visual Basic, expresiones"
  - "código de Visual Basic, operadores"
ms.assetid: bd22340e-b5be-458b-8772-3916c02309a4
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Combinaci&#243;n eficaz de operadores (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Las expresiones complejas pueden contener muchos operadores diferentes.  Esto se ilustra en el siguiente ejemplo:  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 La creación de expresiones complejas como la del ejemplo anterior requiere comprender a fondo las reglas de prioridad de operador.  Para obtener más información, vea [Prioridad de operador en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## Expresiones entre paréntesis  
 A menudo, desea que las operaciones se realicen en un orden diferente del que determina la prioridad de operador.  Considere el ejemplo siguiente.  
  
 `x = z * y + 4`  
  
 El ejemplo anterior multiplica `z` por `y` y suma el resultado a `4`.  Si desea sumar `y` y `4` antes de multiplicar el resultado por `z`, puede anular la prioridad de operadores normal utilizando paréntesis.  Si escribe una expresión entre paréntesis, fuerza a que dicha expresión se evalúe primero, independientemente de la prioridad de operador.  Para indicar que en el ejemplo anterior se lleve a cabo la suma en primer lugar, podría reescribirlo como en el ejemplo siguiente.  
  
 `x = z * (y + 4)`  
  
 El ejemplo anterior suma `y` y `4` y, a continuación, multiplica esa suma por `z`.  
  
### Expresiones entre paréntesis anidadas  
 Puede anidar expresiones en varios niveles de paréntesis para anular todavía más la prioridad.  La expresión en el último nivel de anidación entre paréntesis se evalúa en primer lugar, después la siguiente expresión más anidada y así sucesivamente hasta el último nivel de anidación; por último, se evalúan las expresiones situadas fuera de los paréntesis.  Esto se ilustra en el siguiente ejemplo:  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 En el ejemplo anterior, se evalúa `z + 2` en primer lugar y, a continuación, las otras expresiones entre paréntesis.  La exponenciación, que generalmente tiene mayor prioridad que la suma o la multiplicación, se evalúa en último lugar debido a que las demás expresiones están escritas entre paréntesis.  
  
## Vea también  
 [Operadores aritméticos en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Operadores de comparación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Operadores lógicos y bit a bit en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)   
 [Operadores lógicos y operadores bit a bit](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Expresiones booleanas](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)   
 [Comparaciones de valores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Cómo: Calcular valores numéricos](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)   
 [Prioridad de operador en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)