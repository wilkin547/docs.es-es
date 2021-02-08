---
description: 'Más información sobre: entrada más allá del final del archivo'
title: Se sobrepasó el final del archivo
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: b65a57bdc56367518a93880be28781e56c9b99cc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796046"
---
# <a name="input-past-end-of-file"></a><span data-ttu-id="8c2ad-103">Se sobrepasó el final del archivo</span><span class="sxs-lookup"><span data-stu-id="8c2ad-103">Input past end of file</span></span>

<span data-ttu-id="8c2ad-104">Una `Input` instrucción está leyendo de un archivo que está vacío o uno en el que se usan todos los datos, o bien se ha usado la `EOF` función con un archivo abierto para el acceso binario.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-104">Either an `Input` statement is reading from a file that is empty or one in which all the data is used, or you used the `EOF` function with a file opened for binary access.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8c2ad-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="8c2ad-105">To correct this error</span></span>  
  
1. <span data-ttu-id="8c2ad-106">Utilice la `EOF` función inmediatamente antes de la `Input` instrucción para detectar el final del archivo.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-106">Use the `EOF` function immediately before the `Input` statement to detect the end of the file.</span></span>  
  
2. <span data-ttu-id="8c2ad-107">Si el archivo se abre para el acceso binario, use `Seek` y `Loc` .</span><span class="sxs-lookup"><span data-stu-id="8c2ad-107">If the file is opened for binary access, use `Seek` and `Loc`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c2ad-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c2ad-108">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
