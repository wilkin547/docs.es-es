---
title: "&gt;&gt;= (Operador, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.>>="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - ">>= (operador) [Visual Basic]"
  - "instrucciones de asignación, compuesta"
  - "instrucciones de asignación compuesta"
  - ">>= (operador) [Visual Basic]"
  - "instrucciones [Visual Basic], asignación compuesta"
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# &gt;&gt;= (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Realiza un desplazamiento aritmético a la derecha sobre el valor de una variable o una propiedad y asigna el nuevo valor a la variable o la propiedad.  
  
## Sintaxis  
  
```  
  
variableorproperty >>= amount  
```  
  
## Elementos  
 `variableorproperty`  
 Obligatorio.  Variable o propiedad de un tipo entero \(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` o `ULong`\).  
  
 `amount`  
 Obligatorio.  Expresión numérica de un tipo de datos que se amplíe a `Integer`.  
  
## Comentarios  
 El elemento situado a la izquierda del operador `>>=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz.  La variable o la propiedad no pueden ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 El operador de `>>=` primero realiza un desplazamiento aritmético a la derecha en el valor de la variable o propiedad.  El operador y asigna el resultado de esa operación de nuevo a la variable o la propiedad.  
  
 Los desplazamientos aritméticos no son circulares, lo que significa que los bits desplazados a un extremo del resultado no se vuelven a introducir en el otro extremo.  En un desplazamiento aritmético a la derecha, los bits desplazados más allá del extremo derecho se descartan y el bit del extremo izquierdo se propaga a las posiciones de bit que quedan vacantes a la izquierda.  Esto significa que, si `variableorproperty` tiene un valor negativo, las posiciones vacantes se establecen en uno.  Si `variableorproperty` es positiva o su tipo de datos es un tipo sin signo, las posiciones vacantes se establecen en cero.  
  
## Sobrecarga  
 El operador [\>\> \(Operador\)](../../../visual-basic/language-reference/operators/right-shift-operator.md) se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  La sobrecarga del operador `>>` afecta al comportamiento del operador `>>=`.  Si el código utiliza `>>=` en una clase o estructura que sobrecarga `>>`, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el siguiente ejemplo se utiliza el operador `>>=` para desplazar el modelo de bits de una variable `Integer` a la derecha en la cantidad especificada y asignar el resultado a la variable.  
  
 [!code-vb[VbVbalrOperators#15](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/right-shift-assignment-o_1_1.vb)]  
  
## Vea también  
 [\>\> \(Operador\)](../../../visual-basic/language-reference/operators/right-shift-operator.md)   
 [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Operadores de desplazamiento](../../../visual-basic/language-reference/operators/bit-shift-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)