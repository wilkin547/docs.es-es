---
title: "C&#243;mo: Leer y escribir en archivos en almacenamiento aislado | Microsoft Docs"
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
  - "almacenamiento de datos mediante almacenamiento aislado, leer y escribir en archivos"
  - "almacenes de datos, leer y escribir en archivos"
  - "archivos, almacenamiento aislado"
  - "almacenamiento aislado, leer y escribir en archivos"
  - "leer datos"
  - "leer archivos de un almacén"
  - "almacenes, leer y escribir en archivos"
  - "almacenar datos mediante almacenamiento aislado, leer y escribir en archivos"
  - "escribir en archivos de un almacén"
ms.assetid: f977ebdc-1b55-475a-bc3d-3376470b08ae
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Leer y escribir en archivos en almacenamiento aislado
Para leer, escribir o, en un archivo de un almacén aislado, utilice un objeto de <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> con un lector de entradas \(objeto de<xref:System.IO.StreamReader> \) o el programador de la secuencia \(objeto de<xref:System.IO.StreamWriter> \).  
  
## Ejemplo  
 El ejemplo de código siguiente se obtiene un almacén aislado y comprueba si un archivo denominado TestStore.txt existe en el almacén.  Si no existe, cree el archivo y escribe “Hello isolated storage” en el archivo.  Si existe TestStore.txt ya, lee el código de ejemplo del archivo.  
  
 [!code-csharp[Conceptual.IsolatedStorage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source5.cs#5)]
 [!code-vb[Conceptual.IsolatedStorage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source5.vb#5)]  
  
## Vea también  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>   
 <xref:System.IO.FileMode?displayProperty=fullName>   
 <xref:System.IO.FileAccess?displayProperty=fullName>   
 <xref:System.IO.StreamReader?displayProperty=fullName>   
 <xref:System.IO.StreamWriter?displayProperty=fullName>   
 [E\/S de archivos y secuencias](../../../docs/standard/io/index.md)   
 [Almacenamiento aislado](../../../docs/standard/io/isolated-storage.md)