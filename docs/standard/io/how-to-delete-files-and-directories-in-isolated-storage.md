---
title: "C&#243;mo: Eliminar archivos y directorios en almacenamiento aislado | Microsoft Docs"
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
  - "almacenamiento de datos mediante almacenamiento aislado, eliminar archivos y directorios"
  - "directorios [.NET Framework], almacenamiento aislado"
  - "archivos [.NET Framework], almacenamiento aislado"
  - "almacenamiento aislado, eliminar archivos y directorios"
  - "almacenes de datos, eliminar archivos y directorios"
  - "almacenes, crear archivos y directorios"
  - "eliminar archivos de un archivo de almacenamiento aislado"
  - "almacenamiento de datos mediante almacenamiento aislado, eliminar archivos y directorios"
  - "eliminar directorios de un archivo de almacenamiento aislado"
ms.assetid: 8fcc0dea-435b-4d40-ba4d-ba056265c202
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Eliminar archivos y directorios en almacenamiento aislado
Se pueden eliminar los directorios y archivos de un archivo de almacenamiento aislado.  Dentro de un almacén, los nombres de archivo y de directorio dependen del sistema operativo y se especifican como en relación con la raíz del sistema de archivos virtual.  No distinguen entre mayúsculas y minúsculas en los sistemas operativos Windows.  
  
 La clase de <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=fullName> proporciona dos métodos para eliminar directorios y archivos: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> y <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>.  Se produce una excepción de <xref:System.IO.IsolatedStorage.IsolatedStorageException> si intenta eliminar un archivo o un directorio que no existe.  Si incluye un carácter comodín en el nombre, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> produce una excepción de <xref:System.IO.IsolatedStorage.IsolatedStorageException> , y <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> produce una excepción de <xref:System.ArgumentException> .  
  
 El método de <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> supera si el directorio contiene archivos o subdirectorios.  Puede utilizar los métodos de <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> y de <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> para recuperar los archivos y directorios existentes.  Para obtener más información sobre cómo buscar en el sistema de archivos virtual de un almacén, vea [Cómo: Buscar archivos y directorios existentes en almacenamiento aislado](../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md).  
  
## Ejemplo  
 En el siguiente ejemplo de código se crean varios directorios y archivos y, a continuación, se eliminan.  
  
 [!code-cpp[Conceptual.IsolatedStorage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.IsolatedStorage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source4.cs#4)]
 [!code-vb[Conceptual.IsolatedStorage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source4.vb#4)]  
  
## Vea también  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=fullName>   
 [Almacenamiento aislado](../../../docs/standard/io/isolated-storage.md)