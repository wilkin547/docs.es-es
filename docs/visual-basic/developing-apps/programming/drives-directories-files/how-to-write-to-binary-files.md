---
title: "Cómo: Escribir en archivos binarios en Visual Basic | Microsoft Docs"
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
- files, binary access
- WriteAllBytes method
- binary files, writing in Visual Basic
ms.assetid: 59fae125-de5b-4c96-883c-209f4a55112c
caps.latest.revision: 16
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
ms.openlocfilehash: 0d86e39b7150b4ae8fc4de0498b0b786c5669bb4
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-write-to-binary-files-in-visual-basic"></a>Cómo: Escribir en archivos binarios en Visual Basic
El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> escribe datos en un archivo binario. Si el parámetro `append` es `True`, anexará los datos al archivo; de lo contrario se sobrescriben los datos existentes en el archivo.  
  
 Si la ruta de acceso especificada excepto el nombre de archivo no es válida, se producirá una excepción <xref:System.IO.DirectoryNotFoundException>. Si la ruta de acceso es válida pero el archivo no existe, se creará el archivo.  
  
### <a name="to-write-to-a-binary-file"></a>Para escribir en un archivo binario  
  
-   Use el método `WriteAllBytes`, proporcionando la ruta de acceso del archivo, su nombre y los bytes que se deben escribir. En este ejemplo se anexa la matriz de datos `CustomerData` al archivo denominado `CollectedData.dat`.  
  
     [!code-vb[VbVbcnMyFileSystem#27](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-to-binary-files_1.vb)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden crear una excepción:  
  
-   La ruta de acceso no es válida por uno de los siguientes motivos: es una cadena de longitud cero, contiene solo espacios en blanco, o contiene caracteres no válidos. (<xref:System.ArgumentException>).  
  
-   La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).  
  
-   `File` señala a una ruta de acceso que no existe (<xref:System.IO.FileNotFoundException> o <xref:System.IO.DirectoryNotFoundException>).  
  
-   El archivo está en uso por otro proceso o hay un error de E/S (<xref:System.IO.IOException>).  
  
-   La ruta de acceso supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).  
  
-   Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).  
  
-   El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>   
 [Escribir texto en archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-write-text-to-files.md)
