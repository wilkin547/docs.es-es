---
title: Archivo ya abierto
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 401801c7c9072ce11f9eafdb84f2b377669ae545
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770365"
---
# <a name="file-already-open"></a><span data-ttu-id="ae785-102">Archivo ya abierto</span><span class="sxs-lookup"><span data-stu-id="ae785-102">File already open</span></span>
<span data-ttu-id="ae785-103">A veces se debe cerrar un archivo antes que otro `FileOpen` o puede producirse otra operación.</span><span class="sxs-lookup"><span data-stu-id="ae785-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="ae785-104">Entre las causas posibles de este error se incluyen:</span><span class="sxs-lookup"><span data-stu-id="ae785-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="ae785-105">Modo de salida secuencial `FileOpen` ejecutó la operación para un archivo que ya está abierto</span><span class="sxs-lookup"><span data-stu-id="ae785-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="ae785-106">La instrucción hace referencia a un archivo abierto.</span><span class="sxs-lookup"><span data-stu-id="ae785-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ae785-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ae785-107">To correct this error</span></span>  
  
1. <span data-ttu-id="ae785-108">Cierre el archivo antes de ejecutar la instrucción.</span><span class="sxs-lookup"><span data-stu-id="ae785-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae785-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae785-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
