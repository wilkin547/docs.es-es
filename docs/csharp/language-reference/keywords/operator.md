---
title: "operator (Referencia de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "operator_CSharpKeyword"
  - "operator"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "operator (palabra clave) [C#]"
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# operator (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Utilice la palabra clave `operator` para sobrecargar un operador integrado o proporcionar una conversión definida por el usuario en una declaración de clase o struct.  
  
## Ejemplo  
 A continuación, se muestra una clase muy simplificada para números fraccionarios.  Sobrecarga los operadores \+ y \* para implementar la adición y multiplicación de números fraccionarios, y también proporciona un operador de conversión que convierte un tipo Fraction en un tipo double.  
  
 [!code-cs[csrefKeywordsConversion#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/operator_1.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [implícita](../../../csharp/language-reference/keywords/implicit.md)   
 [explícita](../../../csharp/language-reference/keywords/explicit.md)   
 [Cómo: Implementar conversiones definidas por el usuario entre structs](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)