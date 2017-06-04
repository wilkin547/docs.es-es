---
title: "Cómo: Crear un directorio en Visual Basic | Microsoft Docs"
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
- directories [Visual Basic], creating
- folders [Visual Basic], creating
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
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
ms.openlocfilehash: 81afe64204fda468f452f86171b15080f9c3d948
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-create-a-directory-in-visual-basic"></a>Cómo: Crear un directorio en Visual Basic
Use el método `CreateDirectory` del objeto `My.Computer.FileSystem` para crear directorios.  
  
 Si el directorio ya existe, no se produce ninguna excepción.  
  
### <a name="to-create-a-directory"></a>Para crear un directorio  
  
-   Use el método `CreateDirectory` especificando la ruta de acceso completa de la ubicación donde se debe crear el directorio. Este ejemplo crea el directorio `NewDirectory` en `C:\Documents and Settings\All Users\Documents`.  
  
     [!code-vb[VbVbcnMyFileSystem#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-directory_1.vb)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El nombre del directorio es incorrecto. Por ejemplo, contiene caracteres no válidos o solo tiene espacios en blanco (<xref:System.ArgumentException>).  
  
-   El directorio principal del directorio que se va a crear es de solo lectura (<xref:System.IO.IOException>).  
  
-   El nombre del directorio es `Nothing` (<xref:System.ArgumentNullException>).  
  
-   El nombre del directorio es demasiado largo (<xref:System.IO.PathTooLongException>).  
  
-   El nombre del directorio son dos puntos ":" (<xref:System.NotSupportedException>).  
  
-   El usuario no tiene permiso para crear el directorio (<xref:System.UnauthorizedAccessException>).  
  
-   El usuario no tiene permisos en una situación de confianza parcial (<xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A>   
 [Creación, eliminación y movimiento de archivos y directorios](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)
