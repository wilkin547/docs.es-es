---
title: "C&#243;mo: Leer archivos binarios en Visual Basic | Microsoft Docs"
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
  - "archivos binarios, leer"
  - "E/S [Visual Basic], leer de archivos binarios"
  - "My.Computer.FileSystem (objeto), leer de archivos binarios"
  - "ReadAllBytes (método), leer de archivos binarios"
ms.assetid: d2b1269e-24b6-42e0-9414-ae708db282d8
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Leer archivos binarios en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

El objeto `My.Computer.FileSystem` proporciona el método `ReadAllBytes` para leer archivos binarios.  
  
### Para leer un archivo binario  
  
-   Utilice el método `ReadAllBytes`, que devuelve el contenido de un archivo como una matriz de bytes.  En este ejemplo se lee el archivo `C:/Documents and Settings/selfportrait.jpg`.  
  
     [!code-vb[VbVbcnMyFileSystem#78](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-binary-files_1.vb)]  
  
-   Para los archivos binarios grandes, puede utilizar el método <xref:System.IO.FileStream.Read%2A> del objeto <xref:System.IO.FileStream> para leer solo una cantidad especificada de contenido del archivo a la vez.  A continuación, puede limitar la cantidad de contenido del archivo que se carga en memoria para cada operación de lectura.  En el ejemplo de código siguiente se copia un archivo y se permite al llamador especificar la cantidad de contenido del archivo que se lee en memoria por cada operación de lectura.  
  
     [!code-vb[VbVbcnMyFileSystem#91](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-binary-files_2.vb)]  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar que se produzca una excepción:  
  
-   La ruta de acceso no es válida por una de las razones siguientes: es una cadena de longitud cero, sólo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo \(<xref:System.ArgumentException>\).  
  
-   La ruta de acceso no es válida porque es `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   El archivo no existe \(<xref:System.IO.FileNotFoundException>\).  
  
-   El archivo está en uso por otro proceso o hay un error de E\/S \(<xref:System.IO.IOException>\).  
  
-   La ruta de acceso supera la longitud máxima definida por el sistema \(<xref:System.IO.PathTooLongException>\).  
  
-   Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos \(:\) o tiene un formato no válido \(<xref:System.NotSupportedException>\).  
  
-   No hay suficiente memoria para escribir la cadena en el búfer \(<xref:System.OutOfMemoryException>\).  
  
-   El usuario no tiene los permisos necesarios para ver la ruta de acceso \(<xref:System.Security.SecurityException>\).  
  
 No tome ninguna decisión sobre el contenido del archivo basándose en su nombre.  Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente de Visual Basic.  
  
 Compruebe todas las entradas antes de utilizar los datos en la aplicación.  Puede que el contenido del archivo no sea el esperado y que los métodos que leen el archivo produzcan un error.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>   
 [Leer archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)   
 [Cómo: Leer archivos de texto con varios formatos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)   
 [Almacenar y leer datos en el Portapapeles](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md)