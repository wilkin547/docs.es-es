---
title: "Cómo: Copiar directorios"
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
helpviewer_keywords:
- directory copying
- I/O [.NET Framework], copying directories
- subdirectory copying
- copying directories
- directories [.NET Framework], copying
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 43e9027c1dbfc831f598991374c22434e01fe7ff
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-copy-directories"></a>Cómo: Copiar directorios
En este ejemplo se muestra cómo usar las clases de E/S para copiar de forma sincrónica el contenido de un directorio en otra ubicación. En este ejemplo, el usuario puede especificar si desea copiar también los subdirectorios. Si se copian los subdirectorios, el método en este ejemplo los copia de forma recursiva llamándose en cada subdirectorio posterior hasta que no haya ninguno más para copiar.  
  
 Para obtener un ejemplo de cómo copiar archivos de forma asincrónica, vea [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO.FileInfo>  
 <xref:System.IO.DirectoryInfo>  
 <xref:System.IO.FileStream>  
 [E/S de archivos y secuencias](../../../docs/standard/io/index.md)  
 [Tareas de E/S comunes](../../../docs/standard/io/common-i-o-tasks.md)  
 [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md) (E/S de archivos asincrónica)
