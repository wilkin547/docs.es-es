---
title: "Se sobrepasó el final del archivo"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 27de462d5d28ee09107d75afe8269e7401c4dc39
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="input-past-end-of-file"></a><span data-ttu-id="0f3fd-102">Se sobrepasó el final del archivo</span><span class="sxs-lookup"><span data-stu-id="0f3fd-102">Input past end of file</span></span>
<span data-ttu-id="0f3fd-103">Ya sea un `Input` instrucción está leyendo de un archivo que está vacío o uno en el que se usan todos los datos o usa el `EOF` función con un archivo abierto para acceso binario.</span><span class="sxs-lookup"><span data-stu-id="0f3fd-103">Either an `Input` statement is reading from a file that is empty or one in which all the data is used, or you used the `EOF` function with a file opened for binary access.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0f3fd-104">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="0f3fd-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="0f3fd-105">Use la `EOF` funcionen inmediatamente antes de la `Input` instrucción para detectar el final del archivo.</span><span class="sxs-lookup"><span data-stu-id="0f3fd-105">Use the `EOF` function immediately before the `Input` statement to detect the end of the file.</span></span>  
  
2.  <span data-ttu-id="0f3fd-106">Si el archivo está abierto para acceso binario, utilice `Seek` y `Loc`.</span><span class="sxs-lookup"><span data-stu-id="0f3fd-106">If the file is opened for binary access, use `Seek` and `Loc`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f3fd-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f3fd-107">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.Input%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
