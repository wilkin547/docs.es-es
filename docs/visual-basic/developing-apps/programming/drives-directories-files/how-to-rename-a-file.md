---
description: 'Más información acerca de: Procedimiento: para cambiar el nombre de un archivo en Visual Basic'
title: Procedimiento para cambiar el nombre de un archivo
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [Visual Basic], renaming files
- files [Visual Basic], renaming
ms.assetid: 0ea7e0c8-2cb2-4bf5-a00d-7b6e3c08a3bc
ms.openlocfilehash: cf182fa94befdfdcb1568052a0193d483670cf49
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797411"
---
# <a name="how-to-rename-a-file-in-visual-basic"></a>Cómo: Cambiar el nombre de un archivo en Visual Basic

Use el método `RenameFile` del objeto `My.Computer.FileSystem` para cambiar el nombre de un archivo proporcionando la ubicación actual, el nombre de archivo y el nombre de archivo nuevo. No se puede usar este método para mover un archivo. Use el método `MoveFile` para mover y cambiar el nombre del archivo.  
  
### <a name="to-rename-a-file"></a>Para cambiar el nombre de un archivo  
  
- Use el método `My.Computer.FileSystem.RenameFile` para cambiar el nombre de un archivo. En este ejemplo se cambia el nombre del archivo `Test.txt` por `SecondTest.txt`.  
  
     [!code-vb[VbVbcnMyFileSystem#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#9)]  
  
 Este ejemplo de código también está disponible como fragmento de código de IntelliSense. En el selector de fragmentos de código, el fragmento de código se encuentra en **Sistema de archivos - procesamiento de unidades, carpetas y archivos**. Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).  
  
## <a name="robust-programming"></a>Programación sólida  

 Las condiciones siguientes pueden provocar una excepción:  
  
- La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).  
  
- `newName` contiene información de ruta de acceso (<xref:System.ArgumentException>).  
  
- La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).  
  
- `newName` es `Nothing` o una cadena vacía (<xref:System.ArgumentNullException>).  
  
- El archivo de origen no es válido o no existe (<xref:System.IO.FileNotFoundException>).  
  
- Hay un archivo o directorio con el nombre especificado en `newName` (<xref:System.IO.IOException>).  
  
- La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).  
  
- Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).  
  
- El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).  
  
- El usuario no tiene el permiso necesario (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.RenameFile%2A>
- [Procedimiento para mover un archivo](how-to-move-a-file.md)
- [Creación, eliminación y movimiento de archivos y directorios](creating-deleting-and-moving-files-and-directories.md)
- [Procedimiento para crear una copia de un archivo en el mismo directorio](how-to-create-a-copy-of-a-file-in-the-same-directory.md)
- [Procedimiento para crear una copia de un archivo en otro directorio](how-to-create-a-copy-of-a-file-in-a-different-directory.md)
