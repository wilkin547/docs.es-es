---
title: Se sobrepasó el final del archivo
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: abd5f5c6e5df262d1deadd74f0a146a8d436ceb3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586746"
---
# <a name="input-past-end-of-file"></a><span data-ttu-id="460df-102">Se sobrepasó el final del archivo</span><span class="sxs-lookup"><span data-stu-id="460df-102">Input past end of file</span></span>
<span data-ttu-id="460df-103">Ya sea un `Input` instrucción está leyendo de un archivo que está vacío o uno en el que se usan todos los datos o usa el `EOF` función con un archivo abierto para acceso binario.</span><span class="sxs-lookup"><span data-stu-id="460df-103">Either an `Input` statement is reading from a file that is empty or one in which all the data is used, or you used the `EOF` function with a file opened for binary access.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="460df-104">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="460df-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="460df-105">Use la `EOF` funcionen inmediatamente antes de la `Input` instrucción para detectar el final del archivo.</span><span class="sxs-lookup"><span data-stu-id="460df-105">Use the `EOF` function immediately before the `Input` statement to detect the end of the file.</span></span>  
  
2.  <span data-ttu-id="460df-106">Si el archivo está abierto para acceso binario, utilice `Seek` y `Loc`.</span><span class="sxs-lookup"><span data-stu-id="460df-106">If the file is opened for binary access, use `Seek` and `Loc`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="460df-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="460df-107">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.Input%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
