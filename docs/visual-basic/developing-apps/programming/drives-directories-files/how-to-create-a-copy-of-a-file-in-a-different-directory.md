---
title: 'Cómo: Crear una copia de un archivo en un directorio diferente'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: 88e2145c-d414-45a5-ad03-6f5d58ecca26
ms.openlocfilehash: 3b4b41e105d6bb6a17fbb688aa4718b33c23b9d6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401698"
---
# <a name="how-to-create-a-copy-of-a-file-in-a-different-directory-in-visual-basic"></a>Cómo: Crear una copia de un archivo en un directorio diferente en Visual Basic

El método `My.Computer.FileSystem.CopyFile` le permite copiar archivos. Sus parámetros proporcionan la capacidad de sobrescribir archivos existentes, cambiar el nombre al archivo, mostrar el progreso de la operación y permitir al usuario cancelar la operación.  
  
### <a name="to-copy-a-text-file-to-another-folder"></a>Para copiar un archivo de texto en otra carpeta  
  
- Use el método `CopyFile` para copiar un archivo, especificando un archivo de origen y el directorio de destino. El parámetro `overwrite` le permite especificar si se deben sobrescribir los archivos existentes. Los ejemplos de código siguientes muestran cómo usar `CopyFile`.  
  
     [!code-vb[VbFileIOMisc#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#24)]  
  
## <a name="robust-programming"></a>Programación sólida  

 Las condiciones siguientes pueden provocar que se produzca una excepción:  
  
- La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).  
  
- El sistema no pudo recuperar la ruta de acceso absoluta (<xref:System.ArgumentException>).  
  
- La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).  
  
- El archivo de origen no es válido o no existe (<xref:System.IO.FileNotFoundException>).  
  
- La ruta de acceso combinada apunta a un directorio existente (<xref:System.IO.IOException>).  
  
- El archivo de destino existe y `overwrite` está establecido en `False` (<xref:System.IO.IOException>).  
  
- El usuario no tiene permisos suficientes para acceder al archivo (<xref:System.IO.IOException>).  
  
- Hay un archivo en uso con el mismo nombre en la carpeta de destino (<xref:System.IO.IOException>).  
  
- Un nombre de archivo o de carpeta de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).  
  
- `ShowUI` está establecido en `True`, `onUserCancel` está establecido en `ThrowException` y el usuario ha cancelado la operación (<xref:System.OperationCanceledException>).  
  
- `ShowUI` está establecido en `True`, `onUserCancel` está establecido en `ThrowException` y se produce un error de E/S no especificado (<xref:System.OperationCanceledException>).  
  
- La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).  
  
- El usuario no tiene el permiso necesario (<xref:System.UnauthorizedAccessException>).  
  
- El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>
- <xref:Microsoft.VisualBasic.FileIO.UICancelOption>
- [Copiar archivos con un modelo específico en un directorio](how-to-copy-files-with-a-specific-pattern-to-a-directory.md)
- [Crear una copia de un archivo en el mismo directorio](how-to-create-a-copy-of-a-file-in-the-same-directory.md)
- [Copiar un directorio en otro directorio](how-to-copy-a-directory-to-another-directory.md)
- [Cambiar el nombre de un archivo](how-to-rename-a-file.md)
