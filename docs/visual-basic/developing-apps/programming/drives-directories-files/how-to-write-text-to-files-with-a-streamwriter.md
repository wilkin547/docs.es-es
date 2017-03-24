---
title: "C&#243;mo: Escribir texto en archivos con un objeto StreamWriter en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "archivos, escribir"
  - "texto, escribir en archivos"
  - "escribir en archivos, StreamWriter"
ms.assetid: 99762e57-ef46-4dcc-8959-a8f79c22f067
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# C&#243;mo: Escribir texto en archivos con un objeto StreamWriter en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Este ejemplo abre un objeto <xref:System.IO.StreamWriter> con el método `My.Computer.FileSystem.OpenTextFileWriter` y lo utiliza para escribir una cadena en un archivo de texto con el método <xref:System.IO.TextWriter.WriteLine%2A> de la clase <xref:System.IO.StreamWriter>.  
  
## Ejemplo  
 [!code-vb[VbFileIOWrite#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-with-a-streamwriter_1.vb)]  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El archivo ya existe y es de sólo lectura \(<xref:System.IO.IOException>\).  
  
-   El disco está lleno \(<xref:System.IO.IOException>\).  
  
-   El nombre de la ruta de acceso es demasiado largo \(<xref:System.IO.PathTooLongException>\).  
  
## Seguridad de .NET Framework  
 En este ejemplo se crea un nuevo archivo, si es que aún no existe.  Si una aplicación necesita crear un archivo, precisará acceso `Create` para la carpeta correspondiente.  Sin embargo, si el archivo ya existe, la aplicación sólo precisará acceso `Write`, un privilegio menor.  Por tanto, siempre que sea posible, resulta más seguro crear el archivo durante la implementación y conceder sólo acceso `Read` para un único archivo, en lugar de acceso `Create` para una carpeta.  
  
## Vea también  
 <xref:System.IO.StreamWriter>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>   
 [Cómo: Leer de archivos de texto](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)   
 [Escribir en archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)