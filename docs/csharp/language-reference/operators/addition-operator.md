---
title: "Operador + (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "+_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "+ (operador) [C#]"
  - "operador de suma [C#]"
  - "operador de concatenación [C#]"
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# Operador + (Referencia de C#)
El operador `+` puede funcionar como operador unario o binario.  
  
## Comentarios  
 Los operadores unarios `+` se encuentran predefinidos para todos los tipos numéricos.  El resultado de una operación unaria `+` aplicada a un tipo numérico es simplemente el valor del operando.  
  
 Los operadores `+` binarios se encuentran predefinidos para los tipos numéricos y de cadena.  Para tipos numéricos, \+ calcula la suma de sus dos operandos.  Cuando al menos uno de los operandos es de tipo string, \+ concatena las representaciones de tipo string de los operandos.  
  
 Los tipos delegados también proporcionan un operador binario `+`, el cual realiza la concatenación de delegados.  
  
 Los tipos definidos por el usuario pueden sobrecargar los operadores unario `+` y binario `+`.  Las operaciones en tipos enteros se suelen permitir en enumeraciones.  Para obtener más información, vea [operador](../../../csharp/language-reference/keywords/operator.md).  
  
## Ejemplo  
 [!code-cs[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#28)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)   
 [operador](../../../csharp/language-reference/keywords/operator.md)