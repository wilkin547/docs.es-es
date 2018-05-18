---
title: 'Cómo: Enumerar directorios y archivos'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4cd7b7542e5cf9352e965717368399dcf4a9ecd2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enumerate-directories-and-files"></a>Cómo: Enumerar directorios y archivos
Puede enumerar directorios y archivos utilizando métodos que devuelven una colección enumerable de cadenas de sus nombres. También puede utilizar métodos que devuelven una colección enumerable de objetos <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo> o <xref:System.IO.FileSystemInfo>. Las colecciones enumerables ofrecen mayor rendimiento que las matrices cuando se trabaja con colecciones grandes de directorios y archivos.  
  
 También puede utilizar colecciones enumerables obtenidas de estos métodos para suministrar el parámetro <xref:System.Collections.Generic.IEnumerable%601> para los constructores de clases de colecciones como la clase <xref:System.Collections.Generic.List%601>.  
  
 Si desea obtener solo los nombres de directorios o archivos, utilice los métodos de enumeración de la clase <xref:System.IO.Directory>. Si desea obtener otras propiedades de directorios o archivos, utilice las clases <xref:System.IO.DirectoryInfo> y <xref:System.IO.FileSystemInfo>.  
  
 En la tabla siguiente se proporciona una guía de los métodos que devuelven colecciones enumerables.  
  
|Para enumerar|Colección enumerable que se va a devolver|Método que se usa|  
|------------------|-------------------------------------|-------------------|  
|Directorios|Nombres de directorio|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||Información de directorio (<xref:System.IO.DirectoryInfo>)|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|Archivos|Nombres de archivo|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||Información del archivo (<xref:System.IO.FileInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|Información del sistema de archivos|Entradas del sistema de archivos|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||Información del sistema de archivos (<xref:System.IO.FileSystemInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 Aunque puede enumerar inmediatamente todos los archivos de los subdirectorios de un directorio principal mediante la opción de búsqueda <xref:System.IO.SearchOption.AllDirectories> proporcionada por la enumeración <xref:System.IO.SearchOption>, las excepciones de acceso no autorizado (<xref:System.UnauthorizedAccessException>) pueden dar lugar a que la enumeración esté incompleta. Si estas excepciones son posibles, puede detectarlas y continuar enumerando primero los directorios y luego los archivos.  
  
### <a name="to-enumerate-directory-names"></a>Para enumerar los nombres de directorio  
  
-   Use el método <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> para obtener una lista de los nombres de directorio de nivel superior en una ruta de acceso especificada.  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a>Para enumerar los nombres de archivo de un directorio y de subdirectorios  
  
-   Use el método <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> para buscar un directorio y (opcionalmente) sus subdirectorios y para obtener una lista de nombres de archivo que coincidan con un patrón de búsqueda especificado.  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a>Para enumerar una colección de objetos DirectoryInfo  
  
-   Use el método <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> para obtener una colección de los directorios de nivel superior.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a>Para enumerar una colección de objetos FileInfo en todos los directorios  
  
-   Use el método <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> para obtener una colección de archivos que coincidan con un patrón de búsqueda especificado en todos los directorios. En este ejemplo se enumeran primero los directorios de nivel superior para detectar las posibles excepciones de acceso no autorizado y luego se enumeran los archivos.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [E/S de archivos y secuencias](../../../docs/standard/io/index.md)
