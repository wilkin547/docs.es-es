---
title: Procedimiento para leer y escribir en archivos en almacenamiento aislado
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: a1ea65b0b8280faf51595b2fe9edcbf17eaabd8f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706691"
---
# <a name="how-to-read-and-write-to-files-in-isolated-storage"></a>Procedimiento para leer y escribir en archivos en almacenamiento aislado
Para leer o escribir en un archivo de un almacén aislado, use un objeto <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> con un lector de secuencias (objeto <xref:System.IO.StreamReader>) o el escritor de secuencias (objeto <xref:System.IO.StreamWriter>).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se obtiene un almacén aislado y se comprueba si existe un archivo denominado TestStore.txt en el almacén. Si no existe, crea el archivo y escribe "Hello Isolated Storage" en el archivo. Si TestStore.txt ya existe, el código de ejemplo se lee desde el archivo.  
  
 [!code-csharp[Conceptual.IsolatedStorage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source5.cs#5)]
 [!code-vb[Conceptual.IsolatedStorage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source5.vb#5)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>
- <xref:System.IO.FileMode?displayProperty=nameWithType>
- <xref:System.IO.FileAccess?displayProperty=nameWithType>
- <xref:System.IO.StreamReader?displayProperty=nameWithType>
- <xref:System.IO.StreamWriter?displayProperty=nameWithType>
- [E/S de archivos y secuencias](../../../docs/standard/io/index.md)
- [Almacenamiento aislado](../../../docs/standard/io/isolated-storage.md)
