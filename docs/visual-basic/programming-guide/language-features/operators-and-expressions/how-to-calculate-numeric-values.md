---
title: "C&#243;mo: Calcular valores num&#233;ricos (Visual Basic) | Microsoft Docs"
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
  - "cálculos, expresiones numéricas"
  - "expresiones [Visual Basic], numéricas"
  - "expresiones numéricas"
  - "prioridad de operadores"
  - "operadores [Visual Basic]"
  - "prioridad, de operadores"
  - "código de Visual Basic, expresiones"
  - "código de Visual Basic, operadores"
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# C&#243;mo: Calcular valores num&#233;ricos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Puede calcular valores numéricos mediante el uso de expresiones numéricas.  Una *expresión numérica* es una expresión que contiene literales, constantes y variables que representan valores numéricos, y operadores que actúan sobre esos valores.  
  
## Calcular valores numéricos  
  
#### Para calcular un valor numérico  
  
-   Combine uno o más literales, constantes y variables numéricos en una expresión numérica.  El ejemplo siguiente muestra algunas expresiones numéricas válidas.  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     Las tres primeras líneas muestran un literal, una constante y una variable.  Cada uno forma una expresión numérica válida por sí mismo.  La línea final muestra una combinación de una variable con dos literales.  
  
     Observe que una expresión numérica no forma una instrucción de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] completa por sí misma.  Debe utilizar la expresión como parte de una instrucción completa.  
  
#### Para almacenar un valor numérico  
  
-   Puede utilizar una instrucción de asignación para asignar el valor representado por una expresión numérica a una variable, como se muestra en el ejemplo siguiente.  
  
     [!code-vb[VbVbalrOperators#82](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-calculate-numeric_1.vb)]  
  
     En el ejemplo anterior, el valor de la expresión situada a la derecha del operador igual \(`=`\) se asigna a la variable `j` situada a la izquierda del operador, por lo que `j` da como resultado 276.  
  
     Para obtener más información, vea [Instrucciones](../../../../visual-basic/language-reference/statements/index.md).  
  
## Varios operadores  
 Si la expresión numérica contiene más de un operador, el orden en que se evalúan lo determina las reglas de prioridad de operador.  Para anular las reglas de prioridad de operador, las expresiones se escriben entre paréntesis, como en el ejemplo anterior; estas expresiones se evalúan primero.  
  
#### Para reemplazar la prioridad normal de operadores  
  
-   Utilice paréntesis para indicar las operaciones que desea efectuar en primer lugar.  En el ejemplo siguiente se muestran dos resultados diferentes con los mismos operandos y operadores.  
  
     [!code-vb[VbVbalrOperators#83](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-calculate-numeric_2.vb)]  
  
     En el ejemplo anterior, el cálculo de `j` ejecuta el operador de suma \(`+`\) en primer lugar debido a que los paréntesis en `(67 + i)` anulan la prioridad normal, por lo que el valor asignado a `j` es 276 \(4 por 69\).  El cálculo de `k` ejecuta los operadores con su prioridad normal \(`*` antes de `+`\), por lo que el valor asignado a `k` es 270 \(268 más 2\).  
  
     Para obtener más información, vea [Prioridad de operador en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## Vea también  
 [Operadores y expresiones](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Comparaciones de valores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Instrucciones](../../../../visual-basic/language-reference/statements/index.md)   
 [Prioridad de operador en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores aritméticos](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Combinación eficaz de operadores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)