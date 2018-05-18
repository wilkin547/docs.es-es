---
title: 'Cómo: Buscar subdirectorios con un modelo concreto en Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- pattern matching
- folders, finding
ms.assetid: c9265fd1-7483-4150-8b7f-ff642caa939d
ms.openlocfilehash: b3c80fccea06a48c78f37dc7d1c8dcc88e143de4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-find-subdirectories-with-a-specific-pattern-in-visual-basic"></a>Cómo: Buscar subdirectorios con un modelo concreto en Visual Basic
El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A> devuelve una colección de solo lectura de cadenas que representan los nombres de ruta de acceso de los subdirectorios de un directorio. Puede usar el parámetro `wildCards` para especificar un patrón concreto. Si quiere incluir el contenido de subdirectorios en la búsqueda, establezca el parámetro `searchType` en `SearchOption.SearchAllSubDirectories`.  
  
 Se devuelve una colección vacía si no se encuentra ningún directorio que coincida con el modelo especificado.  
  
### <a name="to-find-subdirectories-with-a-specific-pattern"></a>Para buscar subdirectorios con un modelo concreto  
  
-   Use el método `GetDirectories` y proporcione el nombre y ruta de acceso del directorio que quiera buscar. En el ejemplo siguiente se devuelven todos los directorios de la estructura de directorios que contienen la palabra "Logs" en su nombre y se agregan a `ListBox1`.  
  
     [!code-vb[VbVbcnFileAccess#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-find-subdirectories-with-a-specific-pattern_1.vb)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).  
  
-   La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).  
  
-   Uno (o más) de los caracteres comodín especificados es `Nothing`, una cadena vacía o contiene solo espacios (<xref:System.ArgumentNullException>).  
  
-   `directory` no existe (<xref:System.IO.DirectoryNotFoundException>).  
  
-   `directory` apunta a un archivo existente (<xref:System.IO.IOException>).  
  
-   La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).  
  
-   Un nombre de archivo o de carpeta de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).  
  
-   El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).  
  
-   El usuario no tiene los permisos necesarios (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A>  
 [Buscar archivos con un modelo concreto](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md)
