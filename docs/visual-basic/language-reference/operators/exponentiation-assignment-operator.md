---
title: "^= (Operador, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.^="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "^= (operador) [Visual Basic]"
  - "instrucciones de asignación, compuesta"
  - "instrucciones de asignación compuesta"
  - "instrucciones [Visual Basic], asignación compuesta"
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# ^= (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Eleva el valor de una variable o una propiedad a la potencia de una expresión y asigna el resultado de nuevo a la variable o la propiedad.  
  
## Sintaxis  
  
```  
  
variableorproperty ^= expression  
```  
  
## Elementos  
 `variableorproperty`  
 Obligatorio.  Cualquier propiedad o variable numérica.  
  
 `expression`  
 Obligatorio.  Cualquier expresión numérica.  
  
## Comentarios  
 El elemento situado a la izquierda del operador `^=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz.  La variable o la propiedad no pueden ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 El operador de `^=` primero genera el valor de la variable o propiedad \(a la izquierda del operador\) a la potencia del valor de la expresión \(en el lado derecho del operador\).  El operador y asigna el resultado de esa operación de nuevo a la variable o la propiedad.  
  
 Visual Basic siempre realiza la exponenciación en [Double \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/double-data-type.md).  Los operandos de cualquier tipo diferente se convierten en `Double` y el resultado siempre es `Double`.  
  
 El valor de `expression` puede ser fraccionario, negativo o ambos.  
  
## Sobrecarga  
 El operador [^ \(Operador\)](../../../visual-basic/language-reference/operators/exponentiation-operator.md) se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  La sobrecarga del operador `^` afecta al comportamiento del operador `^=`.  Si el código utiliza `^=` en una clase o estructura que sobrecarga `^`, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el siguiente ejemplo se utiliza el operador `^=` para elevar el valor de una variable `Integer` a la potencia de una segunda variable y asignar el resultado a la primera variable.  
  
 [!code-vb[VbVbalrOperators#21](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/exponentiation-assignmen_1.vb)]  
  
## Vea también  
 [^ \(Operador\)](../../../visual-basic/language-reference/operators/exponentiation-operator.md)   
 [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)