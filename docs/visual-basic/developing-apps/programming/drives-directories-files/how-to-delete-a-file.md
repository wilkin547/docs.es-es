---
title: "C&#243;mo: Eliminar un archivo en Visual Basic | Microsoft Docs"
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
  - "Delete (método)"
  - "File (objeto)"
  - "archivos, eliminar"
  - "archivos, manipular"
ms.assetid: 4b721769-3e45-4be7-b7fe-b08dc4141b44
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Eliminar un archivo en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

El método `DeleteFile` del objeto `My.Computer.FileSystem` permite eliminar un archivo.  Entre las opciones que ofrece se encuentran: enviar el archivo eliminado a la **Papelera de reciclaje**, pedir al usuario que confirme la eliminación del archivo o qué hacer si el usuario cancela la operación.  
  
### Para eliminar un archivo de texto  
  
-   Utilice el método `DeleteFile` para eliminar el archivo.  El código siguiente muestra cómo eliminar el archivo denominado `test.txt`.  
  
     [!code-vb[VbVbcnMyFileSystem#22](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_1.vb)]  
  
### Para eliminar un archivo de texto y pedirle al usuario que confirme que se debe eliminar el archivo  
  
-   Utilice el método `DeleteFile` para eliminar el archivo, estableciendo `showUI` en `AllDialogs`.  El código siguiente muestra cómo eliminar el archivo denominado `test.txt` y permite al usuario confirmar la eliminación del archivo.  
  
     [!code-vb[VbFileIOMisc#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_2.vb)]  
  
### Para eliminar un archivo de texto y enviarlo a la Papelera de Reciclaje  
  
-   Utilice el método `DeleteFile` para eliminar el archivo, especificando `SendToRecycleBin` para el parámetro `recycle`.  El código siguiente muestra cómo eliminar el archivo denominado `test.txt` y enviarlo a la **Papelera de Reciclaje**.  
  
     [!code-vb[VbFileIOMisc#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_3.vb)]  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   La ruta de acceso no es válida por una de las razones siguientes: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo \(empieza por \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   La ruta de acceso no es válida porque es `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   La ruta de acceso supera la longitud máxima definida por el sistema \(<xref:System.IO.PathTooLongException>\).  
  
-   Un nombre de archivo o de carpeta en la ruta de acceso contiene dos puntos \(:\) o está en un formato no válido \(<xref:System.NotSupportedException>\).  
  
-   El archivo está en uso \(<xref:System.IO.IOException>\).  
  
-   El usuario no tiene los permisos necesarios para ver la ruta de acceso \(<xref:System.Security.SecurityException>\).  
  
-   El archivo no existe \(<xref:System.IO.FileNotFoundException>\).  
  
-   El usuario no tiene permiso para eliminar el archivo o el archivo es de sólo lectura \(<xref:System.UnauthorizedAccessException>\).  
  
-   Existe una situación de confianza parcial en la cual el usuario no tiene los permisos necesarios \(<xref:System.Security.SecurityException>\).  
  
-   El usuario ha cancelado la operación y el parámetro `onUserCancel` está establecido en `ThrowException` \(<xref:System.OperationCanceledException>\).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileIO.UICancelOption>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.UIOption>   
 <xref:Microsoft.VisualBasic.FileIO.RecycleOption>   
 [Cómo: Obtener la colección de archivos de un directorio](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)