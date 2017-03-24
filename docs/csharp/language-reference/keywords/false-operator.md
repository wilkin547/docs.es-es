---
title: "false (Operador, Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "false (operador, palabra clave) [C#]"
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# false (Operador, Referencia de C#)
Devuelve el valor [booleano](../../../csharp/language-reference/keywords/bool.md) `true` para indicar que un operando es `false`; de lo contrario, devuelve `false`.  
  
 En las versiones anteriores a C\# 2.0, los operadores `true` y `false` se utilizaban para crear tipos de valor que aceptan valores NULL definidos por el usuario compatibles con tipos como `SqlBool`.  Sin embargo, ahora este lenguaje proporciona compatibilidad integrada con los tipos de valor que aceptan valores NULL; además, debe utilizarlos siempre que sea posible, en lugar de sobrecargar los operadores `true` y `false`.  Para obtener más información, vea [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md).  
  
 Con los tipos booleanos que aceptan valores NULL, la expresión `a != b` no es necesariamente igual a `!(a == b)`, ya que uno o ambos valores pueden ser NULL.  Debe sobrecargar ambos operadores, `true` y `false`, por separado para controlar correctamente los valores NULL en la expresión.  En el ejemplo siguiente se muestra cómo sobrecargar y usar los operadores `true` y `false`.  
  
 [!code-cs[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/false-operator_1.cs)]  
  
 Un tipo que sobrecarga los operadores `true` y `false` puede utilizarse para la expresión de control en las instrucciones [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md) y [for](../../../csharp/language-reference/keywords/for.md) y en las [expresiones condicionales](../../../csharp/language-reference/operators/conditional-operator.md).  
  
 Si un tipo define el operador `false`, también debe definir el operador [true](../../../csharp/language-reference/keywords/true.md).  
  
 Un tipo no puede sobrecargar directamente los operadores lógicos condicionales [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) y [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md), pero al sobrecargar los operadores lógicos regulares y los operadores `true` y `false` se puede lograr un efecto equivalente.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)   
 [true](../../../csharp/language-reference/keywords/true.md)