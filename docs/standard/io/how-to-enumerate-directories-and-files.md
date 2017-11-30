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
# <a name="how-to-enumerate-directories-and-files"></a><span data-ttu-id="c0864-102">Cómo: Enumerar directorios y archivos</span><span class="sxs-lookup"><span data-stu-id="c0864-102">How to: Enumerate Directories and Files</span></span>
<span data-ttu-id="c0864-103">Puede enumerar directorios y archivos utilizando métodos que devuelven una colección enumerable de cadenas de sus nombres.</span><span class="sxs-lookup"><span data-stu-id="c0864-103">You can enumerate directories and files by using methods that return an enumerable collection of strings of their names.</span></span> <span data-ttu-id="c0864-104">También puede utilizar métodos que devuelven una colección enumerable de <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, o <xref:System.IO.FileSystemInfo> objetos.</span><span class="sxs-lookup"><span data-stu-id="c0864-104">You can also use methods that return an enumerable collection of <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, or <xref:System.IO.FileSystemInfo> objects.</span></span> <span data-ttu-id="c0864-105">Colecciones enumerables proporcionan un mejor rendimiento que las matrices cuando se trabaja con grandes conjuntos de archivos y directorios.</span><span class="sxs-lookup"><span data-stu-id="c0864-105">Enumerable collections provide better performance than arrays when you work with large collections of directories and files.</span></span>  
  
 <span data-ttu-id="c0864-106">También puede utilizar colecciones enumerables obtenidas de estos métodos para suministrar la <xref:System.Collections.Generic.IEnumerable%601> parámetro constructores de colección de clases como la <xref:System.Collections.Generic.List%601> clase.</span><span class="sxs-lookup"><span data-stu-id="c0864-106">You can also use enumerable collections obtained from these methods to supply the <xref:System.Collections.Generic.IEnumerable%601> parameter for constructors of collection classes such as the <xref:System.Collections.Generic.List%601> class.</span></span>  
  
 <span data-ttu-id="c0864-107">Si desea obtener solo los nombres de directorios o archivos, utilice los métodos de enumeración de la <xref:System.IO.Directory> clase.</span><span class="sxs-lookup"><span data-stu-id="c0864-107">If you want to obtain only the names of directories or files, use the enumeration methods of the <xref:System.IO.Directory> class.</span></span> <span data-ttu-id="c0864-108">Si desea obtener otras propiedades de directorios o archivos, utilice la <xref:System.IO.DirectoryInfo> y <xref:System.IO.FileSystemInfo> clases.</span><span class="sxs-lookup"><span data-stu-id="c0864-108">If you want to obtain other properties of directories or files, use the <xref:System.IO.DirectoryInfo> and <xref:System.IO.FileSystemInfo> classes.</span></span>  
  
 <span data-ttu-id="c0864-109">En la tabla siguiente proporciona a una guía para los métodos que devuelven colecciones enumerables.</span><span class="sxs-lookup"><span data-stu-id="c0864-109">The following table provides a guide to the methods that return enumerable collections.</span></span>  
  
