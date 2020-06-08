---
title: 'Cómo: Obtener los almacenes de almacenamiento aislado'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: a08563b67239c679e3bc88876781508fd78bea75
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291843"
---
# <a name="how-to-obtain-stores-for-isolated-storage"></a>Cómo: Obtener los almacenes de almacenamiento aislado
Un almacén aislado expone un sistema de archivos virtual dentro de un compartimiento de datos. La clase <xref:System.IO.IsolatedStorage.IsolatedStorageFile> proporciona una serie de métodos para interactuar con un almacén aislado. Para crear y recuperar almacenes, <xref:System.IO.IsolatedStorage.IsolatedStorageFile> proporciona tres métodos estáticos:  
  
- <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> devuelve el almacenamiento que está aislado por usuario y ensamblado.  
  
- <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> devuelve el almacenamiento que está aislado por dominio y ensamblado.  
  
     Ambos métodos recuperan un almacén que pertenece al código desde el que se les llama.  
  
- El método estático <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> devuelve un almacén aislado que se especifica pasando una combinación de parámetros de ámbito.  
  
 El código siguiente devuelve un almacén aislado por usuario, dominio y ensamblado.  
  
 [!code-cpp[Conceptual.IsolatedStorage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#6)]
 [!code-csharp[Conceptual.IsolatedStorage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#6)]
 [!code-vb[Conceptual.IsolatedStorage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#6)]  
  
 Puede usar el método <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> para especificar que un almacén se debe trasladar con un perfil de usuario móvil. Para obtener más información sobre cómo configurar esta opción, vea [Tipos de aislamiento](types-of-isolation.md).  
  
 Los almacenes aislados que se obtienen del interior de distintos ensamblados son, de forma predeterminada, almacenes diferentes. Pueda acceder al almacén de otro ensamblado o dominio pasando la evidencia de ensamblado o dominio en los parámetros del método <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>. Esto requiere el permiso para acceder al almacenamiento aislado según la identidad del dominio de aplicación. Para más información, vea las sobrecargas del método <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  
  
 Los métodos <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> y <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> devuelven un objeto <xref:System.IO.IsolatedStorage.IsolatedStorageFile>. Para ayudarle a decidir qué tipo de aislamiento es más adecuado para su situación, vea [Tipos de aislamiento](types-of-isolation.md). Cuando se tiene un objeto de archivo de almacenamiento aislado, puede usar los métodos de almacenamiento aislado para leer, escribir, crear y eliminar archivos y directorios.  
  
 No hay ningún mecanismo que evite que un código pase un objeto <xref:System.IO.IsolatedStorage.IsolatedStorageFile> al código que no tiene suficientes derechos de acceso para obtener el propio almacén. Las identidades de dominio y ensamblado y los permisos de almacenamiento aislado se comprueban solo cuando se obtiene una referencia a un objeto <xref:System.IO.IsolatedStorage.IsolatedStorage>, normalmente en los métodos <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> o <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>. La protección de las referencias a los objetos <xref:System.IO.IsolatedStorage.IsolatedStorageFile> es, por tanto, responsabilidad del código que usa estas referencias.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente proporciona un ejemplo sencillo de una clase que obtiene un almacén aislado por usuario y ensamblado. El código se puede cambiar para recuperar un almacén que está aislado por usuario, dominio y ensamblado agregando <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Domain?displayProperty=nameWithType> a los argumentos que el método <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> pasa.  
  
 Después de ejecutar el código, puede confirmar que se creó un almacén si escribe **StoreAdm /LIST** en la línea de comandos. Esta opción ejecuta la [herramienta de almacenamiento aislado (Storeadm.exe)](../../framework/tools/storeadm-exe-isolated-storage-tool.md) y enumera todos los almacenes aislados actuales para el usuario.  
  
 [!code-cpp[Conceptual.IsolatedStorage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#7)]
 [!code-csharp[Conceptual.IsolatedStorage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#7)]
 [!code-vb[Conceptual.IsolatedStorage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#7)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- <xref:System.IO.IsolatedStorage.IsolatedStorageScope>
- [Almacenamiento aislado](isolated-storage.md)
- [Tipos de aislamiento](types-of-isolation.md)
- [Ensamblados de .NET](../assembly/index.md)
