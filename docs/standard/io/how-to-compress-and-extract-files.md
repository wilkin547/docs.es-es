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
caps.latest.revision: "19"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 22a95ce18b602d4e329499c5d36557213e08a8b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-compress-and-extract-files"></a>Cómo: Comprimir y extraer archivos
El <xref:System.IO.Compression> espacio de nombres contiene los siguientes tipos para comprimir y descomprimir archivos y secuencias. También puede usar estos tipos para leer y modificar el contenido de un archivo comprimido:  
  
-   <xref:System.IO.Compression.ZipFile>  
  
-   <xref:System.IO.Compression.ZipArchive>  
  
-   <xref:System.IO.Compression.ZipArchiveEntry>  
  
-   <xref:System.IO.Compression.DeflateStream>  
  
-   <xref:System.IO.Compression.GZipStream>  
  
 Los siguientes ejemplos muestran algunas de las funciones que se pueden realizar al trabajar con archivos comprimidos.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo muestra cómo crear y extraer un archivo comprimido que tiene una extensión de nombre de archivo .zip mediante la <xref:System.IO.Compression.ZipFile> clase. Comprime el contenido de una carpeta en un nuevo archivo .zip y, a continuación, extrae el contenido a una nueva carpeta. Para usar el <xref:System.IO.Compression.ZipFile> (clase), debe hacer referencia a la `System.IO.Compression.FileSystem` ensamblado del proyecto.  
  
 [!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo recorrer en iteración el contenido de un archivo .zip existente y extraer los archivos que tienen una extensión. txt. Usa el <xref:System.IO.Compression.ZipArchive> clase para tener acceso a un archivo .zip existente y la <xref:System.IO.Compression.ZipArchiveEntry> clase para inspeccionar las entradas individuales en el archivo comprimido. Usa un método de extensión (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) para el <xref:System.IO.Compression.ZipArchiveEntry> objeto. El método de extensión está disponible en la <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> clase. Para usar el <xref:System.IO.Compression.ZipFileExtensions> (clase), debe hacer referencia a la `System.IO.Compression.FileSystem` ensamblado del proyecto.  
  
 [!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza la <xref:System.IO.Compression.ZipArchive> clase para tener acceso a un archivo zip existentes y agrega un nuevo archivo para el archivo comprimido. El nuevo archivo obtiene comprimen cuando se agrega el archivo .zip existente.  
  
 [!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]  
  
## <a name="example"></a>Ejemplo  
 También puede usar el <xref:System.IO.Compression.GZipStream> y <xref:System.IO.Compression.DeflateStream> clases para comprimir y descomprimir los datos. Usan el mismo algoritmo de compresión. Comprimido <xref:System.IO.Compression.GZipStream> objetos que se escriben en un archivo que tiene una extensión .gz se pueden descomprimir usando muchas herramientas comunes, además de los métodos proporcionados por <xref:System.IO.Compression.GZipStream>. Este ejemplo muestra cómo comprimir y descomprimir un directorio de archivos mediante el uso de la <xref:System.IO.Compression.GZipStream> clase.  
  
 [!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
 [!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO.Compression.ZipArchive>  
 <xref:System.IO.Compression.ZipFile>  
 <xref:System.IO.Compression.ZipArchiveEntry>  
 <xref:System.IO.Compression.DeflateStream>  
 <xref:System.IO.Compression.GZipStream>  
 [E/S de archivos y secuencias](../../../docs/standard/io/index.md)
