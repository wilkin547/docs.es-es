---
title: 'Cómo: Crear un directorio'
ms.date: 07/20/2015
helpviewer_keywords:
- directories [Visual Basic], creating
- folders [Visual Basic], creating
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
ms.openlocfilehash: 0da915054a2e38c778f15bc0b472fe9b02521189
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401672"
---
# <a name="how-to-create-a-directory-in-visual-basic"></a>Cómo: Crear un directorio en Visual Basic

Use el método `CreateDirectory` del objeto `My.Computer.FileSystem` para crear directorios.  
  
 Si el directorio ya existe, no se produce ninguna excepción.  
  
### <a name="to-create-a-directory"></a>Para crear un directorio  
  
- Use el método `CreateDirectory` especificando la ruta de acceso completa de la ubicación donde se debe crear el directorio. Este ejemplo crea el directorio `NewDirectory` en `C:\Documents and Settings\All Users\Documents`.  
  
     [!code-vb[VbVbcnMyFileSystem#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#2)]  
  
## <a name="robust-programming"></a>Programación sólida  

 Las condiciones siguientes pueden provocar una excepción:  
  
- El nombre del directorio es incorrecto. Por ejemplo, contiene caracteres no válidos o solo tiene espacios en blanco (<xref:System.ArgumentException>).  
  
- El directorio principal del directorio que se va a crear es de solo lectura (<xref:System.IO.IOException>).  
  
- El nombre del directorio es `Nothing` (<xref:System.ArgumentNullException>).  
  
- El nombre del directorio es demasiado largo (<xref:System.IO.PathTooLongException>).  
  
- El nombre del directorio son dos puntos ":" (<xref:System.NotSupportedException>).  
  
- El usuario no tiene permiso para crear el directorio (<xref:System.UnauthorizedAccessException>).  
  
- El usuario no tiene permisos en una situación de confianza parcial (<xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A>
- [Creación, eliminación y movimiento de archivos y directorios](creating-deleting-and-moving-files-and-directories.md)
