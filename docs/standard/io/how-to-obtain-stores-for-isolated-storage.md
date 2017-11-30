---
title: "Cómo: Obtener los almacenes de almacenamiento aislado"
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
- stores, obtaining
- storing data using isolated storage, obtaining stores
- isolated storage, obtaining stores
- data stores, obtaining
- data storage using isolated storage, obtaining stores
ms.assetid: fcb6b178-d526-47c4-b029-e946f880f9db
caps.latest.revision: "19"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bb0b877aa0f4cee36bd1f8c1cea624cf9368fbaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-stores-for-isolated-storage"></a>Cómo: Obtener los almacenes de almacenamiento aislado
Un almacén aislado expone un sistema de archivos virtual dentro de un compartimiento de datos. La <xref:System.IO.IsolatedStorage.IsolatedStorageFile> clase proporciona una serie de métodos para interactuar con un almacén aislado. Para crear y recuperar almacenes, <xref:System.IO.IsolatedStorage.IsolatedStorageFile> proporciona tres métodos estáticos:  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>Devuelve el almacenamiento que está aislado por usuario y ensamblado.  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>Devuelve el almacenamiento que está aislado por dominio y ensamblado.  
  
     Ambos métodos recuperan un almacén que pertenece al código desde el que se les llama.  
  
-   El método estático <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> devuelve un almacén aislado que se especifica pasando una combinación de parámetros de ámbito.  
  
 El código siguiente devuelve un almacén aislado por usuario, dominio y ensamblado.  
  
 [!code-cpp[Conceptual.IsolatedStorage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#6)]
 [!code-csharp[Conceptual.IsolatedStorage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#6)]
 [!code-vb[Conceptual.IsolatedStorage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#6)]  
  
 Puede usar el <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> método para especificar que un almacén se debe trasladar con un perfil de usuario móvil. Para obtener más información sobre cómo configurar esta opción, vea [tipos de aislamiento](../../../docs/standard/io/types-of-isolation.md).  
  
 Almacenes aislados que se obtienen del interior de distintos ensamblados son, de forma predeterminada, los almacenes diferentes. Pueda acceder al almacén de otro ensamblado o dominio pasando de la evidencia de ensamblado o dominio de los parámetros de la <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> método. Esto requiere el permiso para tener acceso al almacenamiento aislado según la identidad de dominio de aplicación. Para obtener más información, consulte el <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> sobrecargas del método.  
  
 El <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, y <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> métodos devuelven un <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objeto. Para ayudarle a decidir qué tipo de aislamiento es más adecuado para su situación, vea [tipos de aislamiento](../../../docs/standard/io/types-of-isolation.md). Cuando se tiene un objeto de archivo de almacenamiento aislado, puede usar los métodos de almacenamiento aislado para leer, escribir, crear y eliminar archivos y directorios.  
  
 No hay ningún mecanismo que evita que un código de pasar un <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objeto al código que no tiene suficientes derechos de acceso para obtener el almacén propiamente dicho. Las identidades del dominio y ensamblado y los permisos de almacenamiento aislado sólo se comprueban cuando una referencia a un <xref:System.IO.IsolatedStorage.IsolatedStorage> objeto se obtiene, normalmente, en la <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, o <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> método. Protección de las referencias a <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objetos es, por lo tanto, la responsabilidad del código que utiliza estas referencias.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente proporciona un ejemplo sencillo de una clase que obtiene un almacén aislado por usuario y ensamblado. El código se puede cambiar para recuperar un almacén que está aislado por usuario, dominio y ensamblado agregando <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Domain?displayProperty=nameWithType> a los argumentos que el <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> pasadas de método.  
  
 Después de ejecutar el código, puede confirmar que se creó un almacén escribiendo **StoreAdm /LIST** en la línea de comandos. Esta opción ejecuta la [herramienta almacenamiento aislado (Storeadm.exe)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md) y enumera todos los almacenes aislados actuales para el usuario.  
  
 [!code-cpp[Conceptual.IsolatedStorage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#7)]
 [!code-csharp[Conceptual.IsolatedStorage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#7)]
 [!code-vb[Conceptual.IsolatedStorage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#7)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>  
 [Almacenamiento aislado](../../../docs/standard/io/isolated-storage.md)  
 [Tipos de aislamiento](../../../docs/standard/io/types-of-isolation.md)  
 [Ensamblados en Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
