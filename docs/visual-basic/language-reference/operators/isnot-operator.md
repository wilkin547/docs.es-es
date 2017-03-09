---
title: "IsNot (Operador) (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.isnot"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "IsNot (operador)"
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# IsNot (Operador) (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Compara dos variables de referencia de objeto.  
  
## Sintaxis  
  
```  
  
result = object1 IsNot object2  
```  
  
## Elementos  
 `result`  
 Obligatorio.  Valor `Boolean`.  
  
 `object1`  
 Obligatorio.  Cualquier variable o expresión de tipo `Object`.  
  
 `object2`  
 Obligatorio.  Cualquier variable o expresión de tipo `Object`.  
  
## Comentarios  
 El operador `IsNot` determina si dos referencias a objeto hacen referencia a objetos diferentes.  Sin embargo, no establece comparaciones entre valores.  Si `object1` y `object2` hacen referencia la misma instancia de objeto exacta, `result` da como resultado `False`; si no es así, `result` da como resultado `True`.  
  
 `IsNot` es el opuesto del operador `Is`.  La ventaja de `IsNot` es que puede evitar sintaxis extraña con `Not` e `Is`, que puede ser difícil de leer.  
  
 Puede utilizar los operadores `Is` e `IsNot` para probar objetos enlazados en tiempo de compilación y en tiempo de ejecución.  
  
> [!NOTE]
>  El operador `IsNot` no se puede utilizar para comparar expresiones devueltas del operador `TypeOf`.  En su lugar, debe utilizar los operadores `Not` e `Is`.  
  
## Ejemplo  
 El ejemplo de código siguiente utiliza los operadores `Is` e `IsNot` para lograr la misma comparación.  
  
 [!code-vb[VbVbalrOperators#29](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/isnot-operator_1.vb)]  
  
## Vea también  
 [Is \(Operador\)](../../../visual-basic/language-reference/operators/is-operator.md)   
 [TypeOf \(Operador\)](../../../visual-basic/language-reference/operators/typeof-operator.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Cómo: Comprobar si dos objetos son iguales](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)