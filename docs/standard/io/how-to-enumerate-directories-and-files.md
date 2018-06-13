---
title: 'Cómo: Enumerar directorios y archivos'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4cd7b7542e5cf9352e965717368399dcf4a9ecd2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575855"
---
# <a name="how-to-enumerate-directories-and-files"></a><span data-ttu-id="c8944-102">Cómo: Enumerar directorios y archivos</span><span class="sxs-lookup"><span data-stu-id="c8944-102">How to: Enumerate Directories and Files</span></span>
<span data-ttu-id="c8944-103">Puede enumerar directorios y archivos utilizando métodos que devuelven una colección enumerable de cadenas de sus nombres.</span><span class="sxs-lookup"><span data-stu-id="c8944-103">You can enumerate directories and files by using methods that return an enumerable collection of strings of their names.</span></span> <span data-ttu-id="c8944-104">También puede utilizar métodos que devuelven una colección enumerable de objetos <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo> o <xref:System.IO.FileSystemInfo>.</span><span class="sxs-lookup"><span data-stu-id="c8944-104">You can also use methods that return an enumerable collection of <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, or <xref:System.IO.FileSystemInfo> objects.</span></span> <span data-ttu-id="c8944-105">Las colecciones enumerables ofrecen mayor rendimiento que las matrices cuando se trabaja con colecciones grandes de directorios y archivos.</span><span class="sxs-lookup"><span data-stu-id="c8944-105">Enumerable collections provide better performance than arrays when you work with large collections of directories and files.</span></span>  
  
 <span data-ttu-id="c8944-106">También puede utilizar colecciones enumerables obtenidas de estos métodos para suministrar el parámetro <xref:System.Collections.Generic.IEnumerable%601> para los constructores de clases de colecciones como la clase <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="c8944-106">You can also use enumerable collections obtained from these methods to supply the <xref:System.Collections.Generic.IEnumerable%601> parameter for constructors of collection classes such as the <xref:System.Collections.Generic.List%601> class.</span></span>  
  
 <span data-ttu-id="c8944-107">Si desea obtener solo los nombres de directorios o archivos, utilice los métodos de enumeración de la clase <xref:System.IO.Directory>.</span><span class="sxs-lookup"><span data-stu-id="c8944-107">If you want to obtain only the names of directories or files, use the enumeration methods of the <xref:System.IO.Directory> class.</span></span> <span data-ttu-id="c8944-108">Si desea obtener otras propiedades de directorios o archivos, utilice las clases <xref:System.IO.DirectoryInfo> y <xref:System.IO.FileSystemInfo>.</span><span class="sxs-lookup"><span data-stu-id="c8944-108">If you want to obtain other properties of directories or files, use the <xref:System.IO.DirectoryInfo> and <xref:System.IO.FileSystemInfo> classes.</span></span>  
  
 <span data-ttu-id="c8944-109">En la tabla siguiente se proporciona una guía de los métodos que devuelven colecciones enumerables.</span><span class="sxs-lookup"><span data-stu-id="c8944-109">The following table provides a guide to the methods that return enumerable collections.</span></span>  
  
