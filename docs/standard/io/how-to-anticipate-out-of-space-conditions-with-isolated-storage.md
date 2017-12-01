---
title: "Cómo: Prever condiciones de espacio insuficiente con almacenamiento aislado"
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
- data stores, quotas
- isolated storage, quotas
- quanitity of isolated storage used
- limit on isolated storage used
- stores, quotas
- stores, out of space conditions
- data storage using isolated storage, quotas
- storing data using isolated storage, quotas
- space remaining in isolated storage
- data stores, out of space conditions
- storing data using isolated storage, out of space conditions
- quotas for isolated storage
- isolated storage, out of space conditions
- data storage using isolated storage, out of space conditions
ms.assetid: e35d4535-3732-421e-b1a3-37412e036145
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d813522d0aeb9bf37582c167760d44268df27039
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-anticipate-out-of-space-conditions-with-isolated-storage"></a>Cómo: Prever condiciones de espacio insuficiente con almacenamiento aislado
El código que usa almacenamiento aislado está restringido por un [cuota](../../../docs/standard/io/isolated-storage.md#quotas) que especifica el tamaño máximo para el compartimiento de datos en el que aislado de archivos de almacenamiento y existen. La cuota se define mediante la directiva de seguridad y se puede configurar los administradores. Si se supera el tamaño al intentar escribir datos, el número máximo un <xref:System.IO.IsolatedStorage.IsolatedStorageException> se produce la excepción y se produce un error en la operación. Esto ayuda a evitar los ataques de denegación de servicio malintencionados que pudieron provocar que la aplicación rechazara solicitudes porque se ha llenado el almacén de datos.  
  
 Para ayudarle a determinar si un intento de escritura determinado es probable que genere un error por este motivo, el <xref:System.IO.IsolatedStorage.IsolatedStorage> clase proporciona tres propiedades de solo lectura: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A>, y <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>. Puede utilizar estas propiedades para determinar si escribir en el almacén hará que el tamaño máximo permitido del almacén se ha superado. Tenga en cuenta que el almacenamiento aislado puede acceder simultáneamente; por lo tanto, al calcular la cantidad de almacenamiento restante, el espacio de almacenamiento que pueden consumir el tiempo que se intenta escribir en el almacén. Sin embargo, puede usar el tamaño máximo del almacén para ayudar a determinar si el límite superior del almacenamiento disponible está a punto de alcanzarse.  
  
 El <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> propiedad depende de la evidencia desde el ensamblado para que funcione correctamente. Por este motivo, debe recuperar esta propiedad solo en <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objetos que se crearon utilizando la <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, o <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> método. <xref:System.IO.IsolatedStorage.IsolatedStorageFile>objetos que se crearon en ninguna otra forma (por ejemplo, los objetos que se han devuelto desde el <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> método) no devolverán un tamaño máximo preciso.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se obtiene un almacén aislado, crea unos cuantos archivos y recupera el <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A> propiedad. Se notifica el espacio restante en bytes.  
  
 [!code-cpp[Conceptual.IsolatedStorage#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source7.cpp#8)]
 [!code-csharp[Conceptual.IsolatedStorage#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source7.cs#8)]
 [!code-vb[Conceptual.IsolatedStorage#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source7.vb#8)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [Almacenamiento aislado](../../../docs/standard/io/isolated-storage.md)  
 [Cómo: Obtener los almacenes de almacenamiento aislado](../../../docs/standard/io/how-to-obtain-stores-for-isolated-storage.md)
