---
title: Archivo ya abierto
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: cda72e03eb5c2469b8106957a0c50fbfa5314549
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567040"
---
# <a name="file-already-open"></a><span data-ttu-id="8744e-102">Archivo ya abierto</span><span class="sxs-lookup"><span data-stu-id="8744e-102">File already open</span></span>
<span data-ttu-id="8744e-103">A veces se debe cerrar un archivo antes que otro `FileOpen` o puede producirse otra operación.</span><span class="sxs-lookup"><span data-stu-id="8744e-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="8744e-104">Entre las causas posibles de este error se incluyen:</span><span class="sxs-lookup"><span data-stu-id="8744e-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="8744e-105">Modo de salida secuencial `FileOpen` ejecutó la operación para un archivo que ya está abierto</span><span class="sxs-lookup"><span data-stu-id="8744e-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="8744e-106">La instrucción hace referencia a un archivo abierto.</span><span class="sxs-lookup"><span data-stu-id="8744e-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8744e-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="8744e-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="8744e-108">Cierre el archivo antes de ejecutar la instrucción.</span><span class="sxs-lookup"><span data-stu-id="8744e-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8744e-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="8744e-109">See also</span></span>
- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
