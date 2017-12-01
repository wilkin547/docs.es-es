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
# <a name="how-to-delete-files-and-directories-in-isolated-storage"></a>Cómo: Eliminar archivos y directorios en almacenamiento aislado
Puede eliminar directorios y archivos en un archivo de almacenamiento aislado. Dentro de un almacén, los nombres de archivo y directorio dependen del sistema operativo y se especifican en relación con la raíz del sistema de archivos virtual. No distinguen mayúsculas de minúsculas en sistemas operativos Windows.  
  
 El <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType> clase proporciona dos métodos para eliminar archivos y directorios: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> y <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>. Un <xref:System.IO.IsolatedStorage.IsolatedStorageException> excepción se produce si intenta eliminar un archivo o directorio que no existe. Si incluye un carácter comodín en el nombre, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> produce una <xref:System.IO.IsolatedStorage.IsolatedStorageException> excepción, y <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> produce una <xref:System.ArgumentException> excepción.  
  
 El <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> método produce un error si el directorio contiene archivos o subdirectorios. Puede usar el <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> y <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> métodos para recuperar los archivos y directorios existentes. Para obtener más información acerca de cómo buscar el sistema de archivos virtual de un almacén, vea [Cómo: buscar archivos y directorios existentes en almacenamiento aislado](../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se crea y, a continuación, elimina varios directorios y archivos.  
  
 [!code-cpp[Conceptual.IsolatedStorage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.IsolatedStorage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source4.cs#4)]
 [!code-vb[Conceptual.IsolatedStorage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source4.vb#4)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>  
 [Almacenamiento aislado](../../../docs/standard/io/isolated-storage.md)
