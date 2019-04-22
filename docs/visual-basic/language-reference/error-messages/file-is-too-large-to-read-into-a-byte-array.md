---
title: Archivo demasiado grande para su lectura en una matriz de bytes
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: 0c7d35e08eeb42e35c4c40e47434a64393d829b1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831519"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a><span data-ttu-id="512f1-102">Archivo demasiado grande para su lectura en una matriz de bytes</span><span class="sxs-lookup"><span data-stu-id="512f1-102">File is too large to read into a byte array</span></span>
<span data-ttu-id="512f1-103">El tamaño del archivo que está intentando leer en una matriz de bytes supera los 4 GB.</span><span class="sxs-lookup"><span data-stu-id="512f1-103">The size of the file you are attempting to read into a byte array exceeds 4 GB.</span></span> <span data-ttu-id="512f1-104">El `My.Computer.FileSystem.ReadAllBytes` método no puede leer un archivo que supera este tamaño.</span><span class="sxs-lookup"><span data-stu-id="512f1-104">The `My.Computer.FileSystem.ReadAllBytes` method cannot read a file that exceeds this size.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="512f1-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="512f1-105">To correct this error</span></span>  
  
-   <span data-ttu-id="512f1-106">Use un <xref:System.IO.StreamReader> para leer el archivo.</span><span class="sxs-lookup"><span data-stu-id="512f1-106">Use a <xref:System.IO.StreamReader> to read the file.</span></span> <span data-ttu-id="512f1-107">Para obtener más información, consulte [conceptos básicos de .NET Framework de E/S de archivos y el sistema de archivos (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span><span class="sxs-lookup"><span data-stu-id="512f1-107">For more information, see [Basics of .NET Framework File I/O and the File System (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="512f1-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="512f1-108">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:System.IO.StreamReader>
- [<span data-ttu-id="512f1-109">Acceso a archivos con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="512f1-109">File Access with Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
- [<span data-ttu-id="512f1-110">Cómo: Leer texto de archivos con StreamReader</span><span class="sxs-lookup"><span data-stu-id="512f1-110">How to: Read Text from Files with a StreamReader</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
