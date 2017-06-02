---
title: "C&#243;mo: Prever condiciones de espacio insuficiente con almacenamiento aislado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "almacenes de datos, cuotas"
  - "almacenamiento aislado, cuotas"
  - "cantidad de almacenamiento aislado utilizada"
  - "límite de la cantidad de almacenamiento aislado utilizada"
  - "almacenes, cuotas"
  - "almacenes, condiciones de espacio insuficiente"
  - "almacenamiento de datos mediante almacenamiento aislado, cuotas"
  - "almacenar datos mediante almacenamiento aislado, cuotas"
  - "espacio restante de almacenamiento aislado"
  - "almacenes de datos, condiciones de espacio insuficiente"
  - "almacenar datos mediante almacenamiento aislado, condiciones de espacio insuficiente"
  - "cuotas de almacenamiento aislado"
  - "almacenamiento aislado, condiciones de espacio insuficiente"
  - "almacenar datos con almacenamiento aislado, condiciones de espacio insuficiente"
ms.assetid: e35d4535-3732-421e-b1a3-37412e036145
caps.latest.revision: 17
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Prever condiciones de espacio insuficiente con almacenamiento aislado
El código que usa almacenamiento aislado está restringido por una [cuota](../../../docs/standard/io/isolated-storage.md#quotas) que especifica el tamaño máximo del compartimiento de datos en el que se ubican los archivos y directorios de almacenamiento aislado.  La cuota está definida por la directiva de seguridad y se configura por los administradores.  Si el se supera el tamaño máximo al intentar escribir datos, se produce una excepción de <xref:System.IO.IsolatedStorage.IsolatedStorageException> y se produce un error en la operación.  Esto contribuye a impedir ataques de denegación de servicio malintencionados que podrían hacer que la aplicación rechazara solicitudes porque se ha llenado el almacenamiento de datos.  
  
 Para ayudarle a determinar si es probable que un intento de escritura determinado genere un error por este motivo, la clase <xref:System.IO.IsolatedStorage.IsolatedStorage> proporciona tres propiedades de solo lectura: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A> y <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>.  Puede utilizar estas propiedades para determinar si la escritura en el almacén hará el tamaño máximo permitido del almacén que se supere.  Tenga en cuenta que el almacenamiento aislado se puede lograr simultáneamente; por consiguiente, cuando se calcula la cantidad de almacenamiento restante, el espacio de almacenamiento podría ser utilizado en el momento en que se intenta escribir en el almacén.  Sin embargo, puede utilizar el tamaño máximo del almacén para ayudar a determinar si el límite superior del almacenamiento disponible está a punto de alcanzarse.  
  
 La propiedad de <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> depende de prueba del ensamblado para funcionar correctamente.  Por este motivo, debe recuperar esta propiedad únicamente en los objetos de <xref:System.IO.IsolatedStorage.IsolatedStorageFile> creados mediante <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, o un método de <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> .  los objetos de<xref:System.IO.IsolatedStorage.IsolatedStorageFile> creados de cualquier otra forma \(por ejemplo, los objetos que se devuelva el método de <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> \) no devolverán un tamaño máximo preciso.  
  
## Ejemplo  
 En el ejemplo de código siguiente se obtiene un almacén aislado, se crean unos cuantos archivos y se recupera la propiedad <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>.  El espacio restante se indica en bytes.  
  
 [!code-cpp[Conceptual.IsolatedStorage#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source7.cpp#8)]
 [!code-csharp[Conceptual.IsolatedStorage#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source7.cs#8)]
 [!code-vb[Conceptual.IsolatedStorage#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source7.vb#8)]  
  
## Vea también  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 [Almacenamiento aislado](../../../docs/standard/io/isolated-storage.md)   
 [Cómo: Obtener los almacenes de almacenamiento aislado](../../../docs/standard/io/how-to-obtain-stores-for-isolated-storage.md)