---
title: "C&#243;mo: Crear archivos y directorios en almacenamiento aislado | Microsoft Docs"
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
  - "directorios [.NET Framework], almacenamiento aislado"
  - "archivos [.NET Framework], almacenamiento aislado"
  - "almacenamiento aislado, crear archivos y directorios"
  - "almacenes de datos, crear archivos y directorios"
  - "almacenamiento de datos mediante almacenamiento aislado, crear archivos y directorios"
  - "almacenes, crear archivos y directorios"
  - "almacenar datos mediante almacenamiento aislado, crear archivos y directorios"
ms.assetid: 2ca4d2a4-809b-4f00-bc08-bf4a64d3a5c3
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Crear archivos y directorios en almacenamiento aislado
Una vez que se ha obtenido un almacén aislado, se pueden crear directorios y archivos para almacenar datos.  Dentro de un almacén, los nombres de archivo y de directorio se especifican en relación con la raíz del sistema de archivos virtual.  
  
 Para crear un directorio, utilice el método de instancia <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=fullName>.  Si especifica un subdirectorio de un directorio que no existe, se crean ambos directorios.  Si se especifica un directorio que ya existe, el método vuelve sin crear un directorio, y no se produce ninguna excepción.  Sin embargo, si se especifica un nombre de directorio que contiene caracteres no válidos, se genera una excepción <xref:System.IO.IsolatedStorage.IsolatedStorageException>.  
  
 Para crear un archivo, utilice el método de <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=fullName> .  
  
 En el sistema operativo Windows, los nombres del archivo de almacenamiento aislado y del directorio no distinguen entre mayúsculas y minúsculas.  Así, si se crea un archivo denominado `ThisFile.txt` y después se crea otro denominado `THISFILE.TXT`, sólo se crea un archivo.  El nombre del archivo se mostrará con las mayúsculas y minúsculas del nombre original.  
  
## Ejemplo  
 En el siguiente ejemplo de código se muestra cómo crear archivos y directorios en un almacén aislado.  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## Vea también  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>   
 [Almacenamiento aislado](../../../docs/standard/io/isolated-storage.md)