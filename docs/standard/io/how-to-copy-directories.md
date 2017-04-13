---
title: "C&#243;mo: Copiar directorios | Microsoft Docs"
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
  - "copiar directorios"
  - "directorios [.NET Framework], copiar"
  - "copiar directorio"
  - "E/S [.NET Framework], copiar directorios"
  - "copiar subdirectorio"
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Copiar directorios
En este ejemplo se muestra cómo usar las clases de E\/S para copiar de forma sincrónica el contenido de un directorio en otra ubicación. En este ejemplo, el usuario puede especificar si desea copiar también los subdirectorios. Si se copian los subdirectorios, el método en este ejemplo los copia de forma recursiva llamándose en cada subdirectorio posterior hasta que no haya ninguno más para copiar.  
  
 Para obtener un ejemplo de cómo copiar archivos de forma asincrónica, vea [E\/S de archivos asincrónica](../../../docs/standard/io/e-s-de-archivos-asincrónica.md).  
  
## Ejemplo  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
## Vea también  
 <xref:System.IO.FileInfo>   
 <xref:System.IO.DirectoryInfo>   
 <xref:System.IO.FileStream>   
 [E\/S de archivos y secuencias](../../../docs/standard/io/index.md)   
 [Tareas de E\/S comunes](../../../docs/standard/io/commons-tasks.md)   
 [E\/S de archivos asincrónica](../../../docs/standard/io/e-s-de-archivos-asincrónica.md)