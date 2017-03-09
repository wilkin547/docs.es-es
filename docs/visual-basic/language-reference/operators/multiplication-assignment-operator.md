---
title: "*= (Operador, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.*="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "*= (operador) [Visual Basic]"
  - "instrucciones de asignación, compuesta"
  - "instrucciones de asignación compuesta"
  - "operador *="
  - "instrucciones [Visual Basic], asignación compuesta"
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# *= (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Multiplica el valor de una variable o una propiedad por el valor de una expresión y asigna el resultado a la variable o la propiedad.  
  
## Sintaxis  
  
```  
  
variableorproperty *= expression  
```  
  
## Elementos  
 `variableorproperty`  
 Obligatorio.  Cualquier propiedad o variable numérica.  
  
 `expression`  
 Obligatorio.  Cualquier expresión numérica.  
  
## Comentarios  
 El elemento situado a la izquierda del operador `*=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz.  La variable o la propiedad no pueden ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 El operador de `*=` primero multiplica el valor de la expresión \(en el lado derecho del operador\) por el valor de la variable o propiedad \(a la izquierda del operador\).  El operador y asigna el resultado de la operación a la variable o la propiedad.  
  
## Sobrecarga  
 El operador [\* \(Operador\)](../../../visual-basic/language-reference/operators/multiplication-operator.md) se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  La sobrecarga del operador `*` afecta al comportamiento del operador `*=`.  Si el código utiliza `*=` en una clase o estructura que sobrecarga `*`, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el siguiente ejemplo se utiliza el operador `*=` para multiplicar una variable `Integer` por otra y asignar el resultado a la primera variable.  
  
 [!code-vb[VbVbalrOperators#5](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/multiplication-assignmen_1_1.vb)]  
  
## Vea también  
 [\* \(Operador\)](../../../visual-basic/language-reference/operators/multiplication-operator.md)   
 [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)