---
title: "C&#243;mo: Comprimir y extraer archivos | Microsoft Docs"
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
  - "E/S [.NET Framework], compresión"
  - "compresión"
  - "comprimir archivos"
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
caps.latest.revision: 19
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 19
---
# C&#243;mo: Comprimir y extraer archivos
El espacio de nombres <xref:System.IO.Compression> contiene los siguientes tipos para comprimir y descomprimir los archivos y las secuencias.  También puede utilizar estos tipos para leer y modificar el contenido de un archivo comprimido:  
  
-   <xref:System.IO.Compression.ZipFile>  
  
-   <xref:System.IO.Compression.ZipArchive>  
  
-   <xref:System.IO.Compression.ZipArchiveEntry>  
  
-   <xref:System.IO.Compression.DeflateStream>  
  
-   <xref:System.IO.Compression.GZipStream>  
  
 La los ejemplos siguientes se muestra algunas de las funciones que se pueden realizar al trabajar con archivos comprimidos.  
  
## Ejemplo  
 Este ejemplo muestra cómo crear y extraer un archivo comprimido que tengan una extensión de nombre de archivo .zip mediante la clase de <xref:System.IO.Compression.ZipFile> .  Comprime el contenido de una carpeta en un nuevo archivo .zip y luego extrae el contenido a una nueva carpeta.  Use la clase de <xref:System.IO.Compression.ZipFile> , debe hacer referencia al ensamblado de `System.IO.Compression.FileSystem` en el proyecto.  
  
 [!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]  
  
## Ejemplo  
 El ejemplo siguiente se muestra cómo recorrer en iteración del contenido de un archivo .zip y archivos de fragmento que tienen la extensión .txt.  Utiliza la clase de <xref:System.IO.Compression.ZipArchive> para tener acceso a un archivo .zip, y la clase de <xref:System.IO.Compression.ZipArchiveEntry> inspeccionar las entradas individuales en el archivo comprimido.  Utiliza un método de extensión \(<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>\) para el objeto de <xref:System.IO.Compression.ZipArchiveEntry> .  El método de extensión está disponible en la clase de <xref:System.IO.Compression.ZipFileExtensions?displayProperty=fullName> .  Use la clase de <xref:System.IO.Compression.ZipFileExtensions> , debe hacer referencia al ensamblado de `System.IO.Compression.FileSystem` en el proyecto.  
  
 [!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]  
  
## Ejemplo  
 El ejemplo siguiente utiliza la clase de <xref:System.IO.Compression.ZipArchive> para tener acceso a un archivo .zip, y agregar un nuevo archivo al archivo comprimido.  El nuevo archivo obtiene comprimido cuando se agrega al archivo .zip.  
  
 [!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]  
  
## Ejemplo  
 También puede utilizar las clases de <xref:System.IO.Compression.GZipStream> y de <xref:System.IO.Compression.DeflateStream> para comprimir y descomprimir datos.  Utilizan el mismo algoritmo de compresión.  Los objetos comprimidos de <xref:System.IO.Compression.GZipStream> que se escriben en un archivo con una extensión .gz se pueden descomprimir utilizando muchas herramientas comunes además de los métodos proporcionados por <xref:System.IO.Compression.GZipStream>.  En este ejemplo se muestra cómo comprimir y descomprimir un directorio de archivos mediante la clase <xref:System.IO.Compression.GZipStream>.  
  
 [!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
 [!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]  
  
## Vea también  
 <xref:System.IO.Compression.ZipArchive>   
 <xref:System.IO.Compression.ZipFile>   
 <xref:System.IO.Compression.ZipArchiveEntry>   
 <xref:System.IO.Compression.DeflateStream>   
 <xref:System.IO.Compression.GZipStream>   
 [E\/S de archivos y secuencias](../../../docs/standard/io/index.md)