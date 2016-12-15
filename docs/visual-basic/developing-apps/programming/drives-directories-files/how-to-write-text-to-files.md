---
title: "C&#243;mo: Escribir texto en archivos en Visual Basic | Microsoft Docs"
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
  - "ejemplos [Visual Basic], archivos de texto"
  - "archivos, escribir"
  - "texto, escribir en archivos"
  - "escribir en archivos"
ms.assetid: 304956eb-530d-4df7-b48f-9b4d1f2581a0
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Escribir texto en archivos en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> se puede utilizar para escribir texto en archivos.  Si el archivo especificado no existe, se crea.  
  
## Procedimiento  
  
#### Para escribir texto en un archivo.  
  
-   Utilice el método `WriteAllText` para escribir el texto en un archivo, especificando el archivo y el texto que se va a escribir.  Este ejemplo escribe la línea `"This is new text."` en el archivo llamado `test.txt`, anexando el texto al texto existente en el archivo.  
  
     [!code-vb[VbFileIOWrite#3](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files_1.vb)]  
  
#### Para escribir una serie de cadenas en un archivo  
  
-   Recorra en iteración la colección de cadenas.  Utilice el método `WriteAllText` para escribir el texto en un archivo, especificando el archivo de destino, la cadena que se debe agregar y estableciendo `append` en `True`.  
  
     Este ejemplo escribe los nombres de los archivos contenidos en el directorio `Documents and Settings` en el archivo `FileList.txt`, insertando un retorno de carro entre cada uno de ellos para una mejor legibilidad.  
  
     [!code-vb[VbFileIOWrite#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files_2.vb)]  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   La ruta de acceso no es válida por una de las razones siguientes: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo \(empieza por \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   La ruta de acceso no es válida porque es `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   `File` señala a una ruta de acceso que no existe \(<xref:System.IO.FileNotFoundException> o <xref:System.IO.DirectoryNotFoundException>\).  
  
-   El archivo está en uso por otro proceso o hay un error de E\/S \(<xref:System.IO.IOException>\).  
  
-   La ruta de acceso supera la longitud máxima definida por el sistema \(<xref:System.IO.PathTooLongException>\).  
  
-   Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos \(:\) o tiene un formato no válido \(<xref:System.NotSupportedException>\).  
  
-   El usuario no tiene los permisos necesarios para ver la ruta de acceso \(<xref:System.Security.SecurityException>\).  
  
-   El disco está lleno y se produce un error en la llamada a `WriteAllText` \(<xref:System.IO.IOException>\).  
  
 Si realiza una ejecución en un contexto de confianza parcial, el código podría desencadenar una excepción por falta de privilegios.  Para obtener más información, vea [Code Access Security Basics](../Topic/Code%20Access%20Security%20Basics.md).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 [Cómo: Leer de archivos de texto](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)