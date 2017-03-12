---
title: "C&#243;mo: Obtener la direcci&#243;n de una variable (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "expresiones de puntero [C#], address-of (operador)"
  - "punteros [C#], & (operador)"
  - "variables [C#], address of"
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# C&#243;mo: Obtener la direcci&#243;n de una variable (Gu&#237;a de programaci&#243;n de C#)
Para obtener la dirección de una expresión unaria, que se evalúa como una variable fija, use el operador de dirección.  
  
```  
int number;  
int* p = &number; //address-of operator &  
```  
  
 El operador de dirección sólo se puede aplicar a una variable.  Si la variable es una variable móvil, puede utilizar la [instrucción fixed](../../../csharp/language-reference/keywords/fixed-statement.md) para fijar temporalmente la variable antes de obtener su dirección.  
  
 Es responsabilidad del usuario asegurarse de que se inicialice la variable.  El compilador no emitirá un mensaje de error si no se inicializa la variable.  
  
 No se puede obtener la dirección de una constante o un valor.  
  
## Ejemplo  
 En este ejemplo, se declara un puntero a `int`, `p`, y se le asigna la dirección de una variable de entero, `number`.  La variable `number` se inicializa como resultado de la asignación a \*p.  Comentar esta instrucción de asignación quitará la inicialización de la variable `number`, pero no se emitirá un error de compilación.  Observe el uso del operador [Acceso a miembros](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) `->` para obtener y mostrar la dirección almacenada en el puntero.  
  
 [!code-cs[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers2.cs#7)]  
  
 [!code-cs[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers.cs#8)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Tipos](../../../csharp/language-reference/keywords/types.md)   
 [no seguras](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed \(Instrucción\)](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)