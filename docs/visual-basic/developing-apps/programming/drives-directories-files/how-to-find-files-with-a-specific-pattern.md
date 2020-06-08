---
title: 'Cómo: Buscar archivos con un modelo concreto'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], finding
- pattern matching
- patterns, matching
ms.assetid: 25e3b71d-b844-4293-9e4e-f06c5836b5cc
ms.openlocfilehash: 71073672ed14cb2d5df5b5365266b718c59cb18f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401646"
---
# <a name="how-to-find-files-with-a-specific-pattern-in-visual-basic"></a><span data-ttu-id="c7aaf-102">Cómo: Buscar archivos con un modelo concreto en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7aaf-102">How to: Find Files with a Specific Pattern in Visual Basic</span></span>

<span data-ttu-id="c7aaf-103">El método <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> devuelve una colección de cadenas de solo lectura que representan los nombres de ruta de acceso de los archivos.</span><span class="sxs-lookup"><span data-stu-id="c7aaf-103">The <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> method returns a read-only collection of strings representing the path names for the files.</span></span> <span data-ttu-id="c7aaf-104">Puede usar el parámetro `wildCards` para especificar un patrón concreto.</span><span class="sxs-lookup"><span data-stu-id="c7aaf-104">You can use the `wildCards` parameter to specify a specific pattern.</span></span> <span data-ttu-id="c7aaf-105">Si quiere incluir los subdirectorios en la búsqueda, establezca el parámetro `searchType` en `SearchOption.SearchAllSubDirectories`.</span><span class="sxs-lookup"><span data-stu-id="c7aaf-105">If you would like to include subdirectories in the search, set the `searchType` parameter to `SearchOption.SearchAllSubDirectories`.</span></span>  
  
 <span data-ttu-id="c7aaf-106">Si no se encuentran archivos que coincidan con el patrón especificado, se devuelve una colección vacía.</span><span class="sxs-lookup"><span data-stu-id="c7aaf-106">An empty collection is returned if no files matching the specified pattern are found.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7aaf-107">Para obtener información sobre la devolución de una lista de archivos con la clase `DirectoryInfo` del espacio de nombres `System.IO`, consulte <xref:System.IO.DirectoryInfo.GetFiles%2A>.</span><span class="sxs-lookup"><span data-stu-id="c7aaf-107">For information about returning a file list by using the `DirectoryInfo` class of the `System.IO` namespace, see <xref:System.IO.DirectoryInfo.GetFiles%2A>.</span></span>  
  
### <a name="to-find-files-with-a-specified-pattern"></a><span data-ttu-id="c7aaf-108">Para buscar archivos con un modelo especificado</span><span class="sxs-lookup"><span data-stu-id="c7aaf-108">To find files with a specified pattern</span></span>  
  
- <span data-ttu-id="c7aaf-109">Use el método `GetFiles`, proporcionando el nombre y la ruta de acceso del directorio en el que quiere buscar y especificando el modelo.</span><span class="sxs-lookup"><span data-stu-id="c7aaf-109">Use the `GetFiles` method, supplying the name and path of the directory you want to search and specifying the pattern.</span></span> <span data-ttu-id="c7aaf-110">En el ejemplo siguiente se devuelven todos los archivos situados en el directorio que tienen la extensión `.dll` y los agrega a `ListBox1`.</span><span class="sxs-lookup"><span data-stu-id="c7aaf-110">The following example returns all files with the extension `.dll` in the directory and adds them to `ListBox1`.</span></span>  
  
     [!code-vb[VbFileIOMisc#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#4)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="c7aaf-111">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c7aaf-111">.NET Framework Security</span></span>  

 <span data-ttu-id="c7aaf-112">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="c7aaf-112">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="c7aaf-113">La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="c7aaf-113">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="c7aaf-114">La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="c7aaf-114">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="c7aaf-115">`directory` no existe (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="c7aaf-115">`directory` does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
- <span data-ttu-id="c7aaf-116">`directory` apunta a un archivo existente (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="c7aaf-116">`directory` points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="c7aaf-117">La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="c7aaf-117">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="c7aaf-118">Un nombre de archivo o de carpeta de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="c7aaf-118">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="c7aaf-119">El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="c7aaf-119">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="c7aaf-120">El usuario no tiene los permisos necesarios (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="c7aaf-120">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7aaf-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7aaf-121">See also</span></span>

- <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>
- [<span data-ttu-id="c7aaf-122">Buscar subdirectorios con un modelo concreto</span><span class="sxs-lookup"><span data-stu-id="c7aaf-122">How to: Find Subdirectories with a Specific Pattern</span></span>](how-to-find-subdirectories-with-a-specific-pattern.md)
- [<span data-ttu-id="c7aaf-123">Solución de problemas: Leer y escribir en archivos de texto</span><span class="sxs-lookup"><span data-stu-id="c7aaf-123">Troubleshooting: Reading from and Writing to Text Files</span></span>](troubleshooting-reading-from-and-writing-to-text-files.md)
- [<span data-ttu-id="c7aaf-124">Obtener la colección de archivos de un directorio</span><span class="sxs-lookup"><span data-stu-id="c7aaf-124">How to: Get the Collection of Files in a Directory</span></span>](how-to-get-the-collection-of-files-in-a-directory.md)
