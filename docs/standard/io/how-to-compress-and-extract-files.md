---
title: "Cómo: Comprimir y extraer archivos"
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
helpviewer_keywords:
- I/O [.NET Framework], compression
- compression
- compress files
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 33c9249692998aea8c22ddbf75a5a9b7bdf28708
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-compress-and-extract-files"></a>Cómo: Comprimir y extraer archivos
El espacio de nombres <xref:System.IO.Compression> contiene los siguientes tipos para comprimir y descomprimir archivos y secuencias. También puede usar estos tipos para leer y modificar el contenido de un archivo comprimido:  
  
-   <xref:System.IO.Compression.ZipFile>  
  
-   <xref:System.IO.Compression.ZipArchive>  
  
-   <xref:System.IO.Compression.ZipArchiveEntry>  
  
-   <xref:System.IO.Compression.DeflateStream>  
  
-   <xref:System.IO.Compression.GZipStream>  
  
 Los siguientes ejemplos muestran algunas de las funciones que se pueden ejecutar al trabajar con archivos comprimidos.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo muestra cómo crear y extraer un archivo comprimido que tiene una extensión de nombre de archivo .zip mediante la clase <xref:System.IO.Compression.ZipFile>. Comprime el contenido de una carpeta en un nuevo archivo .zip y, a continuación, extrae el contenido a una nueva carpeta. Para usar la clase <xref:System.IO.Compression.ZipFile>, debe hacer referencia al ensamblado `System.IO.Compression.FileSystem` del proyecto.  
  
 [!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo recorrer en iteración el contenido de un archivo .zip existente y cómo extraer los archivos que tienen una extensión. txt. Use la clase <xref:System.IO.Compression.ZipArchive> para acceder a un archivo .zip existente y la clase <xref:System.IO.Compression.ZipArchiveEntry> para inspeccionar las entradas individuales en el archivo comprimido. Use un método de extensión (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) para el objeto <xref:System.IO.Compression.ZipArchiveEntry>. El método de extensión está disponible en la clase <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType>. Para usar la clase <xref:System.IO.Compression.ZipFileExtensions>, debe hacer referencia al ensamblado `System.IO.Compression.FileSystem` del proyecto.  
  
 [!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza la clase <xref:System.IO.Compression.ZipArchive> para acceder a un archivo .zip existente y agrega un nuevo archivo al archivo comprimido. El nuevo archivo se comprime cuando se agrega al archivo .zip existente.  
  
 [!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]  
  
## <a name="example"></a>Ejemplo  
 También puede usar las clases <xref:System.IO.Compression.GZipStream> y <xref:System.IO.Compression.DeflateStream> para comprimir y descomprimir los datos. Usan el mismo algoritmo de compresión. Los objetos <xref:System.IO.Compression.GZipStream> comprimidos que se escriben en un archivo que tiene una extensión .gz se pueden descomprimir usando muchas herramientas comunes, además de los métodos proporcionados por <xref:System.IO.Compression.GZipStream>. Este ejemplo muestra cómo comprimir y descomprimir un directorio de archivos con la clase <xref:System.IO.Compression.GZipStream>.  
  
 [!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
 [!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO.Compression.ZipArchive>  
 <xref:System.IO.Compression.ZipFile>  
 <xref:System.IO.Compression.ZipArchiveEntry>  
 <xref:System.IO.Compression.DeflateStream>  
 <xref:System.IO.Compression.GZipStream>  
 [E/S de archivos y secuencias](../../../docs/standard/io/index.md)
