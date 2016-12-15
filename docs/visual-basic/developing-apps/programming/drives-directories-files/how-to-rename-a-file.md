---
title: "C&#243;mo: Cambiar el nombre de un archivo en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "archivos, cambiar nombre"
  - "E/S [Visual Basic], cambiar el nombre de archivos"
ms.assetid: 0ea7e0c8-2cb2-4bf5-a00d-7b6e3c08a3bc
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Cambiar el nombre de un archivo en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Utilice el método `RenameFile` del objeto `My.Computer.FileSystem` para cambiar el nombre de un archivo proporcionando la ubicación actual, el nombre de archivo y el nuevo nombre de archivo.  Este método no se puede utilizar para mover archivos; utilice `MoveFile` para mover un archivo y cambiarle el nombre.  
  
### Para cambiar el nombre de un archivo  
  
-   Utilice el método `My.Computer.FileSystem.RenameFile` para cambiar el nombre de un archivo.  En este ejemplo se cambia el nombre del archivo `Test.txt` por `SecondTest.txt`.  
  
     [!code-vb[VbVbcnMyFileSystem#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-rename-a-file_1.vb)]  
  
 Este ejemplo de código también está disponible como fragmento de código de IntelliSense.  En el selector de fragmentos de código, el fragmento de código se encuentra en **Sistema de archivos \- Procesando unidades, carpetas y archivos**.  Para obtener más información, vea [Fragmentos de código](/visual-studio/ide/code-snippets).  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   La ruta de acceso no es válida por una de las razones siguientes: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo \(empieza por \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   `newName` contiene información de la ruta de acceso \(<xref:System.ArgumentException>\).  
  
-   La ruta de acceso no es válida porque es `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   `newName` es `Nothing` o una cadena vacía \(<xref:System.ArgumentNullException>\).  
  
-   El archivo de código fuente no es válido o no existe \(<xref:System.IO.FileNotFoundException>\).  
  
-   Ya hay un archivo o directorio con el nombre especificado en `newName` \(<xref:System.IO.IOException>\).  
  
-   La ruta de acceso supera la longitud máxima definida por el sistema \(<xref:System.IO.PathTooLongException>\).  
  
-   Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos \(:\) o tiene un formato no válido \(<xref:System.NotSupportedException>\).  
  
-   El usuario no tiene los permisos necesarios para ver la ruta de acceso \(<xref:System.Security.SecurityException>\).  
  
-   El usuario no tiene los permisos requeridos \(<xref:System.UnauthorizedAccessException>\).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.RenameFile%2A>   
 [Cómo: Mover archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-move-a-file.md)   
 [Crear, eliminar y mover archivos y directorios](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)   
 [Cómo: Crear una copia de un archivo en el mismo directorio](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-the-same-directory.md)   
 [Cómo: Crear una copia de un archivo en un directorio diferente](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)