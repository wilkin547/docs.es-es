---
title: 'Cómo: Copiar archivos con un modelo específico en un directorio'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: f205d2ad-bbe5-4d55-8a40-acda21aa82dd
ms.openlocfilehash: ee3951e967436a1b8aec09b8e42dc6d1b547bc02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74348854"
---
# <a name="how-to-copy-files-with-a-specific-pattern-to-a-directory-in-visual-basic"></a><span data-ttu-id="2182d-102">Cómo: Copiar archivos con un modelo específico en un directorio en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2182d-102">How to: Copy Files with a Specific Pattern to a Directory in Visual Basic</span></span>

<span data-ttu-id="2182d-103">El método <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> devuelve una colección de cadenas de solo lectura que representan los nombres de ruta de acceso de los archivos.</span><span class="sxs-lookup"><span data-stu-id="2182d-103">The <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> method returns a read-only collection of strings representing the path names for the files.</span></span> <span data-ttu-id="2182d-104">Puede usar el parámetro `wildCards` para especificar un patrón concreto.</span><span class="sxs-lookup"><span data-stu-id="2182d-104">You can use the `wildCards` parameter to specify a specific pattern.</span></span>  
  
 <span data-ttu-id="2182d-105">Si no se encuentran archivos coincidentes, se devuelve una colección vacía.</span><span class="sxs-lookup"><span data-stu-id="2182d-105">An empty collection is returned if no matching files are found.</span></span>  
  
 <span data-ttu-id="2182d-106">Puede usar el método <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A> para copiar los archivos en un directorio.</span><span class="sxs-lookup"><span data-stu-id="2182d-106">You can use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A> method to copy the files to a directory.</span></span>  
  
### <a name="to-copy-files-with-a-specific-pattern-to-a-directory"></a><span data-ttu-id="2182d-107">Para copiar archivos con un patrón específico en un directorio</span><span class="sxs-lookup"><span data-stu-id="2182d-107">To copy files with a specific pattern to a directory</span></span>  
  
1. <span data-ttu-id="2182d-108">Use le método `GetFiles` para devolver la lista de archivos.</span><span class="sxs-lookup"><span data-stu-id="2182d-108">Use the `GetFiles` method to return the list of files.</span></span> <span data-ttu-id="2182d-109">En este ejemplo se devuelven todos los archivos .rtf del directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="2182d-109">This example returns all .rtf files in the specified directory.</span></span>  
  
     [!code-vb[VbFileIOMisc#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#36)]  
  
2. <span data-ttu-id="2182d-110">Use el método `CopyFile` para copiar los archivos.</span><span class="sxs-lookup"><span data-stu-id="2182d-110">Use the `CopyFile` method to copy the files.</span></span> <span data-ttu-id="2182d-111">En este ejemplo se copian los archivos en el directorio denominado `testdirectory`.</span><span class="sxs-lookup"><span data-stu-id="2182d-111">This example copies the files to the directory named `testdirectory`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#88)]  
  
3. <span data-ttu-id="2182d-112">Cierre la instrucción `For` con una instrucción `Next` .</span><span class="sxs-lookup"><span data-stu-id="2182d-112">Close the `For` statement with a `Next` statement.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#89)]  
  
## <a name="example"></a><span data-ttu-id="2182d-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2182d-113">Example</span></span>  

 <span data-ttu-id="2182d-114">En el ejemplo siguiente, que presenta los fragmentos de código anteriores de forma completa, se copian todos los archivos .rtf del directorio especificado en el directorio denominado `testdirectory`.</span><span class="sxs-lookup"><span data-stu-id="2182d-114">The following example, which presents the above snippets in complete form, copies all .rtf files in the specified directory to the directory named `testdirectory`.</span></span>  
  
 [!code-vb[VbFileIOMisc#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#37)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="2182d-115">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2182d-115">.NET Framework Security</span></span>  

 <span data-ttu-id="2182d-116">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="2182d-116">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="2182d-117">La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="2182d-117">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="2182d-118">La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="2182d-118">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="2182d-119">El directorio no existe (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="2182d-119">The directory does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
- <span data-ttu-id="2182d-120">El directorio apunta a un archivo existente (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="2182d-120">The directory points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="2182d-121">La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="2182d-121">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="2182d-122">Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="2182d-122">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="2182d-123">El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="2182d-123">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span> <span data-ttu-id="2182d-124">El usuario no tiene los permisos necesarios (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="2182d-124">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2182d-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2182d-125">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>
- <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>
- [<span data-ttu-id="2182d-126">Buscar subdirectorios con un modelo concreto</span><span class="sxs-lookup"><span data-stu-id="2182d-126">How to: Find Subdirectories with a Specific Pattern</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)
- [<span data-ttu-id="2182d-127">Solución de problemas: Leer y escribir en archivos de texto</span><span class="sxs-lookup"><span data-stu-id="2182d-127">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
- [<span data-ttu-id="2182d-128">Obtener la colección de archivos de un directorio</span><span class="sxs-lookup"><span data-stu-id="2182d-128">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
