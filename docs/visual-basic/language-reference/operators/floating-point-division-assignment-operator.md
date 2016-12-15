---
title: "/= (Operador, Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb./="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/= (operador) [Visual Basic]"
  - "instrucciones de asignación, compuesta"
  - "instrucciones de asignación compuesta"
  - "/= (operador)"
  - "instrucciones [Visual Basic], asignación compuesta"
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
caps.latest.revision: 23
caps.handback.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /= (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Divide el valor de una variable o una propiedad por el valor de una expresión y asigna el resultado de punto flotante a la variable o la propiedad.  
  
## Sintaxis  
  
```  
  
variableorproperty /= expression  
```  
  
## Elementos  
 `variableorproperty`  
 Obligatorio.  Cualquier propiedad o variable numérica.  
  
 `expression`  
 Obligatorio.  Cualquier expresión numérica.  
  
## Comentarios  
 El elemento situado a la izquierda del operador `/=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz.  La variable o la propiedad no pueden ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 El operador de `/=` primero divide el valor de la variable o propiedad \(a la izquierda del operador\) con el valor de la expresión \(en el lado derecho del operador\).  El operador y asigna el resultado flotante de esa operación a la variable o la propiedad.  
  
 Esta instrucción asigna un valor de `Double` a la variable o propiedad a la izquierda.  Si `Option Strict` es `On`, `variableorproperty` debe ser `Double`.  Si `Option Strict` es `Off`, Visual Basic realiza una conversión implícita y asigna el valor resultante a `variableorproperty`, con un posible error en tiempo de ejecución.  Para obtener más información, vea [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) y [Option Strict \(Instrucción\)](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## Sobrecarga  
 El operador [\/ \(Operador\)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  La sobrecarga del operador `/` afecta al comportamiento del operador `/=`.  Si el código utiliza `/=` en una clase o estructura que sobrecarga `/`, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el siguiente ejemplo se utiliza el operador `/=` para dividir una variable `Integer` por otra y asignar el cociente a la primera variable.  
  
 [!code-vb[VbVbalrOperators#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-assignment-operator_1.vb)]  
  
## Vea también  
 [\/ \(Operador\)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)   
 [\\\= \(Operador\)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)   
 [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)