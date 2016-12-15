---
title: "+= (Operador, Visual Basic) | Microsoft Docs"
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
  - "vb.+="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "+= (operador) [Visual Basic]"
  - "+= (operador) [Visual Basic], anexar cadenas"
  - "instrucciones de asignación, compuesta"
  - "instrucciones de asignación compuesta"
  - "instrucciones [Visual Basic], asignación compuesta"
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# += (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Suma el valor de una expresión numérica al valor de una propiedad o variable numérica y asigna el resultado a la variable o a la propiedad.  También se puede utilizar para concatenar una expresión `String` con una propiedad o variable `String` y asignar el resultado a la variable o a la propiedad.  
  
## Sintaxis  
  
```  
  
variableorproperty += expression  
```  
  
## Elementos  
 `variableorproperty`  
 Obligatorio.  Cualquier propiedad o variable `String` numérica.  
  
 `expression`  
 Obligatorio.  Cualquier expresión numérica o `String`.  
  
## Comentarios  
 El elemento situado a la izquierda del operador `+=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz.  La variable o la propiedad no pueden ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 El operador de `+=` agrega el valor de la derecha a la variable o propiedad de la izquierda, y asigna el resultado a la variable o propiedad en su izquierda.  El operador de `+=` también se puede utilizar para concatenar la expresión de `String` en su derecha a la variable de `String` o la propiedad a la izquierda, y asignar el resultado a la variable o propiedad en su izquierda.  
  
> [!NOTE]
>  Cuando utilice el operador `+=`, puede que no logre determinar si se producirá una suma o bien una concatenación de cadenas.  Use el operador `&=` de concatenación para eliminar ambigüedades y ofrecer código autoexplicativo.  
  
 Este operador de asignación realizará implícitamente conversiones de ampliación pero no de restricción si el entorno de compilación fuerza una semántica estricta.  Para obtener más información sobre estas conversiones, vea [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  Para obtener más información sobre semánticas de tipos permisivas y estrictas, vea [Option Strict \(Instrucción\)](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
 Si se permite una semántica de tipos permisiva, el operador `+=` realizará de forma implícita una serie de conversiones de cadenas o conversiones numéricas idénticas a las que lleva a cabo el operador `+`.  Para obtener información detallada sobre estas conversiones, vea [\+ \(Operador\)](../../../visual-basic/language-reference/operators/addition-operator.md).  
  
## Sobrecarga  
 El operador `+` se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  La sobrecarga del operador `+` afecta al comportamiento del operador `+=`.  Si el código utiliza `+=` en una clase o estructura que sobrecarga `+`, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza el operador `+=` para combinar el valor de una variable con otra.  La primera parte utiliza `+=` con variables numéricas para sumar un valor a otro.  La segunda parte utiliza `+=` con variables `String` para concatenar un valor con otro.  En ambos casos, el resultado se asigna a la primera variable.  
  
 [!code-vb[VbVbalrOperators#7](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_1.vb)]  
  
 [!code-vb[VbVbalrOperators#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_2.vb)]  
  
 El valor de `num1` es ahora 13 y el valor de `str1` es ahora "103".  
  
## Vea también  
 [\+ \(Operador\)](../../../visual-basic/language-reference/operators/addition-operator.md)   
 [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operadores de concatenación](../../../visual-basic/language-reference/operators/concatenation-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)