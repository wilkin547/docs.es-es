---
title: "C&#243;mo: Obtener el valor de una variable de puntero (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "expresiones de puntero [C#], direccionamiento indirecto"
  - "punteros [C#], * (operador)"
  - "punteros [C#], direccionamiento indirecto"
  - "variables [C#], punteros"
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# C&#243;mo: Obtener el valor de una variable de puntero (Gu&#237;a de programaci&#243;n de C#)
Utilice el operador de direccionamiento indirecto del puntero para obtener la variable en la ubicación indicada por un puntero.  La expresión tiene el formato siguiente, donde  `p` es un tipo de puntero:  
  
```  
*p;  
```  
  
 No se puede utilizar el operador de direccionamiento indirecto unario en una expresión de cualquier tipo distinta de la del tipo de puntero.  Tampoco se puede aplicar a un puntero [void](../../../csharp/language-reference/keywords/void.md).  
  
 Cuando se aplica el operador de direccionamiento indirecto a un puntero [null](../../../csharp/language-reference/keywords/null.md), el resultado depende de la implementación.  
  
## Ejemplo  
 En el ejemplo siguiente, se tiene acceso a una variable del tipo `char` mediante punteros de tipos diferentes.  Hay que tener en cuenta que la dirección de `theChar` variará de una ejecución a otra porque la dirección física asignada a una variable puede cambiar.  
  
 [!code-cs[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers2.cs#5)]  
  
 [!code-cs[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers.cs#6)]  
  
  **Valor de theChar \= Z**   
**Dirección de theChar \= 12F718**  
**Valor de pChar \= Z**   
**Valor de pInt \= 90**    
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Tipos](../../../csharp/language-reference/keywords/types.md)   
 [no seguras](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed \(Instrucción\)](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)