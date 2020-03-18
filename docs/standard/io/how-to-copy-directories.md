---
title: Procedimiento para copiar directorios
ms.date: 12/27/2018
ms.technology: dotnet-standard
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
ms.openlocfilehash: 5d40db7f902dac8bd6bbdc1510be8e56a321be30
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159460"
---
# <a name="how-to-copy-directories"></a>Procedimiento para copiar directorios
En este tema se muestra cómo usar las clases de E/S para copiar de forma sincrónica el contenido de un directorio en otra ubicación.

Para obtener un ejemplo de la copia asincrónica de archivos, vea [E/S de archivos asincrónica](../../../docs/standard/io/asynchronous-file-i-o.md).

En este ejemplo, para copiar los subdirectorios se establece el elemento `copySubDirs` del método `DirectoryCopy` en `true`. Para copiar de forma recursiva los subdirectorios, el método `DirectoryCopy` se llama a si mismo en cada subdirectorio hasta que no haya ninguno más para copiar.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="see-also"></a>Vea también

- <xref:System.IO.FileInfo>
- <xref:System.IO.DirectoryInfo>
- <xref:System.IO.FileStream>
- [E/S de archivos y secuencias](../../../docs/standard/io/index.md)
- [Tareas de E/S comunes](../../../docs/standard/io/common-i-o-tasks.md)
- [E/S de archivos asincrónica](../../../docs/standard/io/asynchronous-file-i-o.md)
