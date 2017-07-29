---
title: "Cómo: Copiar un directorio en otro directorio en Visual Basic"
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
- I/O [Visual Basic], copying directories
- I/O [Visual Basic], copying folders
- folders [Visual Basic], copying
- directories [Visual Basic], copying
ms.assetid: 2a370bd7-10ba-4219-afc4-4519d031eb6c
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7bcc7f924d26247b0d0ab30a9ea0fc6d6333b652
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-copy-a-directory-to-another-directory-in-visual-basic"></a>Cómo: Copiar un directorio en otro directorio en Visual Basic
Use el método <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A> para copiar un directorio en otro directorio. Este método copia el contenido del directorio además del propio directorio. Si el directorio de destino no existe, se creará. Si existe un directorio con el mismo nombre en la ubicación de destino y `overwrite` se establece en `False`, se combinará el contenido de los dos directorios. Puede especificar un nuevo nombre para el directorio durante la operación.  
  
 Al copiar archivos en un directorio, pueden iniciarse excepciones producidas por un archivo concreto, como un archivo existente durante una combinación mientras `overwrite` está establecido en `False`. Cuando estas excepciones se inician, se consolidan en una sola excepción, cuya propiedad `Data` contiene entradas en las que la ruta de acceso del archivo o directorio es la clave y el mensaje de excepción concreto está contenido en el valor correspondiente.  
  
### <a name="to-copy-a-directory-to-another-directory"></a>Para copiar un directorio en otro  
  
-   Use el método `CopyDirectory` y especifique los nombres de los directorios de origen y destino. En el ejemplo siguiente se copia el directorio denominado `TestDirectory1` en `TestDirectory2`, lo que sobrescribe los archivos existentes.  
  
     [!code-vb[VbVbcnMyFileSystem#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-a-directory-to-another-directory_1.vb)]  
  
     Este ejemplo de código también está disponible como fragmento de código de IntelliSense. En el selector de fragmentos de código, se encuentra en **Sistema de archivos - procesamiento de unidades, carpetas y archivos**. Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El nuevo nombre especificado para el directorio contiene un signo de dos puntos (:) o una barra diagonal (\ o /) (<xref:System.ArgumentException>).  
  
-   La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).  
  
-   La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).  
  
-   `destinationDirectoryName` es `Nothing` o una cadena vacía (<xref:System.ArgumentNullException>)  
  
-   El directorio de origen no existe (<xref:System.IO.DirectoryNotFoundException>).  
  
-   El directorio de origen es un directorio raíz (<xref:System.IO.IOException>).  
  
-   La ruta de acceso combinada apunta a un archivo existente (<xref:System.IO.IOException>).  
  
-   Las rutas de acceso de origen y destino son iguales (<xref:System.IO.IOException>).  
  
-   `ShowUI` se establece en `UIOption.AllDialogs` y el usuario cancela la operación o uno o más archivos del directorio no pueden copiarse (<xref:System.OperationCanceledException>).  
  
-   La operación es cíclica (<xref:System.InvalidOperationException>).  
  
-   La ruta de acceso contiene un signo de dos puntos (:) (<xref:System.NotSupportedException>).  
  
-   La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).  
  
-   Un nombre de archivo o de carpeta de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).  
  
-   El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).  
  
-   Un archivo de destino existe pero no se puede acceder a él (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A>   
 [How to: Find Subdirectories with a Specific Pattern](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)  (Cómo: Buscar subdirectorios con un modelo concreto en Visual Basic)  
 [Obtener la colección de archivos de un directorio](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)

