---
title: "Comparaciones de valores (Visual Basic) | Microsoft Docs"
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
  - "operadores de comparación, comparar expresiones"
  - "expresiones [Visual Basic], comparar"
  - "expresiones numéricas"
  - "operadores [Visual Basic], comparación"
  - "variables [Visual Basic], comparar valores"
  - "código de Visual Basic, expresiones"
  - "código de Visual Basic, operadores"
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Comparaciones de valores (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Los operadores de comparación pueden utilizarse para construir expresiones que comparan los valores de variables numéricas.  Estas expresiones devuelven un valor `Boolean` que depende de si la comparación es verdadera o falsa.  A continuación se exponen ejemplos de estas expresiones.  
  
 `45 > 26`  
  
 `26 > 45`  
  
 La primera expresión se evalúa como `True`, porque 45 es mayor que 26.  El segundo ejemplo se evalúa como `False`, porque 26 no es mayor que 45.  
  
 También puede comparar cualquier par de expresiones numéricas de este modo.  Las expresiones comparadas pueden ser complejas, como en el siguiente ejemplo:  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 Esta expresión compleja incluye literales, variables y llamadas a funciones.  Se evalúan las expresiones especificadas a ambos lados del operador de comparación y los valores resultantes se comparan mediante el operador de comparación `>=`.  Si el valor de la expresión de la izquierda es mayor o igual que el valor de la expresión de la derecha, la evaluación de la expresión completa devuelve `True`; de lo contrario, devuelve `False`.  
  
 Las expresiones que comparan valores se utilizan con frecuencia en construcciones `If...Then`, como en el siguiente ejemplo.  
  
 [!code-vb[VbVbalrOperators#84](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/value-comparisons_1.vb)]  
  
 El signo `=` es un operador de comparación, además de un operador de asignación.  Cuando se utiliza como operador de comparación, evalúa si el valor de la izquierda es igual que el valor de la derecha, como se muestra en el siguiente ejemplo.  
  
 [!code-vb[VbVbalrOperators#85](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/value-comparisons_2.vb)]  
  
 Una expresión de comparación también se puede utilizar allí donde sea necesario un valor `Boolean`, como en una instrucción `If`, `While`, `Loop`, `ElseIf`, o cuando se asigna o se pasa un valor a una variable `Boolean`.  En el siguiente ejemplo, el valor devuelto por la expresión de comparación se asigna a una variable `Boolean`.  
  
 [!code-vb[VbVbalrOperators#86](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/value-comparisons_3.vb)]  
  
## Vea también  
 [Expresiones booleanas](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)   
 [Operadores y expresiones](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Operadores de comparación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Cómo: Calcular valores numéricos](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)   
 [Prioridad de operador en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)