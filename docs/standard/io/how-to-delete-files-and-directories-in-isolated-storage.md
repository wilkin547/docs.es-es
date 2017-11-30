---
title: "Cómo: Eliminar archivos y directorios en almacenamiento aislado"
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
- cpp
helpviewer_keywords:
- data storage using isolated storage, deleting files and directories
- directories [.NET Framework], isolated storage
- files [.NET Framework], isolated storage
- isolated storage, deleting files and directories
- data stores, deleting files and directories
- stores, creating files and directories
- deleting files within isolated stage file
- storing data using isolated storage, deleting files and directories
- deleting directories within isolated stage file
ms.assetid: 8fcc0dea-435b-4d40-ba4d-ba056265c202
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 971f27cd25cbe4be3ca3fad6283ab32d4f6db0ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-delete-files-and-directories-in-isolated-storage"></a><span data-ttu-id="3ee2f-102">Cómo: Eliminar archivos y directorios en almacenamiento aislado</span><span class="sxs-lookup"><span data-stu-id="3ee2f-102">How to: Delete Files and Directories in Isolated Storage</span></span>
<span data-ttu-id="3ee2f-103">Puede eliminar directorios y archivos en un archivo de almacenamiento aislado.</span><span class="sxs-lookup"><span data-stu-id="3ee2f-103">You can delete directories and files within an isolated storage file.</span></span> <span data-ttu-id="3ee2f-104">Dentro de un almacén, los nombres de archivo y directorio dependen del sistema operativo y se especifican en relación con la raíz del sistema de archivos virtual.</span><span class="sxs-lookup"><span data-stu-id="3ee2f-104">Within a store, file and directory names are operating-system dependent and are specified as relative to the root of the virtual file system.</span></span> <span data-ttu-id="3ee2f-105">No distinguen mayúsculas de minúsculas en sistemas operativos Windows.</span><span class="sxs-lookup"><span data-stu-id="3ee2f-105">They are not case-sensitive on Windows operating systems.</span></span>  
  
 <span data-ttu-id="3ee2f-106">El <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType> clase proporciona dos métodos para eliminar archivos y directorios: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> y <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="3ee2f-106">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType> class supplies two methods for deleting directories and files: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>.</span></span> <span data-ttu-id="3ee2f-107">Un <xref:System.IO.IsolatedStorage.IsolatedStorageException> excepción se produce si intenta eliminar un archivo o directorio que no existe.</span><span class="sxs-lookup"><span data-stu-id="3ee2f-107">An <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown if you try to delete a file or directory that does not exist.</span></span> <span data-ttu-id="3ee2f-108">Si incluye un carácter comodín en el nombre, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> produce una <xref:System.IO.IsolatedStorage.IsolatedStorageException> excepción, y <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> produce una <xref:System.ArgumentException> excepción.</span><span class="sxs-lookup"><span data-stu-id="3ee2f-108">If you include a wildcard character in the name, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> throws an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception, and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="3ee2f-109">El <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> método produce un error si el directorio contiene archivos o subdirectorios.</span><span class="sxs-lookup"><span data-stu-id="3ee2f-109">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> method fails if the directory contains any files or subdirectories.</span></span> <span data-ttu-id="3ee2f-110">Puede usar el <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> y <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> métodos para recuperar los archivos y directorios existentes.</span><span class="sxs-lookup"><span data-stu-id="3ee2f-110">You can use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> methods to retrieve the existing files and directories.</span></span> <span data-ttu-id="3ee2f-111">Para obtener más información acerca de cómo buscar el sistema de archivos virtual de un almacén, vea [Cómo: buscar archivos y directorios existentes en almacenamiento aislado](../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md).</span><span class="sxs-lookup"><span data-stu-id="3ee2f-111">For more information about searching the virtual file system of a store, see [How to: Find Existing Files and Directories in Isolated Storage](../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ee2f-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3ee2f-112">Example</span></span>  
 <span data-ttu-id="3ee2f-113">En el ejemplo de código siguiente se crea y, a continuación, elimina varios directorios y archivos.</span><span class="sxs-lookup"><span data-stu-id="3ee2f-113">The following code example creates and then deletes several directories and files.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.IsolatedStorage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source4.cs#4)]
 [!code-vb[Conceptual.IsolatedStorage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="3ee2f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ee2f-114">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>  
 [<span data-ttu-id="3ee2f-115">Almacenamiento aislado</span><span class="sxs-lookup"><span data-stu-id="3ee2f-115">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