|<span data-ttu-id="c0864-110">Para enumerar</span><span class="sxs-lookup"><span data-stu-id="c0864-110">To enumerate</span></span>|<span data-ttu-id="c0864-111">Colección enumerable que se va a devolver</span><span class="sxs-lookup"><span data-stu-id="c0864-111">Enumerable collection to return</span></span>|<span data-ttu-id="c0864-112">Método que se usa</span><span class="sxs-lookup"><span data-stu-id="c0864-112">Method to use</span></span>|  
|------------------|-------------------------------------|-------------------|  
|<span data-ttu-id="c0864-113">Directorios</span><span class="sxs-lookup"><span data-stu-id="c0864-113">Directories</span></span>|<span data-ttu-id="c0864-114">Nombres de directorio</span><span class="sxs-lookup"><span data-stu-id="c0864-114">Directory names</span></span>|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="c0864-115">Información del directorio (<xref:System.IO.DirectoryInfo>)</span><span class="sxs-lookup"><span data-stu-id="c0864-115">Directory information (<xref:System.IO.DirectoryInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="c0864-116">Archivos</span><span class="sxs-lookup"><span data-stu-id="c0864-116">Files</span></span>|<span data-ttu-id="c0864-117">Nombres de archivo</span><span class="sxs-lookup"><span data-stu-id="c0864-117">File names</span></span>|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="c0864-118">Archivo de información (<xref:System.IO.FileInfo>)</span><span class="sxs-lookup"><span data-stu-id="c0864-118">File information (<xref:System.IO.FileInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="c0864-119">Información del sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="c0864-119">File system information</span></span>|<span data-ttu-id="c0864-120">Entradas del sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="c0864-120">File system entries</span></span>|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="c0864-121">Información del sistema de archivos (<xref:System.IO.FileSystemInfo>)</span><span class="sxs-lookup"><span data-stu-id="c0864-121">File system information (<xref:System.IO.FileSystemInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="c0864-122">Aunque puede enumerar inmediatamente todos los archivos en los subdirectorios de un directorio primario usando el <xref:System.IO.SearchOption.AllDirectories> Buscar opción proporcionada por el <xref:System.IO.SearchOption> enumeración, las excepciones de acceso no autorizado (<xref:System.UnauthorizedAccessException>) puede provocar la enumeración estar incompletos.</span><span class="sxs-lookup"><span data-stu-id="c0864-122">Although you can immediately enumerate all the files in the subdirectories of a parent directory by using the <xref:System.IO.SearchOption.AllDirectories> search option provided by the <xref:System.IO.SearchOption> enumeration, unauthorized access exceptions (<xref:System.UnauthorizedAccessException>) may cause the enumeration to be incomplete.</span></span> <span data-ttu-id="c0864-123">Si estas excepciones son posibles, puede detectarlas y continuar enumerando primero los directorios y, a continuación, enumerar los archivos.</span><span class="sxs-lookup"><span data-stu-id="c0864-123">If these exceptions are possible, you can catch them and continue by first enumerating directories and then enumerating files.</span></span>  
  
### <a name="to-enumerate-directory-names"></a><span data-ttu-id="c0864-124">Para enumerar los nombres de directorio</span><span class="sxs-lookup"><span data-stu-id="c0864-124">To enumerate directory names</span></span>  
  
-   <span data-ttu-id="c0864-125">Use la <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> método para obtener una lista de los nombres de directorio de nivel superior en una ruta de acceso especificada.</span><span class="sxs-lookup"><span data-stu-id="c0864-125">Use the <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> method to obtain a list of the top-level directory names in a specified path.</span></span>  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a><span data-ttu-id="c0864-126">Para enumerar los nombres de archivo en un directorio y subdirectorios</span><span class="sxs-lookup"><span data-stu-id="c0864-126">To enumerate file names in a directory and subdirectories</span></span>  
  
-   <span data-ttu-id="c0864-127">Use la <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> método para buscar un directorio y (opcionalmente) en sus subdirectorios y para obtener una lista de nombres de archivo que coinciden con un patrón de búsqueda especificado.</span><span class="sxs-lookup"><span data-stu-id="c0864-127">Use the <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> method to search a directory and (optionally) its subdirectories, and to obtain a list of file names that match a specified search pattern.</span></span>  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a><span data-ttu-id="c0864-128">Enumerar una colección de objetos DirectoryInfo</span><span class="sxs-lookup"><span data-stu-id="c0864-128">To enumerate a collection of DirectoryInfo objects</span></span>  
  
-   <span data-ttu-id="c0864-129">Use la <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> método para obtener una colección de los directorios de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="c0864-129">Use the <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> method to obtain a collection of top-level directories.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a><span data-ttu-id="c0864-130">Enumerar una colección de objetos FileInfo en todos los directorios</span><span class="sxs-lookup"><span data-stu-id="c0864-130">To enumerate a collection of FileInfo objects in all directories</span></span>  
  
-   <span data-ttu-id="c0864-131">Use la <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> método para obtener una colección de archivos que coinciden con un patrón de búsqueda especificado en todos los directorios.</span><span class="sxs-lookup"><span data-stu-id="c0864-131">Use the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> method to obtain a collection of files that match a specified search pattern in all directories.</span></span> <span data-ttu-id="c0864-132">Este ejemplo enumera primero los directorios de nivel superior para detectar las excepciones de posibles accesos no autorizados y, a continuación, enumera los archivos.</span><span class="sxs-lookup"><span data-stu-id="c0864-132">This example first enumerates the top-level directories to catch possible unauthorized access exceptions, and then enumerates the files.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c0864-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0864-133">See Also</span></span>  
 [<span data-ttu-id="c0864-134">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="c0864-134">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
