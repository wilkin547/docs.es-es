---
title: "\= (Operador) | Microsoft Docs"
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
  - "\="
  - "vb.\="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "\= (operador) [Visual Basic]"
  - "instrucciones de asignación, compuesta"
  - "instrucciones de asignación compuesta"
  - "\= (operador) [Visual Basic]"
  - "instrucciones [Visual Basic], asignación compuesta"
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# \= (Operador)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Divide el valor de una variable o una propiedad por el valor de una expresión y asigna el resultado entero a la variable o la propiedad.  
  
## Sintaxis  
  
```  
  
variableorproperty \= expression  
```  
  
## Elementos  
 `variableorproperty`  
 Obligatorio.  Cualquier propiedad o variable numérica.  
  
 `expression`  
 Obligatorio.  Cualquier expresión numérica.  
  
## Comentarios  
 El elemento situado a la izquierda del operador `\=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz.  La variable o la propiedad no pueden ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 El operador de `\=` divide el valor de una variable o una propiedad a la izquierda el valor de la derecha, y asigna el resultado entero en la variable o propiedad en su izquierda  
  
 Para obtener más información sobre división de enteros, vea [\\ \(Operador\)](../../../visual-basic/language-reference/operators/integer-division-operator.md).  
  
## Sobrecarga  
 El operador `\` se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  La sobrecarga del operador `\` afecta al comportamiento del operador `\=`.  Si el código utiliza `\=` en una clase o estructura que sobrecarga `\`, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el siguiente ejemplo se utiliza el operador `\=` para dividir una variable `Integer` por otra y asignar el resultado entero a la primera variable.  
  
 [!code-vb[VbVbalrOperators#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-assignment-operator_1.vb)]  
  
## Vea también  
 [\\ \(Operador\)](../../../visual-basic/language-reference/operators/integer-division-operator.md)   
 [\/\= \(Operador\)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)   
 [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)