---
title: "Cómo: Obtener la colección de archivos de un directorio en Visual Basic | Microsoft Docs"
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
- folders, working with
- files, accessing
ms.assetid: 6c8ba7e8-dd37-4853-92bf-762b67c98160
caps.latest.revision: 23
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d5b36baee302db0214844e0553473a05603090f1
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-get-the-collection-of-files-in-a-directory-in-visual-basic"></a>Cómo: Obtener la colección de archivos de un directorio en Visual Basic
Las sobrecargas del método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName> devuelven una colección de cadenas de solo lectura que representan los nombres de los archivos de un directorio:  
  
-   Use la sobrecarga <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%28System.String%29> para una simple búsqueda de archivos en un directorio específico, sin buscar en los subdirectorios.  
  
-   Use la sobrecarga <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles(System.String,Microsoft.VisualBasic.FileIO.SearchOption,System.String[])> para especificar opciones adicionales para la búsqueda. Puede usar el parámetro `wildCards` para especificar un patrón de búsqueda. Para incluir subdirectorios en la búsqueda, establezca el parámetro `searchType` en <xref:Microsoft.VisualBasic.FileIO.SearchOption?displayProperty=fullName>.  
  
 Si no se encuentran archivos que coincidan con el patrón especificado, se devuelve una colección vacía.  
  
### <a name="to-list-files-in-a-directory"></a>Para enumerar los archivos de un directorio  
  
-   Use una de las sobrecargas del método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName> proporcionando el nombre y la ruta de acceso del directorio que se debe buscar en el parámetro `directory`. En el siguiente ejemplo se devuelven todos los archivos contenidos en el directorio y se agregan a `ListBox1`.  
  
     [!code-vb[VbVbcnMyFileSystem#32](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-get-the-collection-of-files-in-a-directory_1.vb)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).  
  
-   La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).  
  
-   `directory` no existe (<xref:System.IO.DirectoryNotFoundException>).  
  
-   `directory` apunta a un archivo existente (<xref:System.IO.IOException>).  
  
-   La ruta de acceso supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).  
  
-   Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).  
  
-   El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).  
  
-   El usuario no tiene los permisos necesarios (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A>   
 [Buscar archivos con un modelo concreto](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md)   
 [Buscar subdirectorios con un modelo concreto](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)

