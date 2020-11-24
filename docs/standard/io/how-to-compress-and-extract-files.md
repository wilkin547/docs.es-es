---
title: Procedimiento para comprimir y extraer archivos
description: Comprima y extraiga archivos con System.IO.Compression. Vea ejemplos de uso de ZipFile, ZipArchive, ZipArchiveEntry, DeflateStream y GZipStream.
ms.date: 01/14/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET], compression
- compression
- compress files
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
ms.openlocfilehash: a1077c7277e0aa54e3c8883cfc27d93926485b8e
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830862"
---
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="2a223-104">Procedimiento para comprimir y extraer archivos</span><span class="sxs-lookup"><span data-stu-id="2a223-104">How to: Compress and extract files</span></span>

<span data-ttu-id="2a223-105">El espacio de nombres <xref:System.IO.Compression> contiene los siguientes tipos para comprimir y descomprimir archivos y secuencias.</span><span class="sxs-lookup"><span data-stu-id="2a223-105">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="2a223-106">También puede usar estos tipos para leer y modificar el contenido de un archivo comprimido.</span><span class="sxs-lookup"><span data-stu-id="2a223-106">You can also use these types to read and modify the contents of a compressed file.</span></span>

- <xref:System.IO.Compression.ZipFile>
- <xref:System.IO.Compression.ZipArchive>
- <xref:System.IO.Compression.ZipArchiveEntry>
- <xref:System.IO.Compression.DeflateStream>
- <xref:System.IO.Compression.GZipStream>

<span data-ttu-id="2a223-107">Los siguientes ejemplos muestran algunas de las operaciones que se pueden ejecutar con archivos comprimidos.</span><span class="sxs-lookup"><span data-stu-id="2a223-107">The following examples show some of the operations you can perform with compressed files.</span></span> <span data-ttu-id="2a223-108">En estos ejemplos es necesario que los siguientes paquetes de NuGet se agreguen al proyecto:</span><span class="sxs-lookup"><span data-stu-id="2a223-108">These examples require the following NuGet packages to be added to your project:</span></span>

