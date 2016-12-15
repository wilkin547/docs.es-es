---
title: "C&#243;mo: Crear archivos o carpetas (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "crear archivos [C#]"
  - "crear carpetas [C#]"
  - "archivos [C#]"
  - "carpetas [C#]"
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Crear archivos o carpetas (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Puede crear mediante programación una carpeta en el equipo, crear una subcarpeta, crear un archivo en la subcarpeta y escribir datos en el archivo.  
  
## Ejemplo  
 [!code-cs[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-create-a-file-or-folder_1.cs)]  
  
 Si la carpeta existe ya, <xref:System.IO.Directory.CreateDirectory%2A> no hace nada y no se produce ninguna excepción.  Sin embargo, <xref:System.IO.File.Create%2A?displayProperty=fullName> reemplaza un archivo existente con un nuevo archivo.  El ejemplo utiliza una instrucción `if`\-`else` para evitar que un archivo existente se reemplace.  
  
 Si hace los cambios siguientes en el ejemplo, puede especificar resultados diferentes basándose en si ya existe un archivo con cierto nombre.  Si ese archivo no existe, el código crea uno.  Si existe ese archivo, el código anexa datos a ese archivo.  
  
-   Especifique un nombre de archivo no aleatorio.  
  
    ```c#  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
  
    ```  
  
-   Reemplace la instrucción `if`\-`else` por la instrucción `using` en el código siguiente.  
  
    ```c#  
    using (System.IO.FileStream fs = new System.IO.FileStream(pathString, FileMode.Append))   
    {  
        for (byte i = 0; i < 100; i++)  
        {  
            fs.WriteByte(i);  
        }  
    }  
  
    ```  
  
 Ejecute el ejemplo varias veces para comprobar que los datos se agregan al archivo cada vez.  
  
 Para obtener más valores `FileMode` que puede probar, vea <xref:System.IO.FileMode>.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El nombre de la carpeta es incorrecto.  Por ejemplo, contiene caracteres ilegales o está compuesto sólo por espacios en blanco \(clase <xref:System.ArgumentException>\).  Use la clase <xref:System.IO.Path> para crear nombres de ruta de acceso válidos.  
  
-   La carpeta principal o la carpeta que se va a crear es de sólo lectura \(clase <xref:System.IO.IOException>\).  
  
-   El nombre de la carpeta es `null` \(clase <xref:System.ArgumentNullException>\).  
  
-   El nombre de la carpeta es demasiado largo \(clase <xref:System.IO.PathTooLongException>\).  
  
-   El nombre de carpeta contiene sólo un signo de dos puntos, ":" \(clase <xref:System.IO.PathTooLongException>\).  
  
## Seguridad de .NET Framework  
 Una instancia de la clase <xref:System.Security.SecurityException> se puede producir en entornos de confianza parcial.  
  
 Si no tiene permiso para crear la carpeta, el ejemplo producirá una instancia de la clase <xref:System.UnauthorizedAccessException>.  
  
## Vea también  
 <xref:System.IO?displayProperty=fullName>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Registro y sistema de archivos](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)