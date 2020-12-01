---
title: 'Cómo: Leer y escribir en archivos en almacenamiento aislado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- files, isolated storage
- reading data
- storing data using isolated storage, reading and writing to files
- writing to files within store
- data storage using isolated storage, reading and writing to files
- reading files within store
- isolated storage, reading and writing to files
- data stores, reading and writing to files
- stores, reading and writing to files
ms.assetid: f977ebdc-1b55-475a-bc3d-3376470b08ae
ms.openlocfilehash: 3a8b783cf2cce93cb26b11823d9f565961376ca3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734600"
---
# <a name="how-to-read-and-write-to-files-in-isolated-storage"></a><span data-ttu-id="e3205-102">Cómo: Leer y escribir en archivos en almacenamiento aislado</span><span class="sxs-lookup"><span data-stu-id="e3205-102">How to: Read and Write to Files in Isolated Storage</span></span>

<span data-ttu-id="e3205-103">Para leer o escribir en un archivo de un almacén aislado, use un objeto <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> con un lector de secuencias (objeto <xref:System.IO.StreamReader>) o el escritor de secuencias (objeto <xref:System.IO.StreamWriter>).</span><span class="sxs-lookup"><span data-stu-id="e3205-103">To read from, or write to, a file in an isolated store, use an <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> object with a stream reader (<xref:System.IO.StreamReader> object) or stream writer (<xref:System.IO.StreamWriter> object).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3205-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e3205-104">Example</span></span>  

 <span data-ttu-id="e3205-105">En el ejemplo de código siguiente se obtiene un almacén aislado y se comprueba si existe un archivo denominado TestStore.txt en el almacén.</span><span class="sxs-lookup"><span data-stu-id="e3205-105">The following code example obtains an isolated store and checks whether a file named TestStore.txt exists in the store.</span></span> <span data-ttu-id="e3205-106">Si no existe, crea el archivo y escribe "Hello Isolated Storage" en el archivo.</span><span class="sxs-lookup"><span data-stu-id="e3205-106">If it doesn't exist, it creates the file and writes "Hello Isolated Storage" to the file.</span></span> <span data-ttu-id="e3205-107">Si TestStore.txt ya existe, el código de ejemplo se lee desde el archivo.</span><span class="sxs-lookup"><span data-stu-id="e3205-107">If TestStore.txt already exists, the example code reads from the file.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source5.cs#5)]
 [!code-vb[Conceptual.IsolatedStorage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source5.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="e3205-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3205-108">See also</span></span>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>
- <xref:System.IO.FileMode?displayProperty=nameWithType>
- <xref:System.IO.FileAccess?displayProperty=nameWithType>
- <xref:System.IO.StreamReader?displayProperty=nameWithType>
- <xref:System.IO.StreamWriter?displayProperty=nameWithType>
- [<span data-ttu-id="e3205-109">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="e3205-109">File and Stream I/O</span></span>](index.md)
- [<span data-ttu-id="e3205-110">Almacenamiento aislado</span><span class="sxs-lookup"><span data-stu-id="e3205-110">Isolated Storage</span></span>](isolated-storage.md)
