---
title: Procedimiento para copiar directorios
description: Vea cómo usar clases de E/S que copian de forma sincrónica el contenido de un directorio en otra ubicación.
ms.date: 12/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directory copying
- I/O [.NET], copying directories
- subdirectory copying
- copying directories
- directories [.NET], copying
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
ms.openlocfilehash: 476473d5c25ce29d070abbeef7fa29a7cb9621e1
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2020
ms.locfileid: "93187988"
---
# <a name="how-to-copy-directories"></a>Procedimiento para copiar directorios

En este artículo se muestra cómo usar las clases de E/S para copiar de forma sincrónica el contenido de un directorio en otra ubicación.

Para obtener un ejemplo de la copia asincrónica de archivos, vea [E/S de archivos asincrónica](asynchronous-file-i-o.md).

En este ejemplo, para copiar los subdirectorios se establece el elemento `copySubDirs` del método `DirectoryCopy` en `true`. Para copiar de forma recursiva los subdirectorios, el método `DirectoryCopy` se llama a si mismo en cada subdirectorio hasta que no haya ninguno más para copiar.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="see-also"></a>Vea también

- <xref:System.IO.FileInfo>
- <xref:System.IO.DirectoryInfo>
- <xref:System.IO.FileStream>
- [E/S de archivos y secuencias](index.md)
- [Tareas de E/S comunes](common-i-o-tasks.md)
- [E/S de archivos asincrónica](asynchronous-file-i-o.md)
