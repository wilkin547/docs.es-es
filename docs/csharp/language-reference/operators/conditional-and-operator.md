---
title: "Operador &amp;&amp; (Referencia de C#) | Microsoft Docs"
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
  - "&&_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "&& (operador) [C#]"
  - "AND (operador lógico) [C#]"
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operador &amp;&amp; (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El operador AND condicional \(`&&`\) realiza una operación lógica AND de sus operandos de tipo `bool`, pero sólo evalúa su segundo operando si es necesario.  
  
## Comentarios  
 La operación  
  
```  
x && y  
```  
  
 se corresponde con la operación  
  
```  
x & y  
```  
  
 pero si `x`es `false`, `y` no se evalúa, porque el resultado de la operación de AND es `false` independientemente de cuál sea la configuración de `y` .  Esto se conoce como evaluación "cortocircuitada".  
  
 El operador AND condicional no se puede sobrecargar, pero las sobrecargas de los operadores lógicos normales y los operadores [true](../../../csharp/language-reference/keywords/true.md) y [false](../../../csharp/language-reference/keywords/false.md) también se consideran, con ciertas restricciones, sobrecargas de los operadores lógicos condicionales.  
  
## Ejemplo  
 En el ejemplo siguiente, la expresión condicional en la segunda instrucción de `if` evalúa sólo el primer operando porque el operando devuelve `false`.  
  
 [!code-cs[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)