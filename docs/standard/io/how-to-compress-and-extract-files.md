---
title: Compresión y extracción de archivos
ms.date: 06/06/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], compression
- compression
- compress files
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f045f2137d65a66ac025c81e58e66c96bcaca031
ms.sourcegitcommit: d955cb4c681d68cf301d410925d83f25172ece86
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2018
ms.locfileid: "34827129"
---
# <a name="how-to-compress-and-extract-files"></a>Compresión y extracción de archivos

El espacio de nombres <xref:System.IO.Compression> contiene los siguientes tipos para comprimir y descomprimir archivos y secuencias. También puede usar estos tipos para leer y modificar el contenido de un archivo comprimido:

- <xref:System.IO.Compression.ZipFile>

- <xref:System.IO.Compression.ZipArchive>

- <xref:System.IO.Compression.ZipArchiveEntry>

- <xref:System.IO.Compression.DeflateStream>

- <xref:System.IO.Compression.GZipStream>

Los siguientes ejemplos muestran algunas de las funciones que se pueden ejecutar al trabajar con archivos comprimidos.

## <a name="example-1---create-and-extract-a-zip-file"></a>Ejemplo 1: crear y extraer un archivo .zip

En este ejemplo se muestra cómo crear y extraer un archivo comprimido que tiene una extensión de nombre de archivo .zip mediante la clase <xref:System.IO.Compression.ZipFile>. Comprime el contenido de una carpeta en un nuevo archivo .zip y, a continuación, extrae el contenido a una nueva carpeta. Para usar la clase <xref:System.IO.Compression.ZipFile>, debe hacer referencia al ensamblado `System.IO.Compression.FileSystem` del proyecto.

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2---extract-specific-file-extensions"></a>Ejemplo 2: extraer determinadas extensiones de archivo

En el ejemplo siguiente se muestra cómo recorrer en iteración el contenido de un archivo .zip existente y cómo extraer los archivos que tienen una extensión. txt. Use la clase <xref:System.IO.Compression.ZipArchive> para acceder a un archivo .zip existente y la clase <xref:System.IO.Compression.ZipArchiveEntry> para inspeccionar las entradas individuales en el archivo comprimido. Use un método de extensión (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) para el objeto <xref:System.IO.Compression.ZipArchiveEntry>. El método de extensión está disponible en la clase <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType>. Para usar la clase <xref:System.IO.Compression.ZipFileExtensions>, debe hacer referencia al ensamblado `System.IO.Compression.FileSystem` del proyecto.

> [!IMPORTANT]
> Al descomprimir archivos, también debe buscar rutas de acceso de archivos malintencionados que puedan salir del directorio en que desea descomprimir. Esto se conoce como un ataque de ruta transversal.

En el ejemplo siguiente se muestra cómo comprobar si hay rutas de acceso a archivos malintencionados y se proporciona una manera segura para descomprimir:

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3---add-a-new-file-to-an-existing-zip-file"></a>Ejemplo 3: agregar un nuevo archivo a un archivo .zip existente

En el ejemplo siguiente se utiliza la clase <xref:System.IO.Compression.ZipArchive> para acceder a un archivo .zip existente y se agrega un nuevo archivo al archivo comprimido. El nuevo archivo se comprime cuando se agrega al archivo .zip existente.

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4---compress-and-decompress-a-directory-of-gz-files"></a>Ejemplo 4: comprimir y descomprimir un directorio de archivos .gz

También puede usar las clases <xref:System.IO.Compression.GZipStream> y <xref:System.IO.Compression.DeflateStream> para comprimir y descomprimir los datos. Usan el mismo algoritmo de compresión. Los objetos <xref:System.IO.Compression.GZipStream> comprimidos que se escriben en un archivo que tiene una extensión .gz se pueden descomprimir usando muchas herramientas comunes, además de los métodos proporcionados por <xref:System.IO.Compression.GZipStream>. En este ejemplo se muestra cómo comprimir y descomprimir un directorio de archivos con la clase <xref:System.IO.Compression.GZipStream>:

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a>Vea también

<xref:System.IO.Compression.ZipArchive>  
<xref:System.IO.Compression.ZipFile>  
<xref:System.IO.Compression.ZipArchiveEntry>  
<xref:System.IO.Compression.DeflateStream>  
<xref:System.IO.Compression.GZipStream>  
[E/S de archivos y secuencias](../../../docs/standard/io/index.md)
