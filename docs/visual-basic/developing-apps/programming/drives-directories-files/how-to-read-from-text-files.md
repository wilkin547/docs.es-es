---
title: "Cómo: Leer archivos de texto en Visual Basic | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- extended characters, reading
- reading text files
- reading data, text files
- examples [Visual Basic], reading text files
- text files, reading
ms.assetid: 735fe9d7-0f7a-4185-ba02-f35e580ec4b8
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4ea4f6ebfaf06a8b2b5d161d9986eebd28f50d5b
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-read-from-text-files-in-visual-basic"></a>Cómo: Leer archivos de texto en Visual Basic
El método <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.ReadAllText%2A> del objeto `My.Computer.FileSystem` permite leer de un archivo de texto. Se puede especificar la codificación del archivo si el contenido del mismo utiliza una codificación como ASCII o UTF-8.  
  
 Si está leyendo de un archivo que incluye caracteres extendidos, deberá especificar la codificación del archivo.  
  
> [!NOTE]
>  Para leer una única línea de texto de un archivo a la vez, utilice el método <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.OpenTextFileReader%2A> del objeto `My.Computer.FileSystem`. El método `OpenTextFileReader` devuelve un objeto <xref:System.IO.StreamReader>. Puede usar el método <xref:System.IO.StreamReader.ReadLine%2A> del objeto `StreamReader` para leer de un archivo una línea a la vez. Puede buscar el final del archivo con el método <xref:System.IO.StreamReader.EndOfStream%2A> del objeto `StreamReader`.  
  
### <a name="to-read-from-a-text-file"></a>Para leer de un archivo de texto  
  
-   Utilice el método `ReadAllText` del objeto `My.Computer.FileSystem` para leer el contenido de un archivo de texto en una cadena, proporcionando la ruta de acceso. El ejemplo siguiente lee el contenido del archivo test.txt, lo coloca en una cadena y, a continuación, lo muestra en un cuadro de mensaje.  
  
     [!code-vb[VbFileIORead#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files_1.vb)]  
  
### <a name="to-read-from-a-text-file-that-is-encoded"></a>Para leer de un archivo de texto que está codificado  
  
-   Utilice el método `ReadAllText` del objeto `My.Computer.FileSystem` para leer el contenido de un archivo de texto en una cadena, proporcionando la ruta de acceso y el tipo de codificación del archivo. El ejemplo siguiente lee el contenido del archivo UTF32 test.txt, lo coloca en una cadena y, a continuación, lo muestra en un cuadro de mensaje.  
  
     [!code-vb[VbFileIORead#3](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files_2.vb)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   La ruta de acceso no es válida por una de las razones siguientes: es una cadena de longitud cero, sólo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (<xref:System.ArgumentException>).  
  
-   La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).  
  
-   El archivo no existe (<xref:System.IO.FileNotFoundException>).  
  
-   El archivo está en uso por otro proceso o hay un error de E/S (<xref:System.IO.IOException>).  
  
-   La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).  
  
-   Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).  
  
-   No hay suficiente memoria para escribir la cadena en el búfer (<xref:System.OutOfMemoryException>).  
  
-   El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).  
  
 No tome ninguna decisión sobre el contenido del archivo basándose en su nombre. Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 Compruebe todas las entradas antes de utilizar los datos en la aplicación. Puede que el contenido del archivo no sea el esperado y que los métodos que leen el archivo produzcan un error.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>   
 [Reading from Files in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  (Leer archivos en Visual Basic)  
 [Cómo: Leer archivos de texto delimitados por comas](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)   
 [Cómo: Leer archivos de texto de ancho fijo](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)   
 [Cómo: Leer archivos de texto con varios formatos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)   
 [Solución de problemas: Leer y escribir en archivos de texto](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [Tutorial: Manipulación de archivos y directorios en Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)   
 [Codificaciones de archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)