- [<span data-ttu-id="2a223-109">System.IO.Compression</span><span class="sxs-lookup"><span data-stu-id="2a223-109">System.IO.Compression</span></span>](https://www.nuget.org/packages/System.IO.Compression)
- [<span data-ttu-id="2a223-110">System.IO.Compression.ZipFile</span><span class="sxs-lookup"><span data-stu-id="2a223-110">System.IO.Compression.ZipFile</span></span>](https://www.nuget.org/packages/System.IO.Compression.ZipFile)

<span data-ttu-id="2a223-111">Si se usa .NET Framework, agregue referencias a estas dos bibliotecas al proyecto:</span><span class="sxs-lookup"><span data-stu-id="2a223-111">If you're using .NET Framework, add references to these two libraries to your project:</span></span>

- `System.IO.Compression`
- `System.IO.Compression.FileSystem`

## <a name="example-1-create-and-extract-a-zip-file"></a><span data-ttu-id="2a223-112">Ejemplo 1: Crear y extraer un archivo .zip</span><span class="sxs-lookup"><span data-stu-id="2a223-112">Example 1: Create and extract a .zip file</span></span>

<span data-ttu-id="2a223-113">En este ejemplo se muestra cómo crear y extraer un archivo comprimido *.zip* mediante la clase <xref:System.IO.Compression.ZipFile>.</span><span class="sxs-lookup"><span data-stu-id="2a223-113">The following example shows how to create and extract a compressed *.zip* file by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="2a223-114">El ejemplo comprime el contenido de una carpeta en un nuevo archivo *.zip* y, a continuación, extrae el archivo zip a una nueva carpeta.</span><span class="sxs-lookup"><span data-stu-id="2a223-114">The example compresses the contents of a folder into a new *.zip* file, and then extracts the zip to a new folder.</span></span>

<span data-ttu-id="2a223-115">Para ejecutar el ejemplo, cree una carpeta de *inicio* en su carpeta de programa y rellénela con archivos que se van a comprimir.</span><span class="sxs-lookup"><span data-stu-id="2a223-115">To run the sample, create a *start* folder in your program folder and populate it with files to zip.</span></span>

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2-extract-specific-file-extensions"></a><span data-ttu-id="2a223-116">Ejemplo 2: Extraer determinadas extensiones de archivo</span><span class="sxs-lookup"><span data-stu-id="2a223-116">Example 2: Extract specific file extensions</span></span>

<span data-ttu-id="2a223-117">El ejemplo siguiente recorre en iteración el contenido de un archivo *.zip* existente y extrae archivos que tienen una extensión *.txt*.</span><span class="sxs-lookup"><span data-stu-id="2a223-117">The next example iterates through the contents of an existing *.zip* file and extracts files that have a *.txt* extension.</span></span> <span data-ttu-id="2a223-118">Usa la clase <xref:System.IO.Compression.ZipArchive> para tener acceso al archivo zip y la clase <xref:System.IO.Compression.ZipArchiveEntry> para inspeccionar las entradas individuales.</span><span class="sxs-lookup"><span data-stu-id="2a223-118">It uses the <xref:System.IO.Compression.ZipArchive> class to access the zip, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries.</span></span> <span data-ttu-id="2a223-119">El método de extensión <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> para el objeto <xref:System.IO.Compression.ZipArchiveEntry> está disponible en la clase <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2a223-119">The extension method <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> for the <xref:System.IO.Compression.ZipArchiveEntry> object is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span>

<span data-ttu-id="2a223-120">Para ejecutar el ejemplo, coloque un archivo *.zip* llamado *result.zip* en su carpeta de programa.</span><span class="sxs-lookup"><span data-stu-id="2a223-120">To run the sample, place a *.zip* file called *result.zip* in your program folder.</span></span> <span data-ttu-id="2a223-121">Cuando se le pida, proporcione un nombre de carpeta al que se va a extraer.</span><span class="sxs-lookup"><span data-stu-id="2a223-121">When prompted, provide a folder name to extract to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a223-122">Al descomprimir archivos, también debe buscar rutas de acceso de archivos malintencionados que puedan salir del directorio en que descomprime.</span><span class="sxs-lookup"><span data-stu-id="2a223-122">When unzipping files, you must look for malicious file paths, which can escape out of the directory you unzip into.</span></span> <span data-ttu-id="2a223-123">Esto se conoce como un ataque de ruta transversal.</span><span class="sxs-lookup"><span data-stu-id="2a223-123">This is known as a path traversal attack.</span></span> <span data-ttu-id="2a223-124">En el ejemplo siguiente se muestra cómo comprobar si hay rutas de acceso a archivos malintencionados y se proporciona una manera segura para descomprimir.</span><span class="sxs-lookup"><span data-stu-id="2a223-124">The following example demonstrates how to check for malicious file paths and provides a safe way to unzip.</span></span>

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3-add-a-file-to-an-existing-zip"></a><span data-ttu-id="2a223-125">Ejemplo 3: Agregar un archivo a un archivo zip existente</span><span class="sxs-lookup"><span data-stu-id="2a223-125">Example 3: Add a file to an existing zip</span></span>

<span data-ttu-id="2a223-126">En el ejemplo siguiente se utiliza la clase <xref:System.IO.Compression.ZipArchive> para acceder a un archivo *.zip* existente y se agrega un archivo a este.</span><span class="sxs-lookup"><span data-stu-id="2a223-126">The following example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing *.zip* file, and adds a file to it.</span></span> <span data-ttu-id="2a223-127">El nuevo archivo se comprime cuando se agrega al archivo zip existente.</span><span class="sxs-lookup"><span data-stu-id="2a223-127">The new file gets compressed when you add it to the existing zip.</span></span>

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4-compress-and-decompress-gz-files"></a><span data-ttu-id="2a223-128">Ejemplo 4: Comprimir y descomprimir archivos .gz</span><span class="sxs-lookup"><span data-stu-id="2a223-128">Example 4: Compress and decompress .gz files</span></span>

<span data-ttu-id="2a223-129">También puede usar las clases <xref:System.IO.Compression.GZipStream> y <xref:System.IO.Compression.DeflateStream> para comprimir y descomprimir los datos.</span><span class="sxs-lookup"><span data-stu-id="2a223-129">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="2a223-130">Usan el mismo algoritmo de compresión.</span><span class="sxs-lookup"><span data-stu-id="2a223-130">They use the same compression algorithm.</span></span> <span data-ttu-id="2a223-131">Puede descomprimir objetos <xref:System.IO.Compression.GZipStream> que se escriben en un archivo *.gz* mediante muchas herramientas comunes.</span><span class="sxs-lookup"><span data-stu-id="2a223-131">You can decompress <xref:System.IO.Compression.GZipStream> objects that are written to a *.gz* file by using many common tools.</span></span> <span data-ttu-id="2a223-132">En este ejemplo se muestra cómo comprimir y descomprimir un directorio de archivos con la clase <xref:System.IO.Compression.GZipStream>:</span><span class="sxs-lookup"><span data-stu-id="2a223-132">The following example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class:</span></span>

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a><span data-ttu-id="2a223-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a223-133">See also</span></span>

- <xref:System.IO.Compression.ZipArchive>  
- <xref:System.IO.Compression.ZipFile>  
- <xref:System.IO.Compression.ZipArchiveEntry>  
- <xref:System.IO.Compression.DeflateStream>  
- <xref:System.IO.Compression.GZipStream>  
- [<span data-ttu-id="2a223-134">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="2a223-134">File and stream I/O</span></span>](index.md)
