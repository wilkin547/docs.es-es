---
title: "C&#243;mo: Crear una copia de un archivo en un directorio diferente en Visual Basic | Microsoft Docs"
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
  - "CopyFile (método), copiar archivos en Visual Basic"
  - "archivos, copiar"
  - "E/S [Visual Basic], copiar archivos"
  - "My.Computer.FileSystem.CopyFile (método), copiar archivos [Visual Basic]"
ms.assetid: 88e2145c-d414-45a5-ad03-6f5d58ecca26
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# C&#243;mo: Crear una copia de un archivo en un directorio diferente en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El método `My.Computer.FileSystem.CopyFile` le permite copiar archivos.  Sus parámetros proporcionan la capacidad de sobrescribir archivos existentes, cambiar el nombre al archivo, mostrar el progreso de la operación y permitir al usuario cancelar la operación.  
  
### Para copiar un archivo de texto en otra carpeta  
  
-   Utilice el método `CopyFile` para copiar un archivo, especificando un archivo de código fuente y el directorio de destino.  El parámetro`overwrite` le permite especificar si se deben sobrescribir los archivos existentes.  Los ejemplos de código siguientes muestran cómo utilizar `CopyFile`.  
  
     [!code-vb[VbFileIOMisc#24](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-create-a-copy-of-_1_1.vb)]  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar que se produzca una excepción:  
  
-   La ruta de acceso no es válida por una de las razones siguientes: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo \(empieza por \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   El sistema no pudo recuperar la ruta de acceso absoluta \(<xref:System.ArgumentException>\).  
  
-   La ruta de acceso no es válida porque es `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   El archivo de código fuente no es válido o no existe \(<xref:System.IO.FileNotFoundException>\).  
  
-   La ruta de acceso combinada apunta a un directorio existente \(<xref:System.IO.IOException>\).  
  
-   El archivo de destino existe y `overwrite` está establecido en `False` \(<xref:System.IO.IOException>\).  
  
-   El usuario no tiene permisos suficientes para el acceso al archivo \(<xref:System.IO.IOException>\).  
  
-   Hay un archivo en uso con el mismo nombre en la carpeta de destino \(<xref:System.IO.IOException>\).  
  
-   Un nombre de archivo o de carpeta en la ruta de acceso contiene dos puntos \(:\) o está en un formato no válido \(<xref:System.NotSupportedException>\).  
  
-   `ShowUI` está establecido en `True`, `onUserCancel` está establecido en `ThrowException` y el usuario ha cancelado la operación \(<xref:System.OperationCanceledException>\).  
  
-   `ShowUI` está establecido en `True`, `onUserCancel` está establecido en `ThrowException` y se produce un error de E\/S no especificado \(<xref:System.OperationCanceledException>\).  
  
-   La ruta de acceso supera la longitud máxima definida por el sistema \(<xref:System.IO.PathTooLongException>\).  
  
-   El usuario no tiene los permisos requeridos \(<xref:System.UnauthorizedAccessException>\).  
  
-   El usuario no tiene los permisos necesarios para ver la ruta de acceso \(<xref:System.Security.SecurityException>\).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>   
 <xref:Microsoft.VisualBasic.FileIO.UICancelOption>   
 [Cómo: Copiar archivos con un modelo específico en un directorio](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-files-with-a-specific-pattern-to-a-directory.md)   
 [Cómo: Crear una copia de un archivo en el mismo directorio](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-the-same-directory.md)   
 [Cómo: Copiar un directorio en otro directorio](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-a-directory-to-another-directory.md)   
 [Cómo: Cambiar el nombre de un archivo](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)