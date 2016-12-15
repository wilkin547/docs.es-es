---
title: "C&#243;mo: Implementar conversiones definidas por el usuario entre structs (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "conversiones definidas por el usuario [C#]"
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Implementar conversiones definidas por el usuario entre structs (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Este ejemplo define dos structs, `RomanNumeral` y `BinaryNumeral`, y muestra dos conversiones entre ellos.  
  
## Ejemplo  
 [!code-cs[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]  
  
## Programación eficaz  
  
-   En el ejemplo anterior, la instrucción:  
  
     [!code-cs[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]  
  
     realiza una conversión de un `RomanNumeral` a un `BinaryNumeral`.  Como no existe una conversión directa de `RomanNumeral` a `BinaryNumeral`, se utiliza una conversión explícita de un `RomanNumeral` a un `int`, y otra conversión explícita para convertir de un `int` a un `BinaryNumeral`.  
  
-   Además, la instrucción  
  
     [!code-cs[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]  
  
     realiza una conversión de un `BinaryNumeral` a un `RomanNumeral`.  Como `RomanNumeral` define una conversión implícita desde `BinaryNumeral`, no se requiere ninguna conversión explícita.  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Operadores de conversión](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)