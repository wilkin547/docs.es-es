---
title: "Operaciones aritm&#233;ticas en punteros (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "punteros [C#], operaciones aritméticas"
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operaciones aritm&#233;ticas en punteros (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En este tema se analiza la utilización de los operadores aritméticos `+` y **\-** para manipular punteros.  
  
> [!NOTE]
>  No se puede realizar ninguna operación aritmética en punteros nulos.  
  
## Sumar valores numéricos a punteros y restarlos de éstos  
 Puede agregar un valor `n` de tipo [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), o [ulong](../../../csharp/language-reference/keywords/ulong.md) a un puntero, `p`, `` de cualquier tipo excepto `void*`.  El resultado `p+n` es el puntero que resulta de sumar `n * sizeof(p) to the address of p`.  De forma similar, `p-n` es el puntero que resulta de restar `n * sizeof(p)` de la dirección de `p`.  
  
## Restar punteros  
 También es posible restar punteros del mismo tipo.  El resultado siempre es de tipo `long`.  Por ejemplo, si `p1` y `p2` son punteros del tipo `pointer-type*`, entonces la expresión `p1-p2` da como resultado:  
  
 `((long)p1 - (long)p2)/sizeof(pointer_type)`  
  
 No se genera ninguna excepción cuando la operación aritmética desborda el dominio del puntero y el resultado depende de la implementación.  
  
## Ejemplo  
 [!code-cs[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]  
  
 [!code-cs[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)   
 [Manipular punteros](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)   
 [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Tipos](../../../csharp/language-reference/keywords/types.md)   
 [no seguras](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed \(Instrucción\)](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)