---
title: "C&#243;mo: Obtener acceso a un miembro con un puntero (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "punteros [C#], acceso a miembros"
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# C&#243;mo: Obtener acceso a un miembro con un puntero (Gu&#237;a de programaci&#243;n de C#)
Para tener acceso a un miembro de un struct que se declara en un contexto no seguro, puede utilizar el operador de acceso a miembros, como se muestra en el ejemplo siguiente en el que `p` es un puntero a una [struct](../../../csharp/language-reference/keywords/struct.md) que contiene un miembro `x`.  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## Ejemplo  
 En este ejemplo, se declara una [struct](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, que contiene dos coordenadas `x` e `y` y se crean instancias de la misma.  Utilizando el operador de acceso a miembros `->` y un puntero a la instancia `home`, se asignan valores a `x` e `y`.  
  
> [!NOTE]
>  Observe que la expresión `p->x` es equivalente a la expresión `(*p).x` y se puede obtener el mismo resultado utilizando cualquiera de las dos expresiones.  
  
 [!code-cs[csProgGuidePointers#9](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_1.cs)]  
  
 [!code-cs[csProgGuidePointers#10](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_2.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Tipos](../../../csharp/language-reference/keywords/types.md)   
 [no seguras](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed \(Instrucción\)](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)