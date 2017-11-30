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
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8b8a48473bf9ac91b89657d00d27031255491353
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-files-and-directories-in-isolated-storage"></a><span data-ttu-id="1a3af-102">Cómo: Crear archivos y directorios en almacenamiento aislado</span><span class="sxs-lookup"><span data-stu-id="1a3af-102">How to: Create Files and Directories in Isolated Storage</span></span>
<span data-ttu-id="1a3af-103">Después de haber obtenido un almacén aislado, puede crear directorios y archivos para almacenar los datos.</span><span class="sxs-lookup"><span data-stu-id="1a3af-103">After you have obtained an isolated store, you can create directories and files for storing data.</span></span> <span data-ttu-id="1a3af-104">Dentro de un almacén, se especifican los nombres de archivos y directorios con respecto a la raíz del sistema de archivos virtual.</span><span class="sxs-lookup"><span data-stu-id="1a3af-104">Within a store, file and directory names are specified with respect to the root of the virtual file system.</span></span>  
  
 <span data-ttu-id="1a3af-105">Para crear un directorio, use el <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> método de instancia.</span><span class="sxs-lookup"><span data-stu-id="1a3af-105">To create a directory, use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> instance method.</span></span> <span data-ttu-id="1a3af-106">Si especifica un subdirectorio de un directorio que no existe, se crean dos directorios.</span><span class="sxs-lookup"><span data-stu-id="1a3af-106">If you specify a subdirectory of an directory that doesn't exist, both directories are created.</span></span> <span data-ttu-id="1a3af-107">Si especifica un directorio que ya existe, el método devuelve sin crear un directorio y se inicia ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="1a3af-107">If you specify a directory that already exists, the method returns without creating a directory, and no exception is thrown.</span></span> <span data-ttu-id="1a3af-108">Sin embargo, si especifica un nombre de directorio que contiene caracteres no válidos, un <xref:System.IO.IsolatedStorage.IsolatedStorageException> se produce la excepción.</span><span class="sxs-lookup"><span data-stu-id="1a3af-108">However, if you specify a directory name that contains invalid characters, an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown.</span></span>  
  
 <span data-ttu-id="1a3af-109">Para crear un archivo, use la <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="1a3af-109">To create a file, use  the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="1a3af-110">En el sistema operativo de Windows, el archivo de almacenamiento aislado y el directorio nombres distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1a3af-110">In the Windows operating system, isolated storage file and directory names are case-insensitive.</span></span> <span data-ttu-id="1a3af-111">Es decir, si crea un archivo denominado `ThisFile.txt`y, a continuación, cree otro archivo denominado `THISFILE.TXT`, se crea un solo archivo.</span><span class="sxs-lookup"><span data-stu-id="1a3af-111">That is, if you create a file named `ThisFile.txt`, and then create another file named `THISFILE.TXT`, only one file is created.</span></span> <span data-ttu-id="1a3af-112">El nombre de archivo mantiene sus mayúsculas y minúsculas original para la presentación.</span><span class="sxs-lookup"><span data-stu-id="1a3af-112">The file name keeps its original casing for display purposes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a3af-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1a3af-113">Example</span></span>  
 <span data-ttu-id="1a3af-114">En el ejemplo de código siguiente se muestra cómo crear archivos y directorios en un almacén aislado.</span><span class="sxs-lookup"><span data-stu-id="1a3af-114">The following code example illustrates how to create files and directories in an isolated store.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1a3af-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a3af-115">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
 [<span data-ttu-id="1a3af-116">Almacenamiento aislado</span><span class="sxs-lookup"><span data-stu-id="1a3af-116">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
