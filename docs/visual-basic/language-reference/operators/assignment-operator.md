---
title: "= (Operador, Visual Basic) | Microsoft Docs"
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
  - "vb.Assign"
  - "vb.="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "= (instrucciones de asignación) [Visual Basic]"
  - "= (operador) [Visual Basic]"
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# = (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Asigna un valor a una variable o propiedad.  
  
## Sintaxis  
  
```  
  
variableorproperty = value  
```  
  
## Elementos  
 `variableorproperty`  
 Cualquier variable o propiedad que se puede escribir.  
  
 `value`  
 Cualquier literal, constante o expresión.  
  
## Comentarios  
 El elemento situado a la izquierda del signo igual \(`=`\) puede ser una variable escalar simple, una propiedad o un elemento de una matriz.  La variable o la propiedad no pueden ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  El operador `=` asigna el valor situado a su derecha a la variable o la propiedad situada a su izquierda.  
  
> [!NOTE]
>  El operador `=` también se utiliza como operador de comparación.  Para obtener información detallada, vea [Operadores de comparación](../../../visual-basic/language-reference/operators/comparison-operators.md).  
  
## Sobrecarga  
 El operador `=` sólo se puede sobrecargar como un operador de comparación relacional, no como un operador de asignación.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 El ejemplo siguiente muestra el operador de asignación.  El valor de la derecha se asigna a la variable de la izquierda.  
  
 [!code-vb[VbVbalrOperators#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]  
  
## Vea también  
 [&\= \(Operador\)](../../../visual-basic/language-reference/operators/and-assignment-operator.md)   
 [\*\= \(Operador\)](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)   
 [\+\= \(Operador\)](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)   
 [\-\= \(Operador\)](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)   
 [\/\= \(Operador\)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)   
 [\\\= \(Operador\)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)   
 [^\= \(Operador\)](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)   
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Operadores de comparación](../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)   
 [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)