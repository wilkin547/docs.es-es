---
title: "Operadores de conversi&#243;n (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, operadores de conversión"
  - "operadores de conversión [C#]"
  - "operadores [C#], conversión"
  - "conversiones definidas por el usuario [C#]"
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# Operadores de conversi&#243;n (Gu&#237;a de programaci&#243;n de C#)
C\# permite a los programadores declarar conversiones de clases o structs para convertirlas en otras clases o structs o en tipos básicos.  Las conversiones se definen como operadores con el nombre del tipo al cual convierten.  El tipo contenedor debe ser el tipo del argumento que se va a convertir o el tipo del resultado de la conversión, pero no ambos.  
  
 [!code-cs[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
## Información general de operadores de conversión  
 Los operadores de conversión tienen las propiedades siguientes:  
  
-   Las conversiones declaradas como `implicit` se producen automáticamente cuando son necesarias.  
  
-   Las conversiones declaradas como `explicit` requieren que se llame a una conversión de tipos.  
  
-   Todas las conversiones se deben declarar como `static`.  
  
## Secciones relacionadas  
 Para obtener más información:  
  
-   [Utilizar operadores de conversión](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [Conversiones de tipos](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [Cómo: Implementar conversiones definidas por el usuario entre structs](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [explícita](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [implícita](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [static](../../../csharp/language-reference/keywords/static.md)  
  
## Vea también  
 <xref:System.Convert>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Conversiones explícitas definido por el usuario encadenadas en C\#](http://go.microsoft.com/fwlink/?LinkId=112384)