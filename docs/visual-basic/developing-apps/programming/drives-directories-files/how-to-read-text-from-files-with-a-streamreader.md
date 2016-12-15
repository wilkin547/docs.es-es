---
title: "C&#243;mo: Leer texto de archivos con StreamReader (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "archivos, leer"
  - "leer archivos, texto"
  - "leer texto de archivos"
  - "texto, leer de archivos"
ms.assetid: 384033c6-18f9-4d59-9610-36371226558f
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Leer texto de archivos con StreamReader (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

El objeto `My.Computer.FileSystem` proporciona métodos para abrir un <xref:System.IO.TextReader> y un <xref:System.IO.TextWriter>.  Estos métodos, `OpenTextFileWriter` y `OpenTextFileReader`, son métodos avanzados que no aparecen en IntelliSense a menos que seleccione la ficha **Todas**.  
  
### Para leer una línea de un archivo con un lector de texto  
  
-   Utilice el método `OpenTextFileReader` para abrir el <xref:System.IO.TextReader>, especificando el archivo.  Este ejemplo abre el archivo denominado `testfile.txt`, lee una línea del mismo y la muestra en un cuadro de mensajes.  
  
     [!code-vb[VbFileIORead#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-text-from-files-with-a-streamreader_1.vb)]  
  
## Programación eficaz  
 El archivo que se lee debe ser un archivo de texto.  
  
 No tome ninguna decisión sobre el contenido del archivo basándose en su nombre.  Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente de Visual Basic.  
  
 Compruebe todas las entradas antes de utilizar los datos en la aplicación.  Puede que el contenido del archivo no sea el esperado y que los métodos que leen el archivo produzcan un error.  
  
## Seguridad de .NET Framework  
 Para leer un archivo, el ensamblado requiere un nivel de privilegios concedido por la clase <xref:System.Security.Permissions.FileIOPermission>.  Si realiza una ejecución en un contexto de confianza parcial, el código podría desencadenar una excepción por falta de privilegios.  Para obtener más información, vea [Code Access Security Basics](../Topic/Code%20Access%20Security%20Basics.md).  El usuario también necesita acceso al archivo.  Para obtener más información, vea [ACL Technology Overview](http://msdn.microsoft.com/es-es/06fbf66d-6f02-4378-b863-b2f12e349045).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:System.Windows.Forms.OpenFileDialog>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A>   
 [SaveFileDialog](../Topic/SaveFileDialog%20Component%20\(Windows%20Forms\).md)   
 [Leer archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)