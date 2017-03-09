---
title: "C&#243;mo: Mostrar argumentos de la l&#237;nea de comandos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "argumentos de la línea de comandos [C#], mostrar"
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# C&#243;mo: Mostrar argumentos de la l&#237;nea de comandos (Gu&#237;a de programaci&#243;n de C#)
Los argumentos proporcionados a una aplicación ejecutable en la línea de comandos son accesibles a través de un parámetro opcional de `Main`.  Los argumentos se proporcionan en forma de matriz de cadenas.  Cada elemento de la matriz contiene un argumento.  Se quita el espacio en blanco entre los argumentos.  Por ejemplo, considere estas invocaciones de la línea de comandos de una aplicación ejecutable ficticia:  
  
|Entrada en la línea de comandos|Matriz de cadenas pasadas a Main|  
|-------------------------------------|--------------------------------------|  
|**executable.exe a b c**|"a"<br /><br /> "b"<br /><br /> "c"|  
|**executable.exe one two**|"one"<br /><br /> "two"|  
|**executable.exe "one two" three**|"one two"<br /><br /> "three"|  
  
> [!NOTE]
>  Cuando se ejecuta una aplicación en Visual Studio, puede especificar argumentos de la línea de comandos en [Página Depuración, Diseñador de proyectos](/visual-studio/ide/reference/debug-page-project-designer).  
  
## Ejemplo  
 Este ejemplo muestra los argumentos de la línea de comandos pasados a una aplicación de línea de comandos.  El resultado mostrado es para la primera entrada de la tabla anterior.  
  
 [!code-cs[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/how-to-display-command-l_1.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Command\-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [Main\(\) y argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)   
 [Cómo: Obtener acceso a argumentos de la línea de comandos utilizando foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)   
 [Valores devueltos Main\(\)](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)