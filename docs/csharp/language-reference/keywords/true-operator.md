---
title: "true (Operador, Referencia de C#) | Microsoft Docs"
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
  - "true (operador) [C#]"
ms.assetid: acaba817-5da5-4364-b3b2-2e5c75ec1839
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# true (Operador, Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Devuelve el valor [booleano](../../../csharp/language-reference/keywords/bool.md) `true` para indicar que un operando es true; de lo contrario, devuelve `false`.  
  
 En las versiones anteriores a C\# 2.0, los operadores `true` y `false` se utilizaban para crear tipos de valor que aceptan valores NULL definidos por el usuario compatibles con tipos como `SqlBool`.  Sin embargo, ahora este lenguaje proporciona compatibilidad integrada con los tipos de valor que aceptan valores NULL; además, debe utilizarlos siempre que sea posible, en lugar de sobrecargar los operadores `true` y `false`.  Para obtener más información, vea [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md).  
  
 Con los tipos booleanos que aceptan valores NULL, la expresión `a != b` no es necesariamente igual a `!(a == b)`, ya que uno o ambos valores pueden ser NULL.  Debe sobrecargar ambos operadores, `true` y `false`, por separado para identificar correctamente los valores NULL en la expresión.  En el ejemplo siguiente se muestra cómo sobrecargar y usar los operadores `true` y `false`.  
  
 [!code-cs[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/true-operator_1.cs)]  
  
 Un tipo que sobrecarga los operadores `true` y `false` puede utilizarse para la expresión de control en las instrucciones [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md) y [for](../../../csharp/language-reference/keywords/for.md) y en las [expresiones condicionales](../../../csharp/language-reference/operators/conditional-operator.md).  
  
 Si un tipo define el operador `true`, también debe definir el operador [false](../../../csharp/language-reference/keywords/false.md).  
  
 Un tipo no puede sobrecargar directamente los operadores lógicos condicionales \([&&](../../../csharp/language-reference/operators/conditional-and-operator.md) y [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)\), pero al sobrecargar los operadores lógicos regulares y los operadores `true` y `false` se puede lograr un efecto equivalente.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)   
 [false](../../../csharp/language-reference/keywords/false.md)