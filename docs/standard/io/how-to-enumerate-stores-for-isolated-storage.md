---
title: "Cómo: Enumerar los almacenes de almacenamiento aislado"
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
- enumerating stores
- data storage using isolated storage, enumerating stores
- storing data using isolated storage, enumerating stores
- stores, enumerating
- isolated storage, enumerating stores
- data stores, enumerating
ms.assetid: 0fcf279a-f241-48f0-8034-2e3d331f1fcb
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8f8863f1d8b3c7f4ed8f65f8f8eb3e8af51b0405
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enumerate-stores-for-isolated-storage"></a>Cómo: Enumerar los almacenes de almacenamiento aislado
Puede enumerar aislados todos los almacenes del usuario actual utilizando el <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType> método estático. Este método toma una <xref:System.IO.IsolatedStorage.IsolatedStorageScope> valor determinado y devuelve un <xref:System.IO.IsolatedStorage.IsolatedStorageFile> enumerador. Para enumerar los almacenes, debe tener la <xref:System.Security.Permissions.IsolatedStorageFilePermission> permiso que especifica la <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> valor. Si se llama a la <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> método con el <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> valor, devuelve una matriz de <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objetos que están definidos para el usuario actual.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se obtiene un almacén aislado por usuario y ensamblado, crea unos cuantos archivos y recupera los archivos mediante el <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> método.  
  
 [!code-csharp[Conceptual.IsolatedStorage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source2.cs#2)]
 [!code-vb[Conceptual.IsolatedStorage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [Almacenamiento aislado](../../../docs/standard/io/isolated-storage.md)
