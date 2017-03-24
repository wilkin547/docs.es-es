---
title: "C&#243;mo: Obtener acceso a argumentos de la l&#237;nea de comandos utilizando Foreach (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "argumentos de la línea de comandos [C#]"
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# C&#243;mo: Obtener acceso a argumentos de la l&#237;nea de comandos utilizando Foreach (Gu&#237;a de programaci&#243;n de C#)
Otro enfoque para recorrer en iteración la matriz es utilizar la instrucción [foreach](../../../csharp/language-reference/keywords/foreach-in.md) como se muestra en este ejemplo.  La instrucción `foreach` se puede utilizar para recorrer en iteración una matriz, una clase de colección de .NET Framework o cualquier clase o struct que implemente la interfaz <xref:System.Collections.IEnumerable>.  
  
> [!NOTE]
>  Si ejecuta una aplicación en Visual Studio, puede especificar argumentos de la línea de comandos en [Página Depuración, Diseñador de proyectos](/visual-studio/ide/reference/debug-page-project-designer).  
  
## Ejemplo  
 En este ejemplo se muestra cómo imprimir los argumentos de la línea de comandos con `foreach`.  
  
 [!code-cs[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]  
  
 [!code-cs[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]  
  
## Vea también  
 <xref:System.Array>   
 <xref:System.Collections>   
 [Command\-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)   
 [Main\(\) y argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)   
 [Cómo: Mostrar argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [Valores devueltos Main\(\)](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)