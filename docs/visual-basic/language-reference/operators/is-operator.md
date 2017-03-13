---
title: "Is (Operador, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.is"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "operadores de comparación"
  - "objetos equivalentes"
  - "Is (operador) [Visual Basic]"
  - "TypeOf...Is (expresión)"
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Is (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Compara dos variables de referencia de objeto.  
  
## Sintaxis  
  
```  
  
result = object1 Is object2  
```  
  
## Elementos  
 `result`  
 Obligatorio.  Cualquier valor de tipo `Boolean`.  
  
 `object1`  
 Obligatorio.  Cualquier nombre de `Object`.  
  
 `object2`  
 Obligatorio.  Cualquier nombre de `Object`.  
  
## Comentarios  
 El operador `Is` determina si dos referencias de objeto hacen referencia al mismo objeto.  Sin embargo, no establece comparaciones entre valores.  Si `object1` y `object2` hacen referencia la misma instancia de objeto exacta, `result` da como resultado `True`; si no es así, `result` da como resultado `False`.  
  
 `Is` también se puede utilizar con la palabra clave `TypeOf` para crear una expresión `TypeOf`...`Is`, que comprueba si una variable de objeto es compatible con un tipo de datos.  
  
> [!NOTE]
>  La palabra clave `Is` se utiliza también en la [Select...Case \(Instrucción\)](../../../visual-basic/language-reference/statements/select-case-statement.md):  
  
## Ejemplo  
 El ejemplo siguiente utiliza el operador `Is` para comparar pares de referencias a objeto.  El resultado se asigna a un valor de tipo `Boolean` que indica si ambos objetos son idénticos.  
  
 [!code-vb[VbVbalrOperators#27](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/is-operator_1.vb)]  
  
 Como muestra el ejemplo anterior, puede utilizar el operador `Is` para comprobar objetos enlazados en tiempo de compilación y en tiempo de ejecución.  
  
## Vea también  
 [TypeOf \(Operador\)](../../../visual-basic/language-reference/operators/typeof-operator.md)   
 [IsNot \(Operador\)](../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Operadores de comparación en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)