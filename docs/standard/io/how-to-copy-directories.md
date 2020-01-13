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
ms.openlocfilehash: 223e83a5ff6a73825985ec4e3b6b601fb196fe5e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75707905"
---
# <a name="how-to-copy-directories"></a><span data-ttu-id="61aa0-102">Procedimiento para copiar directorios</span><span class="sxs-lookup"><span data-stu-id="61aa0-102">How to: Copy directories</span></span>
<span data-ttu-id="61aa0-103">En este tema se muestra cómo usar las clases de E/S para copiar de forma sincrónica el contenido de un directorio en otra ubicación.</span><span class="sxs-lookup"><span data-stu-id="61aa0-103">This topic demonstrates how to use I/O classes to synchronously copy the contents of a directory to another location.</span></span> 

<span data-ttu-id="61aa0-104">Para obtener un ejemplo de la copia asincrónica de archivos, vea [E/S de archivos asincrónica](../../../docs/standard/io/asynchronous-file-i-o.md).</span><span class="sxs-lookup"><span data-stu-id="61aa0-104">For an example of asynchronous file copy, see [Asynchronous file I/O](../../../docs/standard/io/asynchronous-file-i-o.md).</span></span> 

<span data-ttu-id="61aa0-105">En este ejemplo, para copiar los subdirectorios se establece el elemento `copySubDirs` del método `DirectoryCopy` en `true`.</span><span class="sxs-lookup"><span data-stu-id="61aa0-105">This example copies subdirectories by setting the `copySubDirs` of the `DirectoryCopy` method to `true`.</span></span> <span data-ttu-id="61aa0-106">Para copiar de forma recursiva los subdirectorios, el método `DirectoryCopy` se llama a si mismo en cada subdirectorio hasta que no haya ninguno más para copiar.</span><span class="sxs-lookup"><span data-stu-id="61aa0-106">The `DirectoryCopy` method recursively copies subdirectories by calling itself on each subdirectory until there are no more to copy.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61aa0-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61aa0-107">Example</span></span>  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="61aa0-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="61aa0-108">See also</span></span>

- <xref:System.IO.FileInfo>
- <xref:System.IO.DirectoryInfo>
- <xref:System.IO.FileStream>
- [<span data-ttu-id="61aa0-109">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="61aa0-109">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
- [<span data-ttu-id="61aa0-110">Tareas de E/S comunes</span><span class="sxs-lookup"><span data-stu-id="61aa0-110">Common I/O tasks</span></span>](../../../docs/standard/io/common-i-o-tasks.md)
- [<span data-ttu-id="61aa0-111">E/S de archivos asincrónica</span><span class="sxs-lookup"><span data-stu-id="61aa0-111">Asynchronous file I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)
