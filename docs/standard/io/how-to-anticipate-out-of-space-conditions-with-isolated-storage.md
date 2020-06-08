---
title: 'Cómo: Prever condiciones de espacio insuficiente con almacenamiento aislado'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data stores, quotas
- isolated storage, quotas
- quantity of isolated storage used
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
ms.openlocfilehash: bdc2cee343e9d9be44230e84ff45d6fa54901f48
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288594"
---
# <a name="how-to-anticipate-out-of-space-conditions-with-isolated-storage"></a>Cómo: Prever condiciones de espacio insuficiente con almacenamiento aislado

El código que usa el almacenamiento aislado está restringido por una [cuota](isolated-storage.md#quotas) que especifica el tamaño máximo para el compartimiento de datos en que se encuentran los directorios y los archivos del almacenamiento aislado. La cuota se define mediante la directiva de seguridad y la pueden configurar los administradores. Si se supera el tamaño máximo permitido al intentar escribir datos, se genera la excepción <xref:System.IO.IsolatedStorage.IsolatedStorageException> y se produce un error en la operación. Esto ayuda a evitar los ataques de denegación de servicio malintencionados que pudieron provocar que la aplicación rechazara solicitudes porque se llenara el almacén de datos.

Para ayudarlo a determinar si un intento de escritura determinado puede presentar errores por este motivo, la clase <xref:System.IO.IsolatedStorage.IsolatedStorage> proporciona tres propiedades de solo lectura: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A> y <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>. Puede utilizar estas propiedades para determinar si escribir en el almacén hará que se supere el tamaño máximo permitido del almacén. Tenga en cuenta que se puede acceder al almacenamiento aislado de forma simultánea; por tanto, al calcular la cantidad de almacenamiento restante, el tiempo durante el cual se intenta escribir en el almacén podría consumir el espacio de almacenamiento. Sin embargo, puede usar el tamaño máximo del almacén para ayudar a determinar si el límite superior del almacenamiento disponible está a punto de alcanzarse.

La propiedad <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> depende de la evidencia del ensamblado para que funcione correctamente. Por este motivo, debe recuperar esta propiedad solo en objetos <xref:System.IO.IsolatedStorage.IsolatedStorageFile> que se crearon con los métodos <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> o <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>. Los objetos <xref:System.IO.IsolatedStorage.IsolatedStorageFile> creados de otra forma (por ejemplo, los objetos devueltos por el método <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A>) no devolverán un tamaño máximo preciso.

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se obtiene un almacén aislado, se crean algunos archivos y se recupera la propiedad <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>. El espacio restante se notifica en bytes.

[!code-cpp[Conceptual.IsolatedStorage#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source7.cpp#8)]
[!code-csharp[Conceptual.IsolatedStorage#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source7.cs#8)]
[!code-vb[Conceptual.IsolatedStorage#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source7.vb#8)]

## <a name="see-also"></a>Vea también

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- [Almacenamiento aislado](isolated-storage.md)
- [Cómo: Obtener los almacenes de almacenamiento aislado](how-to-obtain-stores-for-isolated-storage.md)
