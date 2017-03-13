---
title: "Operadores y expresiones en Visual Basic | Microsoft Docs"
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
  - "expresiones [Visual Basic]"
  - "operandos"
  - "operandos, definición"
  - "operadores [Visual Basic]"
  - "operadores [Visual Basic], operandos"
  - "código de Visual Basic, expresiones"
  - "código de Visual Basic, operadores"
ms.assetid: b86f3131-94ee-448f-96cd-79611e028b26
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Operadores y expresiones en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Un *operador* es un elemento de código que realiza una operación en uno o más elementos de código que contienen valores.  Los elementos de valor incluyen variables, constantes, literales, propiedades, valores devueltos de procedimientos `Function` y `Operator` y expresiones.  
  
 Una *expresión* es una serie de elementos de valor combinados con operadores, que produce un nuevo valor.  Los operadores actúan sobre los elementos de valor realizando cálculos, comparaciones y otras operaciones.  
  
## Tipos de operadores  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] proporciona los tipos de operadores siguientes:  
  
-   [Operadores aritméticos](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md), realizan los cálculos familiares en valores numéricos, incluido el desplazamiento de sus modelos de bits.  
  
-   [Operadores de comparación](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md), comparan dos expresiones y devuelven un valor `Boolean` que representa el resultado de la comparación.  
  
-   [Operadores de concatenación](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md), combinan varias cadenas en una sola.  
  
-   [Operadores lógicos y bit a bit en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md), combinan valores `Boolean` o numéricos y devuelven un resultado del mismo tipo de datos que los valores.  
  
 Los elementos de valor que se combinan con un operador se denominan *operandos* de ese operador.  Los operadores combinados con los elementos de valor forman expresiones, salvo el operador de asignación, que forma una *instrucción*.  Para obtener más información, vea [Instrucciones](../../../../visual-basic/programming-guide/language-features/statements.md).  
  
## Evaluación de expresiones  
 El resultado final de una expresión representa un valor, que suele ser de un tipo de datos habitual como `Boolean`, `String` o un tipo numérico.  
  
 A continuación se muestran ejemplos de expresiones.  
  
 `5 + 4`  
  
 `' The preceding expression evaluates to 9.`  
  
 `15 * System.Math.Sqrt(9) + x`  
  
 `' The preceding expression evaluates to 45 plus the value of x.`  
  
 `"Concat" & "ena" & "tion"`  
  
 `' The preceding expression evaluates to "Concatenation".`  
  
 `763 < 23`  
  
 `' The preceding expression evaluates to False.`  
  
 Varios operadores pueden realizar acciones en una expresión o instrucción simples, como se muestra en el siguiente ejemplo.  
  
 [!code-vb[VbVbalrOperators#56](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/index_1.vb)]  
  
 En el ejemplo anterior, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] realiza las operaciones en la expresión del lado derecho del operador de asignación \(`=`\) y, a continuación, asigna el valor resultante a la variable `x` de la izquierda.  No existe un límite real en cuanto al número de operadores que se pueden combinar en una expresión, pero debe comprender que es necesaria la [Prioridad de operador en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md) para asegurarse de que obtendrá los resultados previstos.  
  
 Para obtener más información y ejemplos, vea [Sobrecarga en Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703)  
  
## Vea también  
 [Operadores](../../../../visual-basic/language-reference/operators/index.md)   
 [Combinación eficaz de operadores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)   
 [Instrucciones](../../../../visual-basic/language-reference/statements/index.md)