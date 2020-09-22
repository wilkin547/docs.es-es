---
title: Archivo demasiado grande para su lectura en una matriz de bytes
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: 89459aaf766a70f69008f847dda7ac6e2a1e41d1
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874174"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a><span data-ttu-id="20e4d-102">Archivo demasiado grande para su lectura en una matriz de bytes</span><span class="sxs-lookup"><span data-stu-id="20e4d-102">File is too large to read into a byte array</span></span>

<span data-ttu-id="20e4d-103">El tamaño del archivo que está intentando leer en una matriz de bytes supera los 4 GB.</span><span class="sxs-lookup"><span data-stu-id="20e4d-103">The size of the file you are attempting to read into a byte array exceeds 4 GB.</span></span> <span data-ttu-id="20e4d-104">El `My.Computer.FileSystem.ReadAllBytes` método no puede leer un archivo que supere este tamaño.</span><span class="sxs-lookup"><span data-stu-id="20e4d-104">The `My.Computer.FileSystem.ReadAllBytes` method cannot read a file that exceeds this size.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="20e4d-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="20e4d-105">To correct this error</span></span>  
  
- <span data-ttu-id="20e4d-106">Utilice un <xref:System.IO.StreamReader> para leer el archivo.</span><span class="sxs-lookup"><span data-stu-id="20e4d-106">Use a <xref:System.IO.StreamReader> to read the file.</span></span> <span data-ttu-id="20e4d-107">Para obtener más información, vea [conceptos básicos de .NET Framework e/s de archivos y el sistema de archivos (Visual Basic)](../../developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span><span class="sxs-lookup"><span data-stu-id="20e4d-107">For more information, see [Basics of .NET Framework File I/O and the File System (Visual Basic)](../../developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20e4d-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="20e4d-108">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:System.IO.StreamReader>
- [<span data-ttu-id="20e4d-109">Acceso a archivos con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20e4d-109">File Access with Visual Basic</span></span>](../../developing-apps/programming/drives-directories-files/file-access.md)
- [<span data-ttu-id="20e4d-110">Procedimiento para leer texto de archivos con StreamReader</span><span class="sxs-lookup"><span data-stu-id="20e4d-110">How to: Read Text from Files with a StreamReader</span></span>](../../developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
