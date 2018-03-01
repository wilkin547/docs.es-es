---
title: Archivo ya abierto
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3305831e840510e3f0b5bcb8bf847e39ea3ee4ba
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="file-already-open"></a><span data-ttu-id="b142a-102">Archivo ya abierto</span><span class="sxs-lookup"><span data-stu-id="b142a-102">File already open</span></span>
<span data-ttu-id="b142a-103">A veces se debe cerrar un archivo antes que otro `FileOpen` o se puede realizar otra operación.</span><span class="sxs-lookup"><span data-stu-id="b142a-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="b142a-104">Entre las causas posibles de este error se incluyen:</span><span class="sxs-lookup"><span data-stu-id="b142a-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="b142a-105">Modo de salida secuencial `FileOpen` ha ejecutado una operación para un archivo que ya está abierto</span><span class="sxs-lookup"><span data-stu-id="b142a-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="b142a-106">Una instrucción hace referencia a un archivo abierto.</span><span class="sxs-lookup"><span data-stu-id="b142a-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b142a-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="b142a-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="b142a-108">Cierre el archivo antes de ejecutar la instrucción.</span><span class="sxs-lookup"><span data-stu-id="b142a-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b142a-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="b142a-109">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
