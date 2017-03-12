---
title: "Operador ++ (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "++_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "++ (operador) [C#]"
  - "operador de incremento (++) [C#]"
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# Operador ++ (Referencia de C#)
El operador de incremento \(`++`\) incrementa su operando en 1. El operador de incremento puede aparecer antes o después de su operando: `++variable` y `variable++`.  
  
## Comentarios  
 La primera forma es una operación de incremento de prefijo. El resultado de la operación es el valor del operando después del incremento.  
  
 La segunda forma es una operación de incremento de postfijo. El resultado de la operación es el valor del operando antes del incremento.  
  
 Los tipos numéricos y de enumeración poseen operadores de incremento predefinidos. Los tipos definidos por el usuario pueden sobrecargar el operador `++`. Las operaciones de tipos enteros suelen estar permitidas en la enumeración.  
  
## Ejemplo  
 [!code-cs[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#3)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)