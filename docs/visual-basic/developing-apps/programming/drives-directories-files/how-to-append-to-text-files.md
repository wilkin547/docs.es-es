---
title: "C&#243;mo: Anexar a archivos de texto en Visual Basic | Microsoft Docs"
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
  - "E/S [Visual Basic], anexar a archivos"
  - "E/S [Visual Basic], My.Computer.FileSystem.WriteAllText (método)"
  - "E/S [Visual Basic], WriteAllText (método)"
ms.assetid: bbbd7fb5-f169-41a9-b53f-520ea9613913
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Anexar a archivos de texto en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> se puede utilizar para anexar a un archivo de texto especificando que el parámetro `append` se establece en `True`.  
  
### Para anexar a un archivo de texto  
  
-   Utilice el método `WriteAllText`, especificando el archivo de destino y la cadena que se va a anexar y estableciendo el parámetro `append` en `True`.  
  
     Este ejemplo escribe la cadena `"This is a test string."` en el archivo `Testfile.txt`.  
  
     [!code-vb[VbFileIOWrite#6](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-append-to-text-files_1.vb)]  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   La ruta de acceso no es válida por una de las razones siguientes: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo \(empieza por \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   La ruta de acceso no es válida porque es `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   `File` señala a una ruta de acceso que no existe \(<xref:System.IO.FileNotFoundException> o <xref:System.IO.DirectoryNotFoundException>\).  
  
-   El archivo está en uso por otro proceso o hay un error de E\/S \(<xref:System.IO.IOException>\).  
  
-   La ruta de acceso supera la longitud máxima definida por el sistema \(<xref:System.IO.PathTooLongException>\).  
  
-   Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos \(:\) o tiene un formato no válido \(<xref:System.NotSupportedException>\).  
  
-   El usuario no tiene los permisos necesarios para ver la ruta de acceso \(<xref:System.Security.SecurityException>\).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 [Escribir en archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)