---
title: "Hello World, su primer programa (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
f1_keywords: 
  - "cs.program"
  - "vs.csharp.startpage.firstapplication"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "ejemplos [C#], Hola a todos"
  - "ejemplo de Hola a todos [C#]"
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
caps.latest.revision: 39
caps.handback.revision: 39
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Hello World, su primer programa (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El siguiente procedimiento crea una versión de C\# del tradicional "Hello World\!".  El programa muestra la cadena `Hello World!`  
  
 Para obtener más ejemplos de conceptos de introducción, vea [Introducción a Visual C\# y Visual Basic](/visual-studio/ide/getting-started-with-visual-csharp-and-visual-basic).  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### Para crear y ejecutar una aplicación de consola  
  
1.  Inicie Visual Studio.  
  
2.  En la barra de menús, elija **Archivo**, **Nuevo**, **Proyecto**.  
  
     Aparece el cuadro de diálogo **Nuevo proyecto**.  
  
3.  Expanda **Instalado**, **Plantillas**, **Visual C\#** y, a continuación, elija **Aplicación de consola**.  
  
4.  En el cuadro **Nombre**, especifique un nombre para el proyecto y, a continuación, elija el botón **Aceptar**.  
  
     El nuevo proyecto aparecerá en el **Explorador de soluciones**.  
  
5.  Si Program.cs no está abierto en **Editor de código**, abra el menú contextual de **Program.cs** en **Explorador de soluciones** y, a continuación, elija **Ver código**.  
  
6.  Reemplace el contenido de Program.cs con el código siguiente.  
  
     [!code-cs[csProgGuide#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_1.cs)]  
  
7.  Elija la tecla F5 para ejecutar el proyecto.  Aparecerá una ventana del símbolo del sistema con la línea `Hello World!`  
  
 A continuación, se examinan las partes importantes de este programa.  
  
## Comentarios  
 La primera línea contiene un comentario.  Los caracteres `//` convierten el resto de la línea en un comentario.  
  
 [!code-cs[csProgGuide#32](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_2.cs)]  
  
 Un bloque de texto también se puede convertir en comentario si se incluye entre los caracteres `/*` y `*/`.  El ejemplo siguiente muestra esta opción.  
  
 [!code-cs[csProgGuide#33](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_3.cs)]  
  
## Método principal  
 Una aplicación de consola en C\# debe contener un método `Main`, en el cual se inicia y se termina el control.  Este método es donde se crean objetos y se ejecutan otros métodos.  
  
 El método `Main` es un método [static](../../../csharp/language-reference/keywords/static.md) que reside dentro de una clase o un struct.  En el ejemplo anterior de "Hello World\!", reside en una clase denominada `Hello`.  Puede declarar el método `Main` de una de las maneras siguientes:  
  
-   Puede devolver `void`.  
  
     [!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_4.cs)]  
  
-   También puede devolver un entero.  
  
     [!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_5.cs)]  
  
-   Puede utilizar argumentos con cualquiera de los tipos devueltos.  
  
     [!code-cs[csProgGuideMain#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_6.cs)]  
  
     O bien  
  
     [!code-cs[csProgGuideMain#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_7.cs)]  
  
 El parámetro del método `Main`, `args`, es una matriz de tipo `string` que contiene los argumentos de la línea de comandos utilizados para llamar al programa.  A diferencia de C\+\+, la matriz no incluye el nombre del archivo ejecutable \(exe\).  
  
 Para obtener más información sobre cómo utilizar argumentos de la línea de comandos, vea los ejemplos de [Main\(\) y argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md) y [Cómo: Crear y utilizar ensamblados mediante la línea de comandos](../Topic/How%20to:%20Create%20and%20Use%20Assemblies%20Using%20the%20Command%20Line%20\(C%23%20and%20Visual%20Basic\).md).  
  
 La llamada a <xref:System.Console.ReadKey%2A> al final del método `Main` impide que la ventana de la consola se cierre antes de que pueda leer el resultado al ejecutar el programa en modo de depuración presionando F5.  
  
## Entrada y salida  
 Los programas de C\# utilizan normalmente los servicios de entrada y salida que ofrece la biblioteca en tiempo de ejecución de .NET Framework.  La instrucción `System.Console.WriteLine("Hello World!");` utiliza el método <xref:System.Console.WriteLine%2A>.  Es uno de los métodos de salida de la clase <xref:System.Console> en la biblioteca en tiempo de ejecución.  Muestra el parámetro cadena en el flujo de salida estándar seguido por una nueva línea.  Otros métodos de <xref:System.Console> se utilizan para otras operaciones de entrada y salida.  Si incluye la directiva `using System;` al principio del programa, puede utilizar directamente las clases y métodos de <xref:System> sin escribir el nombre completo.  Por ejemplo, puede llamar a `Console.WriteLine` en lugar de llamar a `System.Console.WriteLine`:  
  
 [!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_8.cs)]  
  
 [!code-cs[csProgGuide#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_9.cs)]  
  
 Para obtener más información sobre métodos de entrada y salida, vea <xref:System.IO>.  
  
## Compilación y ejecución de línea de comandos  
 Puede compilar el programa "Hello World\!" usando la línea de comandos en lugar del entorno de desarrollo integrado \(IDE\) de Visual Studio.  
  
#### Para compilar y ejecutar desde un símbolo del sistema  
  
1.  Pegue el código del procedimiento anterior en cualquier editor de texto y, a continuación, guarde el archivo como archivo de texto.  Asigne al archivo el nombre `Hello.cs`.  Los archivos de código fuente de C\# utilizan la extensión `.cs`.  
  
2.  Realice uno de los pasos siguientes para abrir una ventana de símbolo del sistema:  
  
    -   En Windows 8, en la pantalla de **Iniciar**, busque `Símbolo del sistema para desarrolladores` y, a continuación, puntee o elija **Símbolo del sistema para desarrolladores de VS2012**.  
  
         Una ventana de símbolo del sistema del desarrollador aparece.  
  
    -   En Windows 7, abra el menú de **Iniciar**, expanda la carpeta para la versión actual de Visual Studio, abra el menú contextual para **Visual Studio Tools**y, a continuación, elija **Símbolo del sistema para desarrolladores de VS2012**.  
  
         Una ventana de símbolo del sistema del desarrollador aparece.  
  
    -   Habilite compilaciones de línea de comandos desde una ventana Símbolo del sistema estándar.  
  
         Vea [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).  
  
3.  En la ventana del símbolo del sistema, navegue hasta la carpeta que contiene su archivo `Hello.cs`.  
  
4.  Escriba el comando siguiente para compilar `Hello.cs`.  
  
     `csc Hello.cs`  
  
     Si el programa no tiene ningún error de compilación, se crea un archivo ejecutable denominado `Hello.exe`.  
  
5.  En la ventana de símbolo del sistema, especifique el siguiente comando para ejecutar el programa:  
  
     `Hello`  
  
 Para obtener más información sobre el compilador de C\# y sus opciones, vea [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md).  
  
## Capítulo destacado del libro  
 [Escribir un programa de C\#](http://go.microsoft.com/fwlink/?LinkId=221227) en [Iniciar Visual C\# 2010](http://go.microsoft.com/fwlink/?LinkId=221214)  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Dentro de un programa de C\#](../../../csharp/programming-guide/inside-a-program/index.md)   
 [Cadenas](../../../csharp/programming-guide/strings/index.md)   
 [\<paveover\>C\# Sample Applications](http://msdn.microsoft.com/es-es/9a9d7aaa-51d3-4224-b564-95409b0f3e15)   
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Main\(\) y argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)   
 [Introducción a Visual C\# y Visual Basic](/visual-studio/ide/getting-started-with-visual-csharp-and-visual-basic)