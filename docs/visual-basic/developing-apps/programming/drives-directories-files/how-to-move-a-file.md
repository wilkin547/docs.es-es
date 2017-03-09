---
title: "C&#243;mo: Mover un archivo en Visual Basic | Microsoft Docs"
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
  - "archivos, mover"
ms.assetid: 53a7457b-5815-41ad-b37d-28537c1fb77a
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# C&#243;mo: Mover un archivo en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El método `My.Computer.FileSystem.MoveFile` se puede usar para mover un archivo a otra carpeta. Si la estructura de destino no existe, se creará.  
  
### Para mover un archivo  
  
-   Use el método `MoveFile` para mover el archivo, y especifique el nombre y la ubicación de los archivos de origen y de destino. En este ejemplo se mueve el archivo denominado `test.txt` de `TestDir1` a `TestDir2`. Observe que el nombre del archivo de destino se especifica aunque coincida con el nombre del archivo de origen.  
  
     [!code-vb[VbVbcnMyFileSystem#24](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-move-a-file_1.vb)]  
  
### Para mover un archivo y cambiarle el nombre  
  
-   Use el método `MoveFile` para mover el archivo, y especifique el nombre y la ubicación del archivo de origen, la ubicación de destino y el nuevo nombre en la ubicación de destino. En este ejemplo se mueve el archivo denominado `test.txt` de `TestDir1` a `TestDir2` y su nombre se cambia a `nexttest.txt`.  
  
     [!code-vb[VbVbcnMyFileSystem#25](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-move-a-file_2.vb)]  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo \(empieza por \\\\.\\\) \(<xref:System.ArgumentException>\).  
  
-   La ruta de acceso no es válida porque es `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   `destinationFileName` es `Nothing` o una cadena vacía \(<xref:System.ArgumentNullException>\).  
  
-   El archivo de origen no es válido o no existe \(<xref:System.IO.FileNotFoundException>\).  
  
-   La ruta de acceso combinada apunta a un directorio existente, el archivo de destino existe y `overwrite` está establecido en `False`, un archivo del directorio de destino con el mismo nombre está en uso o el usuario no tiene permisos suficientes para acceder al archivo \(<xref:System.IO.IOException>\).  
  
-   Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos \(:\) o tiene un formato no válido \(<xref:System.NotSupportedException>\).  
  
-   `showUI` está establecido en `True`, `onUserCancel` está establecido en `ThrowException` y el usuario canceló la operación o se produjo un error de E\/S no especificado \(<xref:System.OperationCanceledException>\).  
  
-   La ruta supera la longitud máxima definida por el sistema \(<xref:System.IO.PathTooLongException>\).  
  
-   El usuario no tiene los permisos necesarios para ver la ruta de acceso \(<xref:System.Security.SecurityException>\).  
  
-   El usuario no tiene el permiso necesario \(<xref:System.UnauthorizedAccessException>\).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.MoveFile%2A>   
 [Cómo: Cambiar el nombre de un archivo](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)   
 [Cómo: Crear una copia de un archivo en un directorio diferente](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)   
 [Cómo: Analizar rutas de acceso a archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)