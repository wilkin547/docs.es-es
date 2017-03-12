---
title: "Prioridad de operador en Visual Basic | Microsoft Docs"
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
  - "operadores aritméticos, prioridad"
  - "asociatividad de operadores"
  - "operadores de comparación, prioridad"
  - "operadores lógicos, prioridad"
  - "operadores matemáticos"
  - "prioridad de operadores"
  - "operadores [Visual Basic], asociatividad"
  - "operadores [Visual Basic], prioridad"
  - "operadores [Visual Basic], resolución"
  - "orden de prioridad"
  - "prioridad, de operadores"
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Prioridad de operador en Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Cuando aparecen varias operaciones en una expresión, cada parte se evalúa y se resuelve en un orden predeterminado conocido como *prioridad de operador*.  
  
## Reglas de prioridad  
 Cuando las expresiones contienen operadores de más de una categoría, dichos operadores se evalúan de acuerdo con las siguientes reglas:  
  
-   Los operadores aritméticos y de concatenación tienen el orden de prioridad que se describe en la siguiente sección y tienen prioridad sobre los operadores lógicos, de comparación y bit a bit.  
  
-   Todos los operadores de comparación tienen la misma prioridad; todos ellos tienen mayor prioridad que los operadores lógicos y los operadores bit a bit, pero menor prioridad que los operadores de concatenación y los operadores aritméticos.  
  
-   Los operadores lógicos y bit a bit tienen el orden de prioridad que se describe en la siguiente sección y tienen menor prioridad que los operadores aritméticos, de concatenación y de comparación.  
  
-   Los operadores con la misma prioridad se evalúan de izquierda a derecha en el orden en que aparecen en la expresión.  
  
## Orden de prioridad  
 Los operadores se evalúan en el siguiente orden de prioridad:  
  
### Espera el operador  
 Await  
  
### Operadores de concatenación y aritméticos  
 Exponenciación \(`^`\)  
  
 Identidad y negación unarios \(`+`, `–`\)  
  
 Multiplicación y división de punto flotante \(`*`, `/`\)  
  
 División de número entero \(`\`\)  
  
 Módulo aritmético \(`Mod`\)  
  
 Suma y resta \(`+`, `–`\)  
  
 Concatenación de cadenas \(`&`\)  
  
 Desplazamiento de bits aritmético \(`<<`, `>>`\)  
  
### Operadores de comparación  
 Todos los operadores de comparación \(`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`\)  
  
### Operadores lógicos y bit a bit  
 Negación \(`Not`\)  
  
 Conjunción \(`And`, `AndAlso`\)  
  
 Disyunción inclusiva \(`Or`, `OrElse`\)  
  
 Disyunción exclusiva \(`Xor`\)  
  
### Comentarios  
 El operador `=` sólo es el operador de comparación de igualdad, no el operador de asignación.  
  
 El operador de concatenación de cadenas \(`&`\) no es un operador aritmético, pero en cuanto a prioridad, se agrupa con los operadores aritméticos.  
  
 Los operadores `Is` e `IsNot` son los operadores de comparación de referencia de objeto.  No comparan los valores de dos objetos; sólo comprueban y determinan si dos variables de objeto hacen referencia a la misma instancia del objeto.  
  
## Asociatividad  
 Cuando aparecen operadores de la misma prioridad juntos en una expresión, por ejemplo, multiplicación y división, el compilador evalúa cada operación de izquierda a derecha.  Esto se ilustra en el siguiente ejemplo:  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 La primera expresión evalúa la división 96 \/ 8 \(que da como resultado 12\) y, a continuación, la división 12 \/ 4 que es igual a tres.  Dado que el compilador evalúa de izquierda a derecha las operaciones para `n1`, la evaluación es igual cuando se indica ese orden explícitamente para `n2`.  Tanto `n1` como `n2` dan como resultado tres.  En cambio, `n3` da como resultado 48, porque los paréntesis fuerzan a que el compilador evalúe 8 \/ 4 en primer lugar.  
  
 Debido a este comportamiento, se dice que los operadores son *asociativos por la izquierda* en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
## Modificación de la prioridad y la asociatividad  
 Puede utilizar paréntesis para hacer que determinadas partes de una expresión se evalúen antes que otras.  Esto puede invalidar el orden de prioridad y la asociatividad por la izquierda.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] realiza siempre las operaciones que están escritas entre paréntesis antes de las fuera de. Sin embargo, dentro de los paréntesis, mantiene prioridad y asociatividad normales, a menos que utilice paréntesis entre paréntesis.  Esto se ilustra en el siguiente ejemplo:  
  
```  
Dim a, b, c, d, e, f, g As Double  
a = 8.0  
b = 3.0  
c = 4.0  
d = 2.0  
e = 1.0  
f = a - b + c / d * e  
' The preceding line sets f to 7.0. Because of natural operator   
' precedence and associativity, it is exactly equivalent to the   
' following line.  
f = (a - b) + ((c / d) * e)  
' The following line overrides the natural operator precedence   
' and left associativity.  
g = (a - (b + c)) / (d * e)  
' The preceding line sets g to 0.5.  
```  
  
## Vea también  
 [\= \(Operador\)](../../../visual-basic/language-reference/operators/assignment-operator.md)   
 [Is \(Operador\)](../../../visual-basic/language-reference/operators/is-operator.md)   
 [IsNot \(Operador\)](../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Like \(Operador\)](../../../visual-basic/language-reference/operators/like-operator.md)   
 [TypeOf \(Operador\)](../../../visual-basic/language-reference/operators/typeof-operator.md)   
 [Await \(Operador\)](../../../visual-basic/language-reference/operators/await-operator.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)