---
title: "&amp;= (Operador, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.&="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "&= (operador) [Visual Basic]"
  - "instrucciones de asignación, compuesta"
  - "instrucciones de asignación compuesta"
  - "operador &="
  - "instrucciones [Visual Basic], asignación compuesta"
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# &amp;= (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Concatena una expresión `String` a una variable o propiedad `String` y asigna el resultado a la variable o propiedad.  
  
## Sintaxis  
  
```  
  
variableorproperty &= expression  
```  
  
## Elementos  
 `variableorproperty`  
 Obligatorio.  Cualquier propiedad o variable de tipo `String`.  
  
 `expression`  
 Obligatorio.  Cualquier expresión de tipo `String`.  
  
## Comentarios  
 El elemento situado a la izquierda del operador `&=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz.  La variable o la propiedad no pueden ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  El operador de `&=` concatena la expresión de `String` en su derecha a la variable de `String` o la propiedad a la izquierda, y asigna el resultado a la variable o propiedad en su izquierda.  
  
## Sobrecarga  
 El operador [& \(Operador\)](../../../visual-basic/language-reference/operators/concatenation-operator.md) se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  La sobrecarga del operador `&` afecta al comportamiento del operador `&=`.  Si el código utiliza `&=` en una clase o estructura que sobrecarga `&`, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el siguiente ejemplo se utiliza el operador `&=` para concatenar dos variables `String` y asignar el resultado a la primera variable.  
  
 [!code-vb[VbVbalrOperators#3](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/and-assignment-operator_1.vb)]  
  
## Vea también  
 [& \(Operador\)](../../../visual-basic/language-reference/operators/concatenation-operator.md)   
 [\+\= \(Operador\)](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)   
 [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Operadores de concatenación](../../../visual-basic/language-reference/operators/concatenation-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)