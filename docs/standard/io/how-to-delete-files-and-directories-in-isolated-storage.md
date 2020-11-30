---
title: 'Cómo: Eliminar archivos y directorios en almacenamiento aislado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data storage using isolated storage, deleting files and directories
- directories [.NET], isolated storage
- files [.NET], isolated storage
- isolated storage, deleting files and directories
- data stores, deleting files and directories
- stores, creating files and directories
- deleting files within isolated stage file
- storing data using isolated storage, deleting files and directories
- deleting directories within isolated stage file
ms.assetid: 8fcc0dea-435b-4d40-ba4d-ba056265c202
ms.openlocfilehash: ea1d7a460a8867f069aa4b4d915e03d6948e23b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688515"
---
# <a name="how-to-delete-files-and-directories-in-isolated-storage"></a>Cómo: Eliminar archivos y directorios en almacenamiento aislado

Puede eliminar directorios y archivos en un archivo de almacenamiento aislado. Dentro de un almacén, los nombres de archivos y directorios dependen del sistema operativo y se especifican con respecto a la raíz del sistema de archivos virtual. No distinguen mayúsculas de minúsculas en sistemas operativos Windows.  
  
 La clase <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType> proporciona dos métodos para eliminar directorios y archivos: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> y <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>. Se genera una excepción <xref:System.IO.IsolatedStorage.IsolatedStorageException> si trata de eliminar un archivo o directorio que no existe. Si incluye un carácter comodín en el nombre, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> produce una excepción <xref:System.IO.IsolatedStorage.IsolatedStorageException> y <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> produce una excepción <xref:System.ArgumentException>.  
  
 El método <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> produce un error si el directorio contiene archivos o subdirectorios. Puede usar los métodos <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> y <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> para recuperar los archivos y directorios existentes. Para obtener información sobre cómo buscar en el sistema de archivos virtual de un almacén, vea [Cómo: Buscar archivos y directorios existentes en almacenamiento aislado](how-to-find-existing-files-and-directories-in-isolated-storage.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo de código siguiente se crean y luego se eliminan varios directorios y archivos.  
  
 [!code-cpp[Conceptual.IsolatedStorage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.IsolatedStorage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source4.cs#4)]
 [!code-vb[Conceptual.IsolatedStorage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source4.vb#4)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>
- [Almacenamiento aislado](isolated-storage.md)
