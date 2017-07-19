---
title: "C&#243;mo: Buscar archivos y directorios existentes en almacenamiento aislado | Microsoft Docs"
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
  - "almacenes, buscar archivos y directorios"
  - "buscar archivos en un archivo de almacenamiento aislado"
  - "directorios [.NET Framework], almacenamiento aislado"
  - "almacenamiento aislado, buscar archivos y directorios"
  - "almacenamiento de datos mediante almacenamiento aislado, buscar archivos y directorios"
  - "archivos [.NET Framework], almacenamiento aislado"
  - "almacenes de datos, buscar archivos y directorios"
  - "buscar directorios en un archivo de almacenamiento aislado"
  - "almacenar datos mediante almacenamiento aislado, buscar archivos y directorios"
ms.assetid: eb28458a-6161-4e7a-9ada-30ef93761b5c
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Buscar archivos y directorios existentes en almacenamiento aislado
Para buscar un directorio en almacenamiento aislado, utilice el método de <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=fullName> .  Este método toma una cadena que representa un modelo de búsqueda.  Puede utilizar los caracteres comodín de carácter único \(?\) y de multi\- carácter \(\*\) en el modelo de búsqueda, pero los caracteres comodín deben aparecer en la parte final del nombre.  Por ejemplo, `directory1/*ect*` es una cadena de búsqueda válida, pero `*ect*/directory2` no.  
  
 Para buscar un archivo, utilice el método de <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=fullName> .  La restricción de caracteres comodín en las cadenas de búsqueda que se aplica a <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> también se aplica a <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>.  
  
 Ninguno de estos métodos son recursivos; la clase de <xref:System.IO.IsolatedStorage.IsolatedStorageFile> no proporciona ningún método para enumerar todos los directorios o archivos en el almacén.  Sin embargo, los métodos recursivos se muestran en el ejemplo de código siguiente.  
  
## Ejemplo  
 En el siguiente ejemplo de código se muestra cómo crear archivos y directorios en un almacén aislado.  Primero, se recupera y se colocan un almacén que se encuentra aislado por usuario, dominio y ensamblado, y en la variable de `isoStore` .  El método de <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A> se utiliza para configurar unos cuantos directorios distintos, y el constructor del <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29> crear archivos en estos directorios.  A continuación, el código recorre los resultados del método `GetAllDirectories`.  Este método utiliza <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> para buscar todos los nombres de directorio del directorio actual.  Estos nombres se almacenan en una matriz y, a continuación `GetAllDirectories` se denomina, pasando cada directorio que ha encontrado.  Como resultado, todos los nombres de directorio se devuelven en una matriz.  Después, el código llama al método `GetAllFiles`.  Este método llama a `GetAllDirectories` para averiguar los nombres de todos los directorios y, a continuación comprueba cada directorio para los archivos mediante el método de <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> .  El resultado se devuelve en una matriz para su presentación.  
  
 [!code-cpp[Conceptual.IsolatedStorage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source8.cpp#9)]
 [!code-csharp[Conceptual.IsolatedStorage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source8.cs#9)]
 [!code-vb[Conceptual.IsolatedStorage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source8.vb#9)]  
  
## Vea también  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 [Almacenamiento aislado](../../../docs/standard/io/isolated-storage.md)