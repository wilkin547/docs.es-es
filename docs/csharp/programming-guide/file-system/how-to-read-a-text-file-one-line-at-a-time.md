---
title: "C&#243;mo: Leer un archivo de texto l&#237;nea a l&#237;nea (Visual C#) | | Microsoft Docs"
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
  - "leer archivos de texto, línea a línea"
  - "ReadLine (método) [C#]"
  - "archivos de texto [C#]"
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Leer un archivo de texto l&#237;nea a l&#237;nea (Visual C#) |
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Este ejemplo lee el contenido de un archivo de texto, línea a línea, y lo almacena en una cadena mediante el método `ReadLine` de la clase `StreamReader`.  Cada línea de texto se almacena en la cadena `line` y se muestra en pantalla.  
  
## Ejemplo  
  
```  
int counter = 0;  
string line;  
  
// Read the file and display it line by line.  
System.IO.StreamReader file =   
    new System.IO.StreamReader(@"c:\test.txt");  
while((line = file.ReadLine()) != null)  
{  
    System.Console.WriteLine (line);  
    counter++;  
}  
  
file.Close();  
System.Console.WriteLine("There were {0} lines.", counter);  
// Suspend the screen.  
System.Console.ReadLine();  
```  
  
## Compilar el código  
 Copie el código y péguelo en el método `Main` de una aplicación de consola.  
  
 Reemplace `"c:\test.txt"` por el nombre del archivo.  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   Puede que el archivo no exista.  
  
## Seguridad de .NET Framework  
 No tome ninguna decisión sobre el contenido del archivo basándose en su nombre.  Por ejemplo, el archivo `myFile.cs` podría no ser un archivo de código fuente C\#.  
  
## Vea también  
 <xref:System.IO?displayProperty=fullName>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Registro y sistema de archivos](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)