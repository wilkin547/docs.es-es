---
title: 'Cómo: Copiar un directorio en otro directorio'
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [Visual Basic], copying directories
- I/O [Visual Basic], copying folders
- folders [Visual Basic], copying
- directories [Visual Basic], copying
ms.assetid: 2a370bd7-10ba-4219-afc4-4519d031eb6c
ms.openlocfilehash: e28f50f6a812188ac7af801cea691818488bd6cd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401724"
---
# <a name="how-to-copy-a-directory-to-another-directory-in-visual-basic"></a>Cómo: Copiar un directorio en otro directorio en Visual Basic

Use el método <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A> para copiar un directorio en otro directorio. Este método copia el contenido del directorio además del propio directorio. Si el directorio de destino no existe, se creará. Si existe un directorio con el mismo nombre en la ubicación de destino y `overwrite` se establece en `False`, se combinará el contenido de los dos directorios. Puede especificar un nuevo nombre para el directorio durante la operación.

Al copiar archivos en un directorio, pueden iniciarse excepciones producidas por un archivo concreto, como un archivo existente durante una combinación mientras `overwrite` está establecido en `False`. Cuando estas excepciones se inician, se consolidan en una sola excepción, cuya propiedad `Data` contiene entradas en las que la ruta de acceso del archivo o directorio es la clave y el mensaje de excepción concreto está contenido en el valor correspondiente.

## <a name="to-copy-a-directory-to-another-directory"></a>Para copiar un directorio en otro

- Use el método `CopyDirectory` y especifique los nombres de los directorios de origen y destino. En el ejemplo siguiente se copia el directorio denominado `TestDirectory1` en `TestDirectory2`, lo que sobrescribe los archivos existentes.

    [!code-vb[VbVbcnMyFileSystem#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#16)]

    Este ejemplo de código también está disponible como fragmento de código de IntelliSense. En el selector de fragmentos de código, se encuentra en **Sistema de archivos - procesamiento de unidades, carpetas y archivos**. Para obtener más información, vea [Code Snippets](/visualstudio/ide/code-snippets).

## <a name="robust-programming"></a>Programación sólida

Las condiciones siguientes pueden provocar una excepción:

- El nuevo nombre especificado para el directorio contiene un signo de dos puntos (:) o una barra diagonal (\ o /) (<xref:System.ArgumentException>).

- La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).

- La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).

- `destinationDirectoryName` es `Nothing` o una cadena vacía (<xref:System.ArgumentNullException>)

- El directorio de origen no existe (<xref:System.IO.DirectoryNotFoundException>).

- El directorio de origen es un directorio raíz (<xref:System.IO.IOException>).

- La ruta de acceso combinada apunta a un archivo existente (<xref:System.IO.IOException>).

- Las rutas de acceso de origen y destino son iguales (<xref:System.IO.IOException>).

- `ShowUI` se establece en `UIOption.AllDialogs` y el usuario cancela la operación o uno o más archivos del directorio no pueden copiarse (<xref:System.OperationCanceledException>).

- La operación es cíclica (<xref:System.InvalidOperationException>).

- La ruta de acceso contiene un signo de dos puntos (:) (<xref:System.NotSupportedException>).

- La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).

- Un nombre de archivo o de carpeta de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).

- El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).

- Un archivo de destino existe pero no se puede acceder a él (<xref:System.UnauthorizedAccessException>).

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A>
- [Buscar subdirectorios con un modelo concreto](how-to-find-subdirectories-with-a-specific-pattern.md)
- [Obtener la colección de archivos de un directorio](how-to-get-the-collection-of-files-in-a-directory.md)
