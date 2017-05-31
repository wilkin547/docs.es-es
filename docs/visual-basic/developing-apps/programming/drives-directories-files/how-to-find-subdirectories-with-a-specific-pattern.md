---
title: "Cómo: Buscar subdirectorios con un modelo concreto en Visual Basic | Microsoft Docs"
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
- pattern matching
- folders, finding
ms.assetid: c9265fd1-7483-4150-8b7f-ff642caa939d
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
ms.openlocfilehash: 3fc7683c6629e2d94f3acb670810c6632efec094
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-find-subdirectories-with-a-specific-pattern-in-visual-basic"></a>Cómo: Buscar subdirectorios con un modelo concreto en Visual Basic
El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A> devuelve una colección de solo lectura de cadenas que representan los nombres de ruta de acceso a los subdirectorios en un directorio. Puede usar el parámetro `wildCards` para especificar un patrón concreto. Si quiere incluir el contenido de subdirectorios en la búsqueda, establezca el parámetro `searchType` en `SearchOption.SearchAllSubDirectories`.  
  
 Se devuelve una colección vacía si no se encuentra ningún directorio que coincida con el modelo especificado.  
  
### <a name="to-find-subdirectories-with-a-specific-pattern"></a>Para buscar subdirectorios con un modelo concreto  
  
-   Use el método `GetDirectories` y proporcione el nombre y ruta de acceso del directorio que quiera buscar. En el ejemplo siguiente se devuelven todos los directorios de la estructura de directorios que contienen la palabra "Logs" en su nombre y se agregan a `ListBox1`.  
  
     [!code-vb[VbVbcnFileAccess#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-find-subdirectories-with-a-specific-pattern_1.vb)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).  
  
-   La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).  
  
-   Uno o varios de los caracteres comodín especificados es `Nothing`, una cadena vacía o contiene solo espacios (<xref:System.ArgumentNullException>).  
  
-   `directory` no existe (<xref:System.IO.DirectoryNotFoundException>).  
  
-   `directory` apunta a un archivo existente (<xref:System.IO.IOException>).  
  
-   La ruta de acceso supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).  
  
-   Un nombre de archivo o de carpeta de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).  
  
-   El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).  
  
-   El usuario no tiene los permisos necesarios (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A>   
 [Buscar archivos con un modelo concreto](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md)
