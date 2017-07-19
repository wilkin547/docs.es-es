---
title: "C&#243;mo: Obtener los almacenes de almacenamiento aislado | Microsoft Docs"
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
  - "almacenes, obtener"
  - "almacenar datos mediante almacenamiento aislado, obtener almacenes"
  - "almacenamiento aislado, obtener almacenes"
  - "almacenes de datos, obtener"
  - "almacenamiento de datos mediante almacenamiento aislado, obtener almacenes"
ms.assetid: fcb6b178-d526-47c4-b029-e946f880f9db
caps.latest.revision: 19
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 19
---
# C&#243;mo: Obtener los almacenes de almacenamiento aislado
Un almacén aislado expone un sistema de archivos virtual dentro de un compartimiento de datos.  Fuentes de la clase de <xref:System.IO.IsolatedStorage.IsolatedStorageFile> varios métodos para interactuar con un almacén aislado.  Para crear y recuperar almacenes, <xref:System.IO.IsolatedStorage.IsolatedStorageFile> proporciona tres métodos estáticos:  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> devuelve almacenamiento que es aislado por usuario y ensamblado.  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> devuelve almacenamiento que es aislado con el dominio y ensamblado.  
  
     Ambos métodos recuperan un almacén que pertenece al código del que se llaman.  
  
-   El método estático <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> devuelve un almacén aislado que se especifica pasando una combinación de parámetros de ámbito.  
  
 El código siguiente devuelve un almacén que sea aislado por usuario, el ensamblado, y el dominio.  
  
 [!code-cpp[Conceptual.IsolatedStorage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#6)]
 [!code-csharp[Conceptual.IsolatedStorage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#6)]
 [!code-vb[Conceptual.IsolatedStorage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#6)]  
  
 Puede utilizar el método de <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> para especificar que un almacén debe trasladar con un perfil de usuario móvil.  Para obtener información sobre cómo configurarlo, vea [Tipos de aislamiento](../../../docs/standard/io/types-of-isolation.md).  
  
 Los almacenes aislados que se obtienen del interior de distintos ensamblados son, de forma predeterminada, distintos.  Puede tener acceso al almacén de otro ensamblado o dominio pasando pruebas de ensamblado o dominio en los parámetros del método de <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> .  Esto requiere permiso para el acceso al almacenamiento aislado según la identidad de dominio de la aplicación.  Para obtener más información, vea las sobrecargas del método de <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> .  
  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, y los métodos de <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> devuelven un objeto de <xref:System.IO.IsolatedStorage.IsolatedStorageFile> .  Para poder decidir qué tipo de aislamiento es el más adecuado para su situación, vea [Tipos de aislamiento](../../../docs/standard/io/types-of-isolation.md).  Si tiene un objeto de archivo de almacenamiento aislado, puede utilizar los métodos del almacenamiento aislado para leer, escribir, crear, y eliminar archivos y directorios.  
  
 No hay ningún mecanismo que impida que el código pase un objeto de <xref:System.IO.IsolatedStorage.IsolatedStorageFile> a código que no tiene acceso suficiente para obtener el propio almacén.  Solo se comprueban las identidades de los dominios y ensamblados y los permisos de almacenamiento aislado cuando se obtiene una referencia a un objeto <xref:System.IO.IsolatedStorage.IsolatedStorage>, normalmente en el método <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> o <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>.  Por lo tanto, la protección de las referencias a objetos <xref:System.IO.IsolatedStorage.IsolatedStorageFile> es responsabilidad del código que las usa.  
  
## Ejemplo  
 El código siguiente proporciona un ejemplo sencillo de una clase que obtiene un almacén que sea aislado por usuario y ensamblado.  El código se puede cambiar para recuperar un almacén que sea aislado por usuario, dominio y ensamblado, y el ensamblado agregando <xref:System.IO.IsolatedStorage.IsolatedStorageScope?displayProperty=fullName> a los argumentos que el método de <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> pasa.  
  
 Después de ejecutar el código, puede comprobar que un almacén se creó escribiendo **StoreAdm \/LIST** en la línea de comandos.  Esto ejecuta [Herramienta de almacenamiento aislado \(Storeadm.exe\)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md) y muestra todos los almacenes aislados actuales del usuario.  
  
 [!code-cpp[Conceptual.IsolatedStorage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#7)]
 [!code-csharp[Conceptual.IsolatedStorage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#7)]
 [!code-vb[Conceptual.IsolatedStorage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#7)]  
  
## Vea también  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>   
 [Almacenamiento aislado](../../../docs/standard/io/isolated-storage.md)   
 [Tipos de aislamiento](../../../docs/standard/io/types-of-isolation.md)   
 [Ensamblados en Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)