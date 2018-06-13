---
title: 'Cómo: Copiar directorios'
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1cfe07af216da1c35b093a1ca23e4d48c60a7bfe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571240"
---
# <a name="how-to-copy-directories"></a><span data-ttu-id="45d86-102">Cómo: Copiar directorios</span><span class="sxs-lookup"><span data-stu-id="45d86-102">How to: Copy Directories</span></span>
<span data-ttu-id="45d86-103">En este ejemplo se muestra cómo usar las clases de E/S para copiar de forma sincrónica el contenido de un directorio en otra ubicación.</span><span class="sxs-lookup"><span data-stu-id="45d86-103">This example demonstrates how to use I/O classes to synchronously copy the contents of a directory to another location.</span></span> <span data-ttu-id="45d86-104">En este ejemplo, el usuario puede especificar si desea copiar también los subdirectorios.</span><span class="sxs-lookup"><span data-stu-id="45d86-104">In this example, the user can specify whether to also copy the subdirectories.</span></span> <span data-ttu-id="45d86-105">Si se copian los subdirectorios, el método en este ejemplo los copia de forma recursiva llamándose en cada subdirectorio posterior hasta que no haya ninguno más para copiar.</span><span class="sxs-lookup"><span data-stu-id="45d86-105">If the subdirectories are copied, the method in this example recursively copies them by calling itself on each subsequent subdirectory until there are no more to copy.</span></span>  
  
 <span data-ttu-id="45d86-106">Para obtener un ejemplo de cómo copiar archivos de forma asincrónica, vea [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md).</span><span class="sxs-lookup"><span data-stu-id="45d86-106">For an example of copying files asynchronously, see [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="45d86-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="45d86-107">Example</span></span>  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="45d86-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="45d86-108">See Also</span></span>  
 <xref:System.IO.FileInfo>  
 <xref:System.IO.DirectoryInfo>  
 <xref:System.IO.FileStream>  
 [<span data-ttu-id="45d86-109">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="45d86-109">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)  
 [<span data-ttu-id="45d86-110">Tareas de E/S comunes</span><span class="sxs-lookup"><span data-stu-id="45d86-110">Common I/O Tasks</span></span>](../../../docs/standard/io/common-i-o-tasks.md)  
 <span data-ttu-id="45d86-111">[Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md) (E/S de archivos asincrónica)</span><span class="sxs-lookup"><span data-stu-id="45d86-111">[Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md)</span></span>
