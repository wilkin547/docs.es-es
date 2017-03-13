---
title: "C&#243;mo: Comprobar si dos objetos son iguales (Visual Basic) | Microsoft Docs"
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
  - "Is (operador) [Visual Basic], comparar objetos"
  - "objetos [Visual Basic], variables que hacen referencia al mismo"
  - "variables de referencia"
  - "variables [Visual Basic], referencia"
  - "variables [Visual Basic], hacer referencia al mismo objeto"
  - "código de Visual Basic, operadores"
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# C&#243;mo: Comprobar si dos objetos son iguales (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Si hay dos variables que hacen referencia a objetos, se puede utilizar el operador `Is` o `IsNot`, o ambos, para determinar si hacen referencia a la misma instancia.  
  
### Para probar si dos objetos son el mismo  
  
-   Utilice el operador [Is \(Operador\)](../../../../visual-basic/language-reference/operators/is-operator.md) o [IsNot \(Operador\)](../../../../visual-basic/language-reference/operators/isnot-operator.md) con las dos variables como operandos.  
  
     [!code-vb[VbVbalrOperators#69](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-test-whether-two-objects-are-the-same_1.vb)]  
  
 Podría ser conveniente tomar ciertas medidas que dependen de si los dos objetos hacen referencia a la misma instancia.  En el ejemplo anterior se compara el control `c` con el control activo en el formulario `f`.  Si no hay un control activo o hay uno que no es la misma instancia de control que `c`, la instrucción `If` genera un error y se vuelve al procedimiento sin procesar la instrucción.  
  
 El uso de `Is` o `IsNot` es una cuestión de preferencias personales.  Uno podría ser más fácil de leer que el otro en una expresión determinada.  
  
## Vea también  
 [Operadores de comparación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)