|<span data-ttu-id="c8944-110">Para enumerar</span><span class="sxs-lookup"><span data-stu-id="c8944-110">To enumerate</span></span>|<span data-ttu-id="c8944-111">Colección enumerable que se va a devolver</span><span class="sxs-lookup"><span data-stu-id="c8944-111">Enumerable collection to return</span></span>|<span data-ttu-id="c8944-112">Método que se usa</span><span class="sxs-lookup"><span data-stu-id="c8944-112">Method to use</span></span>|  
|------------------|-------------------------------------|-------------------|  
|<span data-ttu-id="c8944-113">Directorios</span><span class="sxs-lookup"><span data-stu-id="c8944-113">Directories</span></span>|<span data-ttu-id="c8944-114">Nombres de directorio</span><span class="sxs-lookup"><span data-stu-id="c8944-114">Directory names</span></span>|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="c8944-115">Información de directorio (<xref:System.IO.DirectoryInfo>)</span><span class="sxs-lookup"><span data-stu-id="c8944-115">Directory information (<xref:System.IO.DirectoryInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="c8944-116">Archivos</span><span class="sxs-lookup"><span data-stu-id="c8944-116">Files</span></span>|<span data-ttu-id="c8944-117">Nombres de archivo</span><span class="sxs-lookup"><span data-stu-id="c8944-117">File names</span></span>|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="c8944-118">Información del archivo (<xref:System.IO.FileInfo>)</span><span class="sxs-lookup"><span data-stu-id="c8944-118">File information (<xref:System.IO.FileInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="c8944-119">Información del sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="c8944-119">File system information</span></span>|<span data-ttu-id="c8944-120">Entradas del sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="c8944-120">File system entries</span></span>|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="c8944-121">Información del sistema de archivos (<xref:System.IO.FileSystemInfo>)</span><span class="sxs-lookup"><span data-stu-id="c8944-121">File system information (<xref:System.IO.FileSystemInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="c8944-122">Aunque puede enumerar inmediatamente todos los archivos de los subdirectorios de un directorio principal mediante la opción de búsqueda <xref:System.IO.SearchOption.AllDirectories> proporcionada por la enumeración <xref:System.IO.SearchOption>, las excepciones de acceso no autorizado (<xref:System.UnauthorizedAccessException>) pueden dar lugar a que la enumeración esté incompleta.</span><span class="sxs-lookup"><span data-stu-id="c8944-122">Although you can immediately enumerate all the files in the subdirectories of a parent directory by using the <xref:System.IO.SearchOption.AllDirectories> search option provided by the <xref:System.IO.SearchOption> enumeration, unauthorized access exceptions (<xref:System.UnauthorizedAccessException>) may cause the enumeration to be incomplete.</span></span> <span data-ttu-id="c8944-123">Si estas excepciones son posibles, puede detectarlas y continuar enumerando primero los directorios y luego los archivos.</span><span class="sxs-lookup"><span data-stu-id="c8944-123">If these exceptions are possible, you can catch them and continue by first enumerating directories and then enumerating files.</span></span>  
  
### <a name="to-enumerate-directory-names"></a><span data-ttu-id="c8944-124">Para enumerar los nombres de directorio</span><span class="sxs-lookup"><span data-stu-id="c8944-124">To enumerate directory names</span></span>  
  
-   <span data-ttu-id="c8944-125">Use el método <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> para obtener una lista de los nombres de directorio de nivel superior en una ruta de acceso especificada.</span><span class="sxs-lookup"><span data-stu-id="c8944-125">Use the <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> method to obtain a list of the top-level directory names in a specified path.</span></span>  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a><span data-ttu-id="c8944-126">Para enumerar los nombres de archivo de un directorio y de subdirectorios</span><span class="sxs-lookup"><span data-stu-id="c8944-126">To enumerate file names in a directory and subdirectories</span></span>  
  
-   <span data-ttu-id="c8944-127">Use el método <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> para buscar un directorio y (opcionalmente) sus subdirectorios y para obtener una lista de nombres de archivo que coincidan con un patrón de búsqueda especificado.</span><span class="sxs-lookup"><span data-stu-id="c8944-127">Use the <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> method to search a directory and (optionally) its subdirectories, and to obtain a list of file names that match a specified search pattern.</span></span>  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a><span data-ttu-id="c8944-128">Para enumerar una colección de objetos DirectoryInfo</span><span class="sxs-lookup"><span data-stu-id="c8944-128">To enumerate a collection of DirectoryInfo objects</span></span>  
  
-   <span data-ttu-id="c8944-129">Use el método <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> para obtener una colección de los directorios de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="c8944-129">Use the <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> method to obtain a collection of top-level directories.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a><span data-ttu-id="c8944-130">Para enumerar una colección de objetos FileInfo en todos los directorios</span><span class="sxs-lookup"><span data-stu-id="c8944-130">To enumerate a collection of FileInfo objects in all directories</span></span>  
  
-   <span data-ttu-id="c8944-131">Use el método <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> para obtener una colección de archivos que coincidan con un patrón de búsqueda especificado en todos los directorios.</span><span class="sxs-lookup"><span data-stu-id="c8944-131">Use the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> method to obtain a collection of files that match a specified search pattern in all directories.</span></span> <span data-ttu-id="c8944-132">En este ejemplo se enumeran primero los directorios de nivel superior para detectar las posibles excepciones de acceso no autorizado y luego se enumeran los archivos.</span><span class="sxs-lookup"><span data-stu-id="c8944-132">This example first enumerates the top-level directories to catch possible unauthorized access exceptions, and then enumerates the files.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c8944-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8944-133">See Also</span></span>  
 [<span data-ttu-id="c8944-134">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="c8944-134">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
