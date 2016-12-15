---
title: "C&#243;mo: Escribir en archivos binarios en Visual Basic | Microsoft Docs"
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
  - "archivos binarios, escribir en Visual Basic"
  - "archivos, acceso binario"
  - "WriteAllBytes (método)"
ms.assetid: 59fae125-de5b-4c96-883c-209f4a55112c
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Escribir en archivos binarios en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> escribe datos en un archivo binario.  Si el parámetro `append` es `True`, anexará los datos al archivo; de lo contrario se sobrescriben los datos existentes en el archivo.  
  
 Si la ruta de acceso especificada excepto el nombre de archivo no es válida, se producirá una excepción <xref:System.IO.DirectoryNotFoundException>.  Si la ruta de acceso es válida pero el archivo no existe, se creará el archivo.  
  
### Para escribir en un archivo binario  
  
-   Utilice el método `WriteAllBytes`, proporcionando la ruta de acceso del archivo, su nombre y los bytes que se deben escribir.  Este ejemplo anexa la matriz de datos `CustomerData` al archivo denominado `CollectedData.dat`.  
  
     [!code-vb[VbVbcnMyFileSystem#27](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-to-binary-files_1.vb)]  
  
## Programación eficaz  
 Las condiciones siguientes pueden crear una excepción:  
  
-   La ruta de acceso no es válida por uno de los siguientes motivos: es una cadena de longitud cero, contiene sólo espacios en blanco, o contiene caracteres no válidos.  \(<xref:System.ArgumentException>\).  
  
-   La ruta de acceso no es válida porque es `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   `File` señala a una ruta de acceso que no existe \(<xref:System.IO.FileNotFoundException> o <xref:System.IO.DirectoryNotFoundException>\).  
  
-   El archivo está en uso por otro proceso o hay un error de E\/S \(<xref:System.IO.IOException>\).  
  
-   La ruta de acceso supera la longitud máxima definida por el sistema \(<xref:System.IO.PathTooLongException>\).  
  
-   Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos \(:\) o tiene un formato no válido \(<xref:System.NotSupportedException>\).  
  
-   El usuario no tiene los permisos necesarios para ver la ruta de acceso \(<xref:System.Security.SecurityException>\).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>   
 [Cómo: Escribir texto en archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-write-text-to-files.md)