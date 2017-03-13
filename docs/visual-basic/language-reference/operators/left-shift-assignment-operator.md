---
title: "&lt;&lt;= (Operador, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.<<="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "<<= (operador) [Visual Basic]"
  - "instrucciones de asignación, compuesta"
  - "instrucciones de asignación compuesta"
  - "operador <<="
  - "(<<=) operador"
  - "instrucciones [Visual Basic], asignación compuesta"
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# &lt;&lt;= (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Realiza un desplazamiento aritmético a la izquierda sobre el valor de una variable o una propiedad y asigna el nuevo valor a la variable o la propiedad.  
  
## Sintaxis  
  
```  
  
variableorproperty <<= amount  
```  
  
## Elementos  
 `variableorproperty`  
 Obligatorio.  Variable o propiedad de un tipo entero \(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` o `ULong`\).  
  
 `amount`  
 Obligatorio.  Expresión numérica de un tipo de datos que se amplíe a `Integer`.  
  
## Comentarios  
 El elemento situado a la izquierda del operador `<<=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz.  La variable o la propiedad no pueden ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 El operador de `<<=` primero realiza un desplazamiento aritmético a la izquierda en el valor de la variable o propiedad.  El operador y asigna el resultado de esa operación de nuevo a esa variable o propiedad.  
  
 Los desplazamientos aritméticos no son circulares, lo que significa que los bits desplazados a un extremo del resultado no se vuelven a introducir en el otro extremo.  En un desplazamiento aritmético a la izquierda, los bits desplazados más allá del intervalo del tipo de datos del resultado se descartan y las posiciones vacías de los bits de la derecha se establecen en cero.  
  
## Sobrecarga  
 El operador [\<\< \(Operador\)](../../../visual-basic/language-reference/operators/left-shift-operator.md) se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  La sobrecarga del operador `<<` afecta al comportamiento del operador `<<=`.  Si el código utiliza `<<=` en una clase o estructura que sobrecarga `<<`, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el siguiente ejemplo se utiliza el operador `<<=` para desplazar el modelo de bits de una variable `Integer` a la izquierda en la cantidad especificada y asignar el resultado a la variable.  
  
 [!code-vb[VbVbalrOperators#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-assignment-operator_1.vb)]  
  
## Vea también  
 [\<\< \(Operador\)](../../../visual-basic/language-reference/operators/left-shift-operator.md)   
 [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Operadores de desplazamiento](../../../visual-basic/language-reference/operators/bit-shift-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)