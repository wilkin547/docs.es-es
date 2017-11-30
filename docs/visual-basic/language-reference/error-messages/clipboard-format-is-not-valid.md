---
title: "Formato del Portapapeles no válido"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e7adc417d962de35272319d7dc976b237c7e2b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="38a3c-102">Formato del Portapapeles no válido</span><span class="sxs-lookup"><span data-stu-id="38a3c-102">Clipboard format is not valid</span></span>
<span data-ttu-id="38a3c-103">El formato de Portapapeles especificado no es compatible con el método que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="38a3c-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="38a3c-104">Entre las posibles causas de este error son:</span><span class="sxs-lookup"><span data-stu-id="38a3c-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="38a3c-105">Usar el Portapapeles `GetText` o `SetText` método con un formato de Portapapeles distinto de `vbCFText` o `vbCFLink`.</span><span class="sxs-lookup"><span data-stu-id="38a3c-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
-   <span data-ttu-id="38a3c-106">Usar el Portapapeles `GetData` o `SetData` método con un formato de Portapapeles distinto de `vbCFBitmap`, `vbCFDIB`, o `vbCFMetafile`.</span><span class="sxs-lookup"><span data-stu-id="38a3c-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
-   <span data-ttu-id="38a3c-107">Mediante el `DataObject``GetData` método o `SetData` método con un formato de Portapapeles en el intervalo reservado por Microsoft Windows para formatos registrados (& HC000 - & HFFFF), cuando ese formato de Portapapeles no se ha registrado con Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="38a3c-107">Using the `DataObject``GetData` method or `SetData` method with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="38a3c-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="38a3c-108">To correct this error</span></span>  
  
-   <span data-ttu-id="38a3c-109">Quitar el formato no válido y especifique uno válido.</span><span class="sxs-lookup"><span data-stu-id="38a3c-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38a3c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="38a3c-110">See Also</span></span>  
 [<span data-ttu-id="38a3c-111">Portapapeles: Agregar otros formatos</span><span class="sxs-lookup"><span data-stu-id="38a3c-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
