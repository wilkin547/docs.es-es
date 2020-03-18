---
title: 'Cómo: Eliminar un archivo'
ms.date: 07/20/2015
helpviewer_keywords:
- Delete method [Visual Basic]
- files [Visual Basic], deleting
- files [Visual Basic], manipulating
- File object
ms.assetid: 4b721769-3e45-4be7-b7fe-b08dc4141b44
ms.openlocfilehash: 57182f1a1d92b7fe954fd26b32c5e4b1107823ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74348780"
---
# <a name="how-to-delete-a-file-in-visual-basic"></a>Cómo: Eliminar un archivo en Visual Basic

El método `DeleteFile` del objeto `My.Computer.FileSystem` permite eliminar un archivo. Entre las opciones que ofrece se encuentran: enviar el archivo eliminado a la **Papelera de reciclaje**, pedir al usuario que confirme la eliminación del archivo o qué hacer si el usuario cancela la operación.  
  
### <a name="to-delete-a-text-file"></a>Para eliminar un archivo de texto  
  
- Use el método `DeleteFile` para eliminar el archivo. En el código siguiente se muestra cómo eliminar el archivo denominado `test.txt`.  
  
     [!code-vb[VbVbcnMyFileSystem#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#22)]  
  
### <a name="to-delete-a-text-file-and-ask-the-user-to-confirm-that-the-file-should-be-deleted"></a>Para eliminar un archivo de texto y pedirle al usuario que confirme que se debe eliminar el archivo  
  
- Use el método `DeleteFile` para eliminar el archivo, estableciendo `showUI` en `AllDialogs`. En el código siguiente se muestra cómo eliminar el archivo denominado `test.txt` y se permite al usuario confirmar la eliminación del archivo.  
  
     [!code-vb[VbFileIOMisc#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#9)]  
  
### <a name="to-delete-a-text-file-and-send-it-to-the-recycle-bin"></a>Para eliminar un archivo de texto y enviarlo a la Papelera de reciclaje  
  
- Use el método `DeleteFile` para eliminar el archivo, especificando `SendToRecycleBin` para el parámetro `recycle`. En el código siguiente se muestra cómo eliminar el archivo denominado `test.txt` y enviarlo a la **Papelera de reciclaje**.  
  
     [!code-vb[VbFileIOMisc#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#10)]  
  
## <a name="robust-programming"></a>Programación sólida  

 Las condiciones siguientes pueden provocar una excepción:  
  
- La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).  
  
- La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).  
  
- La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).  
  
- Un nombre de archivo o de carpeta de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).  
  
- El archivo está en uso (<xref:System.IO.IOException>).  
  
- El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).  
  
- El archivo no existe (<xref:System.IO.FileNotFoundException>).  
  
- El usuario no tiene permiso para eliminar el archivo o el archivo es de solo lectura (<xref:System.UnauthorizedAccessException>).  
  
- Existe una situación de confianza parcial en la que el usuario no tiene suficientes permisos (<xref:System.Security.SecurityException>).  
  
- El usuario canceló la operación y `onUserCancel` está establecido en `ThrowException` (<xref:System.OperationCanceledException>).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileIO.UICancelOption>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.UIOption>
- <xref:Microsoft.VisualBasic.FileIO.RecycleOption>
- [Obtener la colección de archivos de un directorio](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
