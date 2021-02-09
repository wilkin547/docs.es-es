---
description: 'Más información acerca de: Procedimiento: para buscar archivos con un modelo concreto en Visual Basic'
title: Procedimiento para buscar archivos con un patrón concreto
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], finding
- pattern matching
- patterns, matching
ms.assetid: 25e3b71d-b844-4293-9e4e-f06c5836b5cc
ms.openlocfilehash: 42266ad354e1ac8e3920663447e4d39fe7ad1b8f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797567"
---
# <a name="how-to-find-files-with-a-specific-pattern-in-visual-basic"></a>Cómo: Buscar archivos con un modelo concreto en Visual Basic

El método <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> devuelve una colección de solo lectura de cadenas que representan los nombres de ruta de acceso de los archivos. Puede usar el parámetro `wildCards` para especificar un patrón concreto. Si quiere incluir los subdirectorios en la búsqueda, establezca el parámetro `searchType` en `SearchOption.SearchAllSubDirectories`.  
  
 Si no se encuentran archivos que coincidan con el patrón especificado, se devuelve una colección vacía.  
  
> [!NOTE]
> Para obtener información sobre la devolución de una lista de archivos con la clase `DirectoryInfo` del espacio de nombres `System.IO`, consulte <xref:System.IO.DirectoryInfo.GetFiles%2A>.  
  
### <a name="to-find-files-with-a-specified-pattern"></a>Para buscar archivos con un modelo especificado  
  
- Use el método `GetFiles`, proporcionando el nombre y la ruta de acceso del directorio en el que quiere buscar y especificando el modelo. En el ejemplo siguiente se devuelven todos los archivos situados en el directorio que tienen la extensión `.dll` y los agrega a `ListBox1`.  
  
     [!code-vb[VbFileIOMisc#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#4)]  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  

 Las condiciones siguientes pueden provocar una excepción:  
  
- La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).  
  
- La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).  
  
- `directory` no existe (<xref:System.IO.DirectoryNotFoundException>).  
  
- `directory` apunta a un archivo existente (<xref:System.IO.IOException>).  
  
- La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).  
  
- Un nombre de archivo o de carpeta de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).  
  
- El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).  
  
- El usuario no tiene los permisos necesarios (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>
- [Procedimiento para buscar subdirectorios con un patrón concreto](how-to-find-subdirectories-with-a-specific-pattern.md)
- [Solución del problema: leer y escribir en archivos de texto](troubleshooting-reading-from-and-writing-to-text-files.md)
- [Procedimiento para obtener la colección de archivos de un directorio](how-to-get-the-collection-of-files-in-a-directory.md)
