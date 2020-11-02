---
title: Procedimiento para enumerar directorios y archivos
description: Aprenda a enumerar directorios y archivos mediante colecciones enumerables, que pueden proporcionar un mejor rendimiento que las matrices en .NET.
ms.date: 12/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
ms.openlocfilehash: 7a757fc97fd934f02592264c3a495c3efc435fd5
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2020
ms.locfileid: "93187897"
---
# <a name="how-to-enumerate-directories-and-files"></a>Procedimiento para enumerar directorios y archivos
Las colecciones enumerables ofrecen mayor rendimiento que las matrices cuando se trabaja con colecciones grandes de directorios y archivos. Para enumerar directorios y archivos, use métodos que devuelvan una colección enumerable de nombres de directorio o archivo, o bien sus objetos <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo> o <xref:System.IO.FileSystemInfo>.  
  
Si quiere buscar y devolver solo los nombres de directorios o archivos, use los métodos de enumeración de la clase <xref:System.IO.Directory>. Si quiere buscar y devolver otras propiedades de directorios o archivos, use las clases <xref:System.IO.DirectoryInfo> y <xref:System.IO.FileSystemInfo>.  
  
También puede usar colecciones enumerables de métodos como el parámetro <xref:System.Collections.Generic.IEnumerable%601> para los constructores de clases de colecciones como <xref:System.Collections.Generic.List%601>.  
  
En la tabla siguiente se resumen los métodos que devuelven colecciones enumerables de archivos y directorios:  
  
|Para buscar y devolver|Método que se usa|  
|------------------|-------------------------------------|-------------------|  
|Nombres de directorio|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|Información de directorio (<xref:System.IO.DirectoryInfo>)|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|Nombres de archivo|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
|Información del archivo (<xref:System.IO.FileInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|Nombres de entrada de archivos del sistema|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
|Información de entrada del sistema de archivos (<xref:System.IO.FileSystemInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
|Nombres de archivos y directorios |<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  

> [!NOTE]
> Aunque puede enumerar inmediatamente todos los archivos de los subdirectorios de un directorio principal mediante la opción <xref:System.IO.SearchOption.AllDirectories> de la enumeración <xref:System.IO.SearchOption>, los errores <xref:System.UnauthorizedAccessException> pueden hacer que la enumeración esté incompleta. Puede detectar estas excepciones si enumera primero los directorios y luego los archivos.  
  
## <a name="examples-use-the-directory-class"></a>Ejemplos: Uso de la clase Directory  
  
En el ejemplo siguiente se usa el método <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> para obtener una lista de los nombres de directorio de nivel superior en una ruta de acceso especificada.  

[!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
[!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  

En el ejemplo siguiente se usa el método <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> para enumerar de forma recursiva todos los nombres de archivo de un directorio y los subdirectorios que coinciden con un patrón determinado. Después, se leen todas las líneas de todos los archivos y se muestran las líneas que contienen una cadena especificada, con sus nombres de archivo y rutas de acceso.

[!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
[!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
## <a name="examples-use-the-directoryinfo-class"></a>Ejemplos: Uso de la clase DirectoryInfo  
  
En el ejemplo siguiente se usa el método <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> para enumerar una colección de los directorios de nivel superior cuyo <xref:System.IO.FileSystemInfo.CreationTimeUtc> es anterior a un valor <xref:System.DateTime> determinado.  

[!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs)]
[!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb)]  
  
En el ejemplo siguiente se usa el método <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> para enumerar todos los archivos cuyo valor <xref:System.IO.FileInfo.Length> supera los 10 MB. En este ejemplo se enumeran primero los directorios de nivel superior, para detectar las posibles excepciones de acceso no autorizado, y luego se enumeran los archivos.  

[!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
[!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [E/S de archivos y secuencias](index.md)
