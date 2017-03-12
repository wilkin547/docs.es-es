---
title: "Conversiones de puntero (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "punteros [C#], conversiones"
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Conversiones de puntero (Gu&#237;a de programaci&#243;n de C#)
La tabla siguiente muestra las conversiones de puntero implícitas predefinidas.  Las conversiones implícitas se pueden dar en muchas ocasiones, incluidas la invocación a métodos y las instrucciones de asignación.  
  
## Conversiones de puntero implícitas  
  
|From|Para|  
|----------|----------|  
|Cualquier tipo de puntero.|void\*|  
|null|Cualquier tipo de puntero.|  
  
 La conversión de puntero explícita se utiliza para realizar conversiones para las que no existe conversión implícita utilizando una expresión de conversión de tipos.  La siguiente tabla muestra estas conversiones.  
  
## Conversiones de puntero explícitas  
  
|From|Para|  
|----------|----------|  
|Cualquier tipo de puntero.|Cualquier otro tipo de puntero|  
|sbyte, byte, short, ushort, int, uint, long o ulong|Cualquier tipo de puntero.|  
|Cualquier tipo de puntero.|sbyte, byte, short, ushort, int, uint, long o ulong|  
  
## Ejemplo  
 En el ejemplo siguiente, un puntero a `int` se convierte en un puntero a `byte`.  Observe que el puntero señala al byte direccionado más bajo de la variable.  Cuando incrementa sucesivamente el resultado, hasta el tamaño de `int` \(4 bytes\), puede mostrar los bytes restantes de la variable.  
  
 [!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers2.cs#3)]  
  
 [!code-cs[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers.cs#4)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Tipos](../../../csharp/language-reference/keywords/types.md)   
 [no seguras](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed \(Instrucción\)](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)