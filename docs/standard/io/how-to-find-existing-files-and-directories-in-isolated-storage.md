---
title: "Cómo: Buscar archivos y directorios existentes en almacenamiento aislado"
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
- stores, finding files and directories
- locating files in isolated storage file
- directories [.NET Framework], isolated storage
- isolated storage, finding files and directories
- data storage using isolated storage, finding files and directories
- files [.NET Framework], isolated storage
- data stores, finding files and directories
- locating directories in isolated storage file
- storing data using isolated storage, finding files and directories
ms.assetid: eb28458a-6161-4e7a-9ada-30ef93761b5c
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 656c390358b6f6a671cf3ef11ea7be75f897d21c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-existing-files-and-directories-in-isolated-storage"></a>Cómo: Buscar archivos y directorios existentes en almacenamiento aislado
Para buscar un directorio en el almacenamiento aislado, use la <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=nameWithType> método. Este método toma una cadena que representa un patrón de búsqueda. Puede usar el carácter único (?) y varios caracteres (*) caracteres comodín en el patrón de búsqueda, pero los caracteres comodín deben aparecer en la parte final del nombre. Por ejemplo, `directory1/*ect*` es una cadena de búsqueda válida, pero `*ect*/directory2` no es.  
  
 Para buscar un archivo, utilice el <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=nameWithType> método. La restricción de caracteres comodín en cadenas de búsqueda que se aplica a <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> también se aplica a <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>.  
  
 Ninguno de estos métodos es recursiva; la <xref:System.IO.IsolatedStorage.IsolatedStorageFile> clase no proporciona ningún método para enumerar todos los directorios o archivos en el almacén. Sin embargo, los métodos de recursivas se muestran en el ejemplo de código siguiente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo crear archivos y directorios en un almacén aislado. En primer lugar, se recuperan y se coloca en un almacén que está aislado de usuario, dominio y ensamblado el `isoStore` variable. El <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A> método se usa para configurar unos cuantos directorios distintos y el <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29> constructor crea algunos archivos en estos directorios. El código recorre, a continuación, los resultados de la `GetAllDirectories` método. Este método usa <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> para buscar todos los nombres de directorio en el directorio actual. Estos nombres se almacenan en una matriz y, a continuación, `GetAllDirectories` llama a sí misma, pasando cada directorio que ha encontrado. Como resultado, se devuelven todos los nombres de directorio en una matriz. A continuación, el código llama a la `GetAllFiles` método. Este método llama a `GetAllDirectories` para averiguar los nombres de todos los directorios y, a continuación, comprueba cada directorio de archivos mediante el uso de la <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> método. El resultado se devuelve en una matriz para su presentación.  
  
 [!code-cpp[Conceptual.IsolatedStorage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source8.cpp#9)]
 [!code-csharp[Conceptual.IsolatedStorage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source8.cs#9)]
 [!code-vb[Conceptual.IsolatedStorage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source8.vb#9)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [Almacenamiento aislado](../../../docs/standard/io/isolated-storage.md)
