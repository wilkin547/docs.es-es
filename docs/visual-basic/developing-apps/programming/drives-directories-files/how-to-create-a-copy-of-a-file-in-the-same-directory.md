---
description: 'Más información acerca de: Procedimiento: para crear una copia de un archivo en el mismo directorio en Visual Basic'
title: Procedimiento para crear una copia de un archivo en el mismo directorio
ms.date: 07/20/2015
f1_keywords:
- File.Copy
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: b2fdda86-e666-42c2-9706-9527e9fa68ff
ms.openlocfilehash: 27fecc22a9317dd45e663aa37884c6c1f1e36349
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797619"
---
# <a name="how-to-create-a-copy-of-a-file-in-the-same-directory-in-visual-basic"></a>Cómo: Crear una copia de un archivo en el mismo directorio en Visual Basic

Use el método `My.Computer.FileSystem.CopyFile` para copiar archivos. Con los parámetros puede sobrescribir archivos existentes, cambiar el nombre del archivo, mostrar el progreso de la operación y permitir al usuario cancelar la operación.  
  
### <a name="to-create-a-copy-of-a-file-in-the-same-folder"></a>Para crear una copia de un archivo en la misma carpeta  
  
- Use el método `CopyFile`, proporcionando el archivo de destino y la ubicación. En el ejemplo siguiente se crea una copia de `test.txt` llamada `test2.txt`.  
  
     [!code-vb[VbVbcnMyFileSystem#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#51)]  
  
### <a name="to-create-a-copy-of-a-file-in-the-same-folder-overwriting-existing-files"></a>Para crear una copia de un archivo en la misma carpeta, sobrescribiendo archivos existentes  
  
- Use el método `CopyFile`; indique el archivo de destino y la ubicación, y establezca `overwrite` en `True`. En el ejemplo siguiente se crea una copia de `test.txt` llamada `test2.txt` y sobrescribe cualquier archivo existente con dicho nombre.  
  
     [!code-vb[VbVbcnMyFileSystem#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#52)]  
  
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
- [Procedimiento para copiar archivos con un patrón específico en un directorio](how-to-copy-files-with-a-specific-pattern-to-a-directory.md)
- [Procedimiento para crear una copia de un archivo en otro directorio](how-to-create-a-copy-of-a-file-in-a-different-directory.md)
- [Procedimiento para copiar un directorio en otro](how-to-copy-a-directory-to-another-directory.md)
- [Procedimiento para cambiar el nombre de un archivo](how-to-rename-a-file.md)
