---
title: "C&#243;mo: Enumerar directorios y archivos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "E/S [.NET Framework], enumerar directorios y archivos"
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
caps.latest.revision: 18
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 18
---
# C&#243;mo: Enumerar directorios y archivos
Puede enumerar directorios y archivos mediante los métodos que devuelven una colección enumerable de cadenas de sus nombres.  También puede utilizar métodos que devuelven una colección enumerable de objetos <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileSystemInfo> o <xref:System.IO.FileInfo>.  Las colecciones enumerables proporcionan un rendimiento mejor que las matrices al ejecutar las colecciones grandes de directorios y archivos.  
  
 Puede utilizar igualmente colecciones enumerables obtenidas de estos métodos para proporcionar el parámetro <xref:System.Collections.Generic.IEnumerable%601> a los constructores de clases de colección como la clase <xref:System.Collections.Generic.List%601>.  
  
 Si desea obtener solo los nombres de directorios o archivos, utilice los métodos de enumeración de la clase <xref:System.IO.Directory>.  Si desea obtener otras propiedades de directorios o archivos, utilice las clases <xref:System.IO.FileSystemInfo> y <xref:System.IO.DirectoryInfo>.  
  
 En la siguiente tabla se proporciona una guía de los métodos que devuelven colecciones enumerables.  
  
|Para enumerar|Colección enumerable que se devuelve|Método que se debe utilizar|  
|-------------------|------------------------------------------|---------------------------------|  
|Directorios|Nombres de directorio|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=fullName>|  
||Información de directorio \(<xref:System.IO.DirectoryInfo>\)|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=fullName>|  
|Archivos|Nombres de archivo|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=fullName>|  
||Información de archivo \(<xref:System.IO.FileInfo>\)|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=fullName>|  
|Información del sistema de archivos|Entradas del sistema de archivos|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=fullName>|  
||Información del sistema de archivos \(<xref:System.IO.FileSystemInfo>\)|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=fullName>|  
  
 Aunque puede enumerar inmediatamente todos los archivos de los subdirectorios de un directorio primario utilizando la opción de búsqueda de <xref:System.IO.SearchOption> proporcionada por la enumeración de <xref:System.IO.SearchOption> , las excepciones de acceso no autorizado \(<xref:System.UnauthorizedAccessException>\) pueden hacer la enumeración para ser incompletas.  Si estas excepciones son posibles, puede detectarlas y continuar enumerando primero los directorios y después los archivos.  
  
### Para enumerar los nombres de directorio  
  
-   Utilice el método <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=fullName> para obtener una lista de los nombres de directorio de nivel superior en una ruta de acceso especificada.  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### Para enumerar los nombres de archivo en un directorio y subdirectorios  
  
-   Utilice el método de <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=fullName> para buscar un directorio y \(opcionalmente\) sus subdirectorios, y para obtener una lista de nombres de archivo que coincidan con un modelo de búsqueda.  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### Para enumerar una colección de objetos DirectoryInfo  
  
-   Utilice el método <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=fullName> para obtener una colección de directorios de nivel superior.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### Para enumerar una colección de objetos FileInfo en todos los directorios  
  
-   Utilice el método <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=fullName> para obtener una colección de archivos que coincidan con un modelo de búsqueda especificado en todos los directorios.  En este ejemplo se enumeran primero los directorios de nivel superior para detectar las posibles excepciones de acceso no autorizado y luego, los archivos.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## Vea también  
 [E\/S de archivos y secuencias](../../../docs/standard/io/index.md)