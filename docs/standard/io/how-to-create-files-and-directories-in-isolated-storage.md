---
title: "Cómo: Crear archivos y directorios en almacenamiento aislado"
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
- directories [.NET Framework], isolated storage
- files [.NET Framework], isolated storage
- isolated storage, creating files and directories
- data stores, creating files and directories
- data storage using isolated storage, creating files and directories
- stores, creating files and directories
- storing data using isolated storage, creating files and directories
ms.assetid: 2ca4d2a4-809b-4f00-bc08-bf4a64d3a5c3
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cf6295e7d58d03e7b4bf4e0a00cfc509d289e071
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-create-files-and-directories-in-isolated-storage"></a><span data-ttu-id="9d461-102">Cómo: Crear archivos y directorios en almacenamiento aislado</span><span class="sxs-lookup"><span data-stu-id="9d461-102">How to: Create Files and Directories in Isolated Storage</span></span>
<span data-ttu-id="9d461-103">Después de haber obtenido un almacén aislado, puede crear directorios y archivos para almacenar los datos.</span><span class="sxs-lookup"><span data-stu-id="9d461-103">After you have obtained an isolated store, you can create directories and files for storing data.</span></span> <span data-ttu-id="9d461-104">Dentro de un almacén, los nombres de archivos y directorios se especifican con respecto a la raíz del sistema de archivos virtual.</span><span class="sxs-lookup"><span data-stu-id="9d461-104">Within a store, file and directory names are specified with respect to the root of the virtual file system.</span></span>  
  
 <span data-ttu-id="9d461-105">Para crear un directorio, use el método de instancia <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9d461-105">To create a directory, use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> instance method.</span></span> <span data-ttu-id="9d461-106">Si especifica un subdirectorio de un directorio que no existe, se crean dos directorios.</span><span class="sxs-lookup"><span data-stu-id="9d461-106">If you specify a subdirectory of an directory that doesn't exist, both directories are created.</span></span> <span data-ttu-id="9d461-107">Si especifica un directorio que ya existe, el método realiza la devolución sin crear un directorio y no se genera ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="9d461-107">If you specify a directory that already exists, the method returns without creating a directory, and no exception is thrown.</span></span> <span data-ttu-id="9d461-108">Sin embargo, si especifica un nombre de directorio que contiene caracteres no válidos, se produce la excepción <xref:System.IO.IsolatedStorage.IsolatedStorageException>.</span><span class="sxs-lookup"><span data-stu-id="9d461-108">However, if you specify a directory name that contains invalid characters, an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown.</span></span>  
  
 <span data-ttu-id="9d461-109">Para crear un archivo, use el método <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9d461-109">To create a file, use  the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="9d461-110">En el sistema operativo Windows, los nombres de archivos y directorios del almacenamiento aislado distinguen mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9d461-110">In the Windows operating system, isolated storage file and directory names are case-insensitive.</span></span> <span data-ttu-id="9d461-111">Es decir, si crea un archivo denominado `ThisFile.txt` y luego crea otro archivo llamado `THISFILE.TXT`, solo se crea un archivo.</span><span class="sxs-lookup"><span data-stu-id="9d461-111">That is, if you create a file named `ThisFile.txt`, and then create another file named `THISFILE.TXT`, only one file is created.</span></span> <span data-ttu-id="9d461-112">El nombre de archivo mantiene las mayúsculas y minúsculas originales para la presentación.</span><span class="sxs-lookup"><span data-stu-id="9d461-112">The file name keeps its original casing for display purposes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d461-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9d461-113">Example</span></span>  
 <span data-ttu-id="9d461-114">En el ejemplo de código siguiente se muestra cómo crear archivos y directorios en un almacén aislado.</span><span class="sxs-lookup"><span data-stu-id="9d461-114">The following code example illustrates how to create files and directories in an isolated store.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="9d461-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d461-115">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
 [<span data-ttu-id="9d461-116">Almacenamiento aislado</span><span class="sxs-lookup"><span data-stu-id="9d461-116">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
