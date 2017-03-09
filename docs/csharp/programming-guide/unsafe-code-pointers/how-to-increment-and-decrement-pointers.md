---
title: "C&#243;mo: Aumentar y disminuir punteros (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "expresiones de puntero [C#], incremento y decremento"
  - "punteros [C#], incremento y decremento"
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# C&#243;mo: Aumentar y disminuir punteros (Gu&#237;a de programaci&#243;n de C#)
Utilice los operadores de incremento y decremento, `++` y `--`, para cambiar la ubicación del puntero en [sizeof](../../../csharp/language-reference/keywords/sizeof.md) \(`pointer-type`\) para un puntero de tipo pointer\-type\*.  Las expresiones de incremento y decremento adquieren la forma siguiente:  
  
```  
++p;  
p++;  
--p;  
p--;  
```  
  
 Los operadores de incremento y decremento se pueden aplicar a punteros de cualquier tipo, a excepción del tipo `void*`.  
  
 El efecto de aplicar el operador de incremento a un puntero del tipo `pointer-type` es agregar [sizeof](../../../csharp/language-reference/keywords/sizeof.md) \(`pointer-type`\) a la dirección que está en la variable del puntero.  
  
 El efecto de aplicar el operador de decremento a un puntero del tipo `pointer-type` es restar `sizeof` \(`pointer-type`\) de la dirección que está en la variable del puntero.  
  
 No se genera ninguna excepción cuando la operación desborda el dominio del puntero y el resultado depende de la implementación.  
  
## Ejemplo  
 En este ejemplo, se avanza a través de una matriz incrementando el puntero según el tamaño de `int`.  Con cada paso que avanza, se muestra la dirección y el contenido del elemento de matriz.  
  
 [!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers2.cs#3)]  
  
 [!code-cs[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers.cs#13)]  
  
  **Value:0 @ Address:12860272**  
**Value:1 @ Address:12860276**  
**Value:2 @ Address:12860280**  
**Value:3 @ Address:12860284**  
**Value:4 @ Address:12860288**   
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)   
 [Manipular punteros](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)   
 [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Tipos](../../../csharp/language-reference/keywords/types.md)   
 [no seguras](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed \(Instrucción\)](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)