---
description: 'Más información acerca de: Procedimiento: para obtener la colección de archivos de un directorio en Visual Basic'
title: Procedimiento para obtener la colección de archivos de un directorio
ms.date: 07/20/2015
helpviewer_keywords:
- folders, working with
- files [Visual Basic], accessing
ms.assetid: 6c8ba7e8-dd37-4853-92bf-762b67c98160
ms.openlocfilehash: bd799390c0ad0868f51387ba12e8612fe8948297
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797541"
---
# <a name="how-to-get-the-collection-of-files-in-a-directory-in-visual-basic"></a>Cómo: Obtener la colección de archivos de un directorio en Visual Basic

Las sobrecargas del método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=nameWithType> devuelven una colección de solo lectura de cadenas que representan los nombres de los archivos contenidos en un directorio:  
  
- Use la sobrecarga <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%28System.String%29> para realizar una búsqueda de archivos sencilla en un directorio concreto, sin buscar en los subdirectorios.  
  
- Use la sobrecarga <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles(System.String,Microsoft.VisualBasic.FileIO.SearchOption,System.String[])> para especificar más opciones de búsqueda. Puede usar el parámetro `wildCards` para especificar un patrón de búsqueda. Para incluir los subdirectorios en la búsqueda, establezca el parámetro `searchType` en <xref:Microsoft.VisualBasic.FileIO.SearchOption.SearchAllSubDirectories?displayProperty=nameWithType>.  
  
 Si no se encuentran archivos que coincidan con el patrón especificado, se devuelve una colección vacía.  
  
### <a name="to-list-files-in-a-directory"></a>Para enumerar los archivos de un directorio  
  
- Use una de las sobrecargas del método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=nameWithType> y proporcione el nombre y la ruta de acceso del directorio para buscar en el parámetro `directory`. En el siguiente ejemplo se devuelven todos los archivos contenidos en el directorio y se agregan a `ListBox1`.  
  
     [!code-vb[VbVbcnMyFileSystem#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#32)]  
  
## <a name="robust-programming"></a>Programación sólida  

 Las condiciones siguientes pueden provocar una excepción:  
  
- La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).  
  
- La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).  
  
- `directory` no existe (<xref:System.IO.DirectoryNotFoundException>).  
  
- `directory` apunta a un archivo existente (<xref:System.IO.IOException>).  
  
- La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).  
  
- Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).  
  
- El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).  
  
- El usuario no tiene los permisos necesarios (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A>
- [Procedimiento para buscar archivos con un patrón concreto](how-to-find-files-with-a-specific-pattern.md)
- [Procedimiento para buscar subdirectorios con un patrón concreto](how-to-find-subdirectories-with-a-specific-pattern.md)
