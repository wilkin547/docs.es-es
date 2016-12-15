---
title: "Operador || (Referencia de C#) | Microsoft Docs"
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
  - "||_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "|| (operador) [C#]"
  - "|| (operador OR condicional) [C#]"
  - "OR (operador lógico) [C#]"
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
caps.latest.revision: 25
caps.handback.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operador || (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Condicional\- operador OR \(`||`\) realiza una disyunción lógica de sus operandos `bool` .  Si el primer operando se evalúa como `true`, el segundo operando no se evalúa.  Si el primer operando se evalúa como `false`, el segundo operador determina si OR la expresión de conjunto se evalúa como `true` o a `false`.  
  
## Comentarios  
 La operación  
  
```  
x || y  
```  
  
 se corresponde con la operación  
  
```  
x | y  
```  
  
 pero si `x` es `true`, `y` no se evalúa porque la operación OR es `true` independientemente del valor `y`.  Este concepto se conoce como evaluación “cortocircuitada”.  
  
 Condicional\- operador OR no se puede sobrecargar, pero las sobrecargas de los operadores lógicos regulares y operadores [true](../../../csharp/language-reference/keywords/true.md) y [false](../../../csharp/language-reference/keywords/false.md) , con algunas restricciones, también se consideran sobrecargas de los operadores lógicos condicionales.  
  
## Ejemplo  
 En los ejemplos siguientes, que utiliza `||` evalúa sólo el primer operando.  La expresión que utiliza `|`evalúa ambos operandos.  En el segundo ejemplo, una excepción en tiempo de ejecución se produce si se evalúan los dos operandos.  
  
 [!code-cs[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)