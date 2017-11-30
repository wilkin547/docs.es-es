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
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="67d1c-102">Cómo: Comprimir y extraer archivos</span><span class="sxs-lookup"><span data-stu-id="67d1c-102">How to: Compress and Extract Files</span></span>
<span data-ttu-id="67d1c-103">El <xref:System.IO.Compression> espacio de nombres contiene los siguientes tipos para comprimir y descomprimir archivos y secuencias.</span><span class="sxs-lookup"><span data-stu-id="67d1c-103">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="67d1c-104">También puede usar estos tipos para leer y modificar el contenido de un archivo comprimido:</span><span class="sxs-lookup"><span data-stu-id="67d1c-104">You can also use these types to read and modify the contents of a compressed file:</span></span>  
  
-   <xref:System.IO.Compression.ZipFile>  
  
-   <xref:System.IO.Compression.ZipArchive>  
  
-   <xref:System.IO.Compression.ZipArchiveEntry>  
  
-   <xref:System.IO.Compression.DeflateStream>  
  
-   <xref:System.IO.Compression.GZipStream>  
  
 <span data-ttu-id="67d1c-105">Los siguientes ejemplos muestran algunas de las funciones que se pueden realizar al trabajar con archivos comprimidos.</span><span class="sxs-lookup"><span data-stu-id="67d1c-105">The following examples show some of the functions you can perform when working with compressed files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67d1c-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67d1c-106">Example</span></span>  
 <span data-ttu-id="67d1c-107">Este ejemplo muestra cómo crear y extraer un archivo comprimido que tiene una extensión de nombre de archivo .zip mediante la <xref:System.IO.Compression.ZipFile> clase.</span><span class="sxs-lookup"><span data-stu-id="67d1c-107">This example shows how to create and extract a compressed file that has a .zip file name extension by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="67d1c-108">Comprime el contenido de una carpeta en un nuevo archivo .zip y, a continuación, extrae el contenido a una nueva carpeta.</span><span class="sxs-lookup"><span data-stu-id="67d1c-108">It compresses the contents of a folder into a new .zip file and then extracts that content to a new folder.</span></span> <span data-ttu-id="67d1c-109">Para usar el <xref:System.IO.Compression.ZipFile> (clase), debe hacer referencia a la `System.IO.Compression.FileSystem` ensamblado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="67d1c-109">To use the <xref:System.IO.Compression.ZipFile> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="67d1c-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67d1c-110">Example</span></span>  
 <span data-ttu-id="67d1c-111">En el ejemplo siguiente se muestra cómo recorrer en iteración el contenido de un archivo .zip existente y extraer los archivos que tienen una extensión. txt.</span><span class="sxs-lookup"><span data-stu-id="67d1c-111">The next example shows how to iterate through the contents of an existing .zip file and extract files that have a .txt extension.</span></span> <span data-ttu-id="67d1c-112">Usa el <xref:System.IO.Compression.ZipArchive> clase para tener acceso a un archivo .zip existente y la <xref:System.IO.Compression.ZipArchiveEntry> clase para inspeccionar las entradas individuales en el archivo comprimido.</span><span class="sxs-lookup"><span data-stu-id="67d1c-112">It uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries in the compressed file.</span></span> <span data-ttu-id="67d1c-113">Usa un método de extensión (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) para el <xref:System.IO.Compression.ZipArchiveEntry> objeto.</span><span class="sxs-lookup"><span data-stu-id="67d1c-113">It uses an extension method (<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>) for the <xref:System.IO.Compression.ZipArchiveEntry> object.</span></span> <span data-ttu-id="67d1c-114">El método de extensión está disponible en la <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> clase.</span><span class="sxs-lookup"><span data-stu-id="67d1c-114">The extension method is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="67d1c-115">Para usar el <xref:System.IO.Compression.ZipFileExtensions> (clase), debe hacer referencia a la `System.IO.Compression.FileSystem` ensamblado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="67d1c-115">To use the <xref:System.IO.Compression.ZipFileExtensions> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="67d1c-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67d1c-116">Example</span></span>  
 <span data-ttu-id="67d1c-117">En el ejemplo siguiente se utiliza la <xref:System.IO.Compression.ZipArchive> clase para tener acceso a un archivo zip existentes y agrega un nuevo archivo para el archivo comprimido.</span><span class="sxs-lookup"><span data-stu-id="67d1c-117">The next example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing .zip file, and adds a new file to the compressed file.</span></span> <span data-ttu-id="67d1c-118">El nuevo archivo obtiene comprimen cuando se agrega el archivo .zip existente.</span><span class="sxs-lookup"><span data-stu-id="67d1c-118">The new file gets compressed when you add it to the existing .zip file.</span></span>  
  
 [!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="67d1c-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67d1c-119">Example</span></span>  
 <span data-ttu-id="67d1c-120">También puede usar el <xref:System.IO.Compression.GZipStream> y <xref:System.IO.Compression.DeflateStream> clases para comprimir y descomprimir los datos.</span><span class="sxs-lookup"><span data-stu-id="67d1c-120">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="67d1c-121">Usan el mismo algoritmo de compresión.</span><span class="sxs-lookup"><span data-stu-id="67d1c-121">They use the same compression algorithm.</span></span> <span data-ttu-id="67d1c-122">Comprimido <xref:System.IO.Compression.GZipStream> objetos que se escriben en un archivo que tiene una extensión .gz se pueden descomprimir usando muchas herramientas comunes, además de los métodos proporcionados por <xref:System.IO.Compression.GZipStream>.</span><span class="sxs-lookup"><span data-stu-id="67d1c-122">Compressed <xref:System.IO.Compression.GZipStream> objects that are written to a file that has an extension of .gz can be decompressed by using many common tools in addition to the methods provided by <xref:System.IO.Compression.GZipStream>.</span></span> <span data-ttu-id="67d1c-123">Este ejemplo muestra cómo comprimir y descomprimir un directorio de archivos mediante el uso de la <xref:System.IO.Compression.GZipStream> clase.</span><span class="sxs-lookup"><span data-stu-id="67d1c-123">This example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class.</span></span>  
  
 [!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
 [!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="67d1c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="67d1c-124">See Also</span></span>  
 <xref:System.IO.Compression.ZipArchive>  
 <xref:System.IO.Compression.ZipFile>  
 <xref:System.IO.Compression.ZipArchiveEntry>  
 <xref:System.IO.Compression.DeflateStream>  
 <xref:System.IO.Compression.GZipStream>  
 [<span data-ttu-id="67d1c-125">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="67d1c-125">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
