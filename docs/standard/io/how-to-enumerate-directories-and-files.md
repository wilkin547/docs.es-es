---
title: "Cómo: Enumerar directorios y archivos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: caf9bdec017a5466269ff7fe97be4d0243035b4a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enumerate-directories-and-files"></a>Cómo: Enumerar directorios y archivos
Puede enumerar directorios y archivos utilizando métodos que devuelven una colección enumerable de cadenas de sus nombres. También puede utilizar métodos que devuelven una colección enumerable de <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, o <xref:System.IO.FileSystemInfo> objetos. Colecciones enumerables proporcionan un mejor rendimiento que las matrices cuando se trabaja con grandes conjuntos de archivos y directorios.  
  
 También puede utilizar colecciones enumerables obtenidas de estos métodos para suministrar la <xref:System.Collections.Generic.IEnumerable%601> parámetro constructores de colección de clases como la <xref:System.Collections.Generic.List%601> clase.  
  
 Si desea obtener solo los nombres de directorios o archivos, utilice los métodos de enumeración de la <xref:System.IO.Directory> clase. Si desea obtener otras propiedades de directorios o archivos, utilice la <xref:System.IO.DirectoryInfo> y <xref:System.IO.FileSystemInfo> clases.  
  
 En la tabla siguiente proporciona a una guía para los métodos que devuelven colecciones enumerables.  
  
|Para enumerar|Colección enumerable que se va a devolver|Método que se usa|  
|------------------|-------------------------------------|-------------------|  
|Directorios|Nombres de directorio|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||Información del directorio (<xref:System.IO.DirectoryInfo>)|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|Archivos|Nombres de archivo|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||Archivo de información (<xref:System.IO.FileInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|Información del sistema de archivos|Entradas del sistema de archivos|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||Información del sistema de archivos (<xref:System.IO.FileSystemInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 Aunque puede enumerar inmediatamente todos los archivos en los subdirectorios de un directorio primario usando el <xref:System.IO.SearchOption.AllDirectories> Buscar opción proporcionada por el <xref:System.IO.SearchOption> enumeración, las excepciones de acceso no autorizado (<xref:System.UnauthorizedAccessException>) puede provocar la enumeración estar incompletos. Si estas excepciones son posibles, puede detectarlas y continuar enumerando primero los directorios y, a continuación, enumerar los archivos.  
  
### <a name="to-enumerate-directory-names"></a>Para enumerar los nombres de directorio  
  
-   Use la <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> método para obtener una lista de los nombres de directorio de nivel superior en una ruta de acceso especificada.  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a>Para enumerar los nombres de archivo en un directorio y subdirectorios  
  
-   Use la <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> método para buscar un directorio y (opcionalmente) en sus subdirectorios y para obtener una lista de nombres de archivo que coinciden con un patrón de búsqueda especificado.  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a>Enumerar una colección de objetos DirectoryInfo  
  
-   Use la <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> método para obtener una colección de los directorios de nivel superior.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a>Enumerar una colección de objetos FileInfo en todos los directorios  
  
-   Use la <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> método para obtener una colección de archivos que coinciden con un patrón de búsqueda especificado en todos los directorios. Este ejemplo enumera primero los directorios de nivel superior para detectar las excepciones de posibles accesos no autorizados y, a continuación, enumera los archivos.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [E/S de archivos y secuencias](../../../docs/standard/io/index.md)
