---
title: Procedimiento para comprimir y extraer archivos
ms.date: 01/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], compression
- compression
- compress files
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
ms.openlocfilehash: 10f990401830bc5f77176f4e586f15f7dd75ff14
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80248022"
---
# <a name="how-to-compress-and-extract-files"></a>Procedimiento para comprimir y extraer archivos

El espacio de nombres <xref:System.IO.Compression> contiene los siguientes tipos para comprimir y descomprimir archivos y secuencias. También puede usar estos tipos para leer y modificar el contenido de un archivo comprimido.

- <xref:System.IO.Compression.ZipFile>
- <xref:System.IO.Compression.ZipArchive>
- <xref:System.IO.Compression.ZipArchiveEntry>
- <xref:System.IO.Compression.DeflateStream>
- <xref:System.IO.Compression.GZipStream>

Los siguientes ejemplos muestran algunas de las operaciones que se pueden ejecutar con archivos comprimidos. En estos ejemplos es necesario que los siguientes paquetes de NuGet se agreguen al proyecto:

- [System.IO.Compression](https://www.nuget.org/packages/System.IO.Compression)
- [System.IO.Compression.ZipFile](https://www.nuget.org/packages/System.IO.Compression.ZipFile)

Si se usa .NET Framework, agregue referencias a estas dos bibliotecas al proyecto:

- `System.IO.Compression`
- `System.IO.Compression.FileSystem`

## <a name="example-1-create-and-extract-a-zip-file"></a>Ejemplo 1: Crear y extraer un archivo .zip

En este ejemplo se muestra cómo crear y extraer un archivo comprimido *.zip* mediante la clase <xref:System.IO.Compression.ZipFile>. El ejemplo comprime el contenido de una carpeta en un nuevo archivo *.zip* y, a continuación, extrae el archivo zip a una nueva carpeta.

Para ejecutar el ejemplo, cree una carpeta de *inicio* en su carpeta de programa y rellénela con archivos que se van a comprimir.

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2-extract-specific-file-extensions"></a>Ejemplo 2: Extraer determinadas extensiones de archivo

El ejemplo siguiente recorre en iteración el contenido de un archivo *.zip* existente y extrae archivos que tienen una extensión *.txt*. Usa la clase <xref:System.IO.Compression.ZipArchive> para tener acceso al archivo zip y la clase <xref:System.IO.Compression.ZipArchiveEntry> para inspeccionar las entradas individuales. El método de extensión <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> para el objeto <xref:System.IO.Compression.ZipArchiveEntry> está disponible en la clase <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType>.

Para ejecutar el ejemplo, coloque un archivo *.zip* llamado *result.zip* en su carpeta de programa. Cuando se le pida, proporcione un nombre de carpeta al que se va a extraer.

> [!IMPORTANT]
> Al descomprimir archivos, también debe buscar rutas de acceso de archivos malintencionados que puedan salir del directorio en que descomprime. Esto se conoce como un ataque de ruta transversal. En el ejemplo siguiente se muestra cómo comprobar si hay rutas de acceso a archivos malintencionados y se proporciona una manera segura para descomprimir.

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3-add-a-file-to-an-existing-zip"></a>Ejemplo 3: Agregar un archivo a un archivo zip existente

En el ejemplo siguiente se utiliza la clase <xref:System.IO.Compression.ZipArchive> para acceder a un archivo *.zip* existente y se agrega un archivo a este. El nuevo archivo se comprime cuando se agrega al archivo zip existente.

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4-compress-and-decompress-gz-files"></a>Ejemplo 4: Comprimir y descomprimir archivos .gz

También puede usar las clases <xref:System.IO.Compression.GZipStream> y <xref:System.IO.Compression.DeflateStream> para comprimir y descomprimir los datos. Usan el mismo algoritmo de compresión. Puede descomprimir objetos <xref:System.IO.Compression.GZipStream> que se escriben en un archivo *.gz* mediante muchas herramientas comunes. En este ejemplo se muestra cómo comprimir y descomprimir un directorio de archivos con la clase <xref:System.IO.Compression.GZipStream>:

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a>Vea también

- <xref:System.IO.Compression.ZipArchive>  
- <xref:System.IO.Compression.ZipFile>  
- <xref:System.IO.Compression.ZipArchiveEntry>  
- <xref:System.IO.Compression.DeflateStream>  
- <xref:System.IO.Compression.GZipStream>  
- [E/S de archivos y secuencias](../../../docs/standard/io/index.md)
