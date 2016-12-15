---
title: "C&#243;mo: Copiar un directorio en otro directorio en Visual Basic | Microsoft Docs"
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
  - "directorios [Visual Basic], copiar"
  - "carpetas [Visual Basic], copiar"
  - "E/S [Visual Basic], copiar directorios"
  - "E/S [Visual Basic], copiar carpetas"
ms.assetid: 2a370bd7-10ba-4219-afc4-4519d031eb6c
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Copiar un directorio en otro directorio en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Utilice el método <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A> para copiar un directorio en otro directorio.  Este método copia el contenido del directorio así como el propio directorio.  Si el directorio de destino no existe, se creará.  Si existe un directorio con el mismo nombre en la ubicación de destino y `overwrite` está establecido en `False`, se combinará el contenido de los dos directorios.  Puede especificar un nuevo nombre para el directorio durante la operación.  
  
 Cuando se copian archivos dentro de un directorio, se pueden producir excepciones producidas por un archivo concreto, como que un archivo existe durante una combinación mientras `overwrite` está establecido en `False`.  Cuando se producen dichas excepciones, se consolidan en una excepción única, cuya propiedad `Data` contiene entradas en las que la ruta de acceso del archivo o del directorio es la clave y el mensaje de excepción concreto está contenido en el valor correspondiente.  
  
### Para copiar un directorio en otro directorio  
  
-   Utilice el método `CopyDirectory`, especificando los nombres de directorio de origen y de destino.  En el siguiente ejemplo se copia el directorio denominado `TestDirectory1` en `TestDirectory2`, sobrescribiendo los archivos existentes.  
  
     [!code-vb[VbVbcnMyFileSystem#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-a-directory-to-another-directory_1.vb)]  
  
     Este ejemplo de código también está disponible como fragmento de código de IntelliSense.  En el selector de fragmentos de código, se encuentra en **Sistema de archivos \- Procesando unidades, carpetas y archivos**.  Para obtener más información, vea [Fragmentos de código](/visual-studio/ide/code-snippets).  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El nuevo nombre especificado para el directorio contiene un signo de dos puntos \(:\) o una barra diagonal \(\\ o \/\) \(<xref:System.ArgumentException>\).  
  
-   La ruta de acceso no es válida por una de las razones siguientes: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo \(empieza por \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   La ruta de acceso no es válida porque es `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   `destinationDirectoryName` es `Nothing` o una cadena vacía \(<xref:System.ArgumentNullException>\).  
  
-   El directorio de origen no existe \(<xref:System.IO.DirectoryNotFoundException>\).  
  
-   El directorio de origen es un directorio raíz \(<xref:System.IO.IOException>\).  
  
-   La ruta de acceso combinada apunta a un archivo existente \(<xref:System.IO.IOException>\).  
  
-   La ruta de acceso de origen y la ruta de acceso de destino son iguales \(<xref:System.IO.IOException>\).  
  
-   `ShowUI` está establecido en `UIOption.AllDialogs` y el usuario cancela la operación o no se puede copiar uno o más archivos del directorio \(<xref:System.OperationCanceledException>\).  
  
-   La operación es cíclica \(<xref:System.InvalidOperationException>\).  
  
-   La ruta de acceso contiene un signo de dos puntos \(:\) \(<xref:System.NotSupportedException>\).  
  
-   La ruta de acceso supera la longitud máxima definida por el sistema \(<xref:System.IO.PathTooLongException>\).  
  
-   Un nombre de archivo o de carpeta en la ruta de acceso contiene dos puntos \(:\) o está en un formato no válido \(<xref:System.NotSupportedException>\).  
  
-   El usuario no tiene los permisos necesarios para ver la ruta de acceso \(<xref:System.Security.SecurityException>\).  
  
-   Existe un archivo de destino pero no se puede obtener acceso a él \(<xref:System.UnauthorizedAccessException>\).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A>   
 [Cómo: Buscar subdirectorios con un modelo concreto](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)   
 [Cómo: Obtener la colección de archivos de un directorio](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)