---
title: Archivo ya abierto
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: e565dbd6352a8f76290f3f58d62e2e14a18ef45f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58823511"
---
# <a name="file-already-open"></a><span data-ttu-id="eb9f5-102">Archivo ya abierto</span><span class="sxs-lookup"><span data-stu-id="eb9f5-102">File already open</span></span>
<span data-ttu-id="eb9f5-103">A veces se debe cerrar un archivo antes que otro `FileOpen` o puede producirse otra operación.</span><span class="sxs-lookup"><span data-stu-id="eb9f5-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="eb9f5-104">Entre las causas posibles de este error se incluyen:</span><span class="sxs-lookup"><span data-stu-id="eb9f5-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="eb9f5-105">Modo de salida secuencial `FileOpen` ejecutó la operación para un archivo que ya está abierto</span><span class="sxs-lookup"><span data-stu-id="eb9f5-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="eb9f5-106">La instrucción hace referencia a un archivo abierto.</span><span class="sxs-lookup"><span data-stu-id="eb9f5-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="eb9f5-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="eb9f5-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="eb9f5-108">Cierre el archivo antes de ejecutar la instrucción.</span><span class="sxs-lookup"><span data-stu-id="eb9f5-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb9f5-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb9f5-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
