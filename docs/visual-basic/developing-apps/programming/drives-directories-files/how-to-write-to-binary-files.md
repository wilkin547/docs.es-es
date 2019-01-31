---
title: Procedimiento para escribir en archivos binarios en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], binary access
- WriteAllBytes method [Visual Basic]
- binary files [Visual Basic], writing in Visual Basic
ms.assetid: 59fae125-de5b-4c96-883c-209f4a55112c
ms.openlocfilehash: 283c1c59d4bfa73f12ee0c9b772bf71c15a3b541
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676710"
---
# <a name="how-to-write-to-binary-files-in-visual-basic"></a>Procedimiento para escribir en archivos binarios en Visual Basic
El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> escribe datos en un archivo binario. Si el parámetro `append` es `True`, anexará los datos al archivo; de lo contrario se sobrescriben los datos existentes en el archivo.  
  
 Si la ruta de acceso especificada excepto el nombre de archivo no es válida, se producirá una excepción <xref:System.IO.DirectoryNotFoundException>. Si la ruta de acceso es válida pero el archivo no existe, se creará el archivo.  
  
### <a name="to-write-to-a-binary-file"></a>Para escribir en un archivo binario  
  
-   Use el método `WriteAllBytes`, proporcionando la ruta de acceso del archivo, su nombre y los bytes que se deben escribir. En este ejemplo se anexa la matriz de datos `CustomerData` al archivo denominado `CollectedData.dat`.  
  
     [!code-vb[VbVbcnMyFileSystem#27](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-to-binary-files_1.vb)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden crear una excepción:  
  
-   La ruta de acceso no es válida por uno de los siguientes motivos: es una cadena de longitud cero, contiene solo espacios en blanco, o contiene caracteres no válidos. (<xref:System.ArgumentException>).  
  
-   La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).  
  
-   `File` apunta a una ruta de acceso que no existe (<xref:System.IO.FileNotFoundException> o <xref:System.IO.DirectoryNotFoundException>).  
  
-   El archivo está en uso por otro proceso o hay un error de E/S (<xref:System.IO.IOException>).  
  
-   La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).  
  
-   Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).  
  
-   El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>
- [Cómo: Escribir texto en archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-write-text-to-files.md)
