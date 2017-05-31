---
title: "Cómo: Escribir texto en archivos en Visual Basic | Microsoft Docs"
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
- files, writing to
- text, writing to files
- writing to files
- examples [Visual Basic], text files
ms.assetid: 304956eb-530d-4df7-b48f-9b4d1f2581a0
caps.latest.revision: 19
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
ms.openlocfilehash: 8febfbb5d4fb9042f2d9153a81aa18bd279cf3dc
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-write-text-to-files-in-visual-basic"></a>Cómo: Escribir texto en archivos en Visual Basic
El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> se puede usar para escribir texto en archivos. Si el archivo especificado no existe, se crea.  
  
## <a name="procedure"></a>Procedimiento  
  
#### <a name="to-write-text-to-a-file"></a>Para escribir texto en un archivo  
  
-   Use el método `WriteAllText` para escribir el texto en un archivo, especificando el archivo y el texto que se va a escribir. Este ejemplo escribe la línea `"This is new text."` en el archivo denominado `test.txt`, anexando el texto al texto existente en el archivo.  
  
     [!code-vb[VbFileIOWrite#3](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files_1.vb)]  
  
#### <a name="to-write-a-series-of-strings-to-a-file"></a>Para escribir una serie de cadenas en un archivo  
  
-   Recorra en iteración la colección de cadenas. Use el método `WriteAllText` para escribir el texto en un archivo, especificando el archivo de destino, la cadena que se debe agregar y estableciendo `append` en `True`.  
  
     En este ejemplo se escriben los nombres de los archivos contenidos en el directorio `Documents and Settings` en `FileList.txt`, insertando un retorno de carro entre cada uno de ellos para una mejor legibilidad.  
  
     [!code-vb[VbFileIOWrite#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files_2.vb)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).  
  
-   La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).  
  
-   `File` señala a una ruta de acceso que no existe (<xref:System.IO.FileNotFoundException> o <xref:System.IO.DirectoryNotFoundException>).  
  
-   El archivo está en uso por otro proceso o hay un error de E/S (<xref:System.IO.IOException>).  
  
-   La ruta de acceso supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).  
  
-   Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).  
  
-   El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).  
  
-   El disco está lleno y se produce un error en la llamada a `WriteAllText` (<xref:System.IO.IOException>).  
  
 Si realiza una ejecución en un contexto de confianza parcial, el código podría desencadenar una excepción por falta de privilegios. Para obtener más información, vea [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8) (Aspectos básicos de seguridad de acceso del código).  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 [Leer de archivos de texto](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)
