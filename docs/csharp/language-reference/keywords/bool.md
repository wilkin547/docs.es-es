---
title: "bool (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "bool_CSharpKeyword"
  - "bool"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "bool (palabra clave) [C#]"
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# bool (Referencia de C#)
La palabra clave `bool` es un alias de <xref:System.Boolean?displayProperty=fullName>.  Se utiliza para declarar variables que almacenan los valores booleanos, [true](../../../csharp/language-reference/keywords/true.md) y [false](../../../csharp/language-reference/keywords/false.md).  
  
> [!NOTE]
>  Si requiere una variable booleana que también puede tener un valor de `null`, utilice `bool?`.  Para obtener más información, vea [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md).  
  
## Literales  
 Puede asignar un valor booleano a una variable de tipo `bool`.  También puede asignar una expresión que se evalúe como `bool` a una variable de tipo `bool`.  
  
 [!code-cs[csrefKeywordsTypes#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_1.cs)]  
  
 El valor predeterminado de una variable `bool` es `false`.  El valor predeterminado de una variable `bool?` es `null`.  
  
## Conversiones  
 En C\+\+, un valor de tipo `bool` se puede convertir a un valor de tipo `int`; es decir, `false` equivale a cero y `true` equivale a valores distintos de cero.  En C\#, no es posible realizar la conversión del tipo `bool` a otros tipos o viceversa.  Por ejemplo, la instrucción `if` siguiente no es válida en C\#:  
  
 [!code-cs[csrefKeywordsTypes#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_2.cs)]  
  
 Para probar una variable de tipo `int`, hay que compararla explícitamente con un valor \(por ejemplo, cero\), como se indica a continuación:  
  
 [!code-cs[csrefKeywordsTypes#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_3.cs)]  
  
## Ejemplo  
 En este ejemplo, se escribe un carácter desde el teclado y el programa comprueba si se trata de una letra.  Si es una letra, comprueba si está en minúsculas o mayúsculas.  Estas comprobaciones se realizan con <xref:System.Char.IsLetter%2A> y <xref:System.Char.IsLower%2A>, que devuelven el tipo `bool`:  
  
 [!code-cs[csrefKeywordsTypes#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_4.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)