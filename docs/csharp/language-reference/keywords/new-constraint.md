---
title: "Restricci&#243;n new (Referencia de C#) | Microsoft Docs"
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
  - "new (palabra clave de restricción) [C#]"
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Restricci&#243;n new (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La restricción `new` especifica que, en una declaración de clase genérica, cualquier argumento de tipo debe tener un constructor público sin parámetros.  Para utilizar la restricción new, el tipo no puede ser abstracto.  
  
## Ejemplo  
 Aplique la restricción `new` a un parámetro de tipo cuando una clase genérica cree nuevas instancias del tipo, como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]  
  
## Ejemplo  
 Cuando se utiliza la restricción `new()` con otras restricciones, se debe especificar en último lugar:  
  
 [!code-cs[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]  
  
 Para obtener más información, vea [Restricciones de tipos de parámetros](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 <xref:System.Collections.Generic>   
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [Genéricos](../../../csharp/programming-guide/generics/index.md)