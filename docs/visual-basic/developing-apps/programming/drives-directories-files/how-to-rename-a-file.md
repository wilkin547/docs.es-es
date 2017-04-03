---
title: "How to: Rename a File in Visual Basic (Cómo: Cambiar el nombre de un archivo en Visual Basic) | Microsoft Docs"
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
- I/O [Visual Basic], renaming files
- files, renaming
ms.assetid: 0ea7e0c8-2cb2-4bf5-a00d-7b6e3c08a3bc
caps.latest.revision: 21
author: stevehoag
ms.author: shoag
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a0a31353ce3ee0c48907f9550f6961260f92b64a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-rename-a-file-in-visual-basic"></a>Cómo: Cambiar el nombre de un archivo en Visual Basic
Use el método `RenameFile` del objeto `My.Computer.FileSystem` para cambiar el nombre de un archivo proporcionando la ubicación actual, el nombre de archivo y el nombre de archivo nuevo. No se puede usar este método para mover un archivo. Use el método `MoveFile` para mover y cambiar el nombre del archivo.  
  
### <a name="to-rename-a-file"></a>Para cambiar el nombre de un archivo  
  
-   Use el método `My.Computer.FileSystem.RenameFile` para cambiar el nombre de un archivo. En este ejemplo se cambia el nombre del archivo `Test.txt` por `SecondTest.txt`.  
  
     [!code-vb[VbVbcnMyFileSystem#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-rename-a-file_1.vb)]  
  
 Este ejemplo de código también está disponible como fragmento de código de IntelliSense. En el selector de fragmentos de código, el fragmento de código se encuentra en **Sistema de archivos - procesamiento de unidades, carpetas y archivos**. Para obtener más información, vea [Fragmentos de código](https://docs.microsoft.com/visualstudio/ide/code-snippets).  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).  
  
-   `newName` contiene información de ruta de acceso (<xref:System.ArgumentException>).  
  
-   La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).  
  
-   `newName` es `Nothing` o una cadena vacía (<xref:System.ArgumentNullException>).  
  
-   El archivo de origen no es válido o no existe (<xref:System.IO.FileNotFoundException>).  
  
-   Hay un archivo o directorio con el nombre especificado en `newName` (<xref:System.IO.IOException>).  
  
-   La ruta de acceso supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).  
  
-   Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).  
  
-   El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).  
  
-   El usuario no tiene el permiso necesario (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.RenameFile%2A>   
 [How to: Move a File](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-move-a-file.md)  (Cómo: Mover archivos)  
 [Creating, Deleting, and Moving Files and Directories](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)  (Creación, eliminación y movimiento de archivos y directorios)  
 [How to: Create a Copy of a File in the Same Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-the-same-directory.md)  (Cómo: Crear una copia de un archivo en el mismo directorio)  
 [Crear una copia de un archivo en un directorio diferente](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)
