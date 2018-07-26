---
title: Formato del Portapapeles no válido
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: f2a0ab33c1749117d5de4987e85c44602ccd29ce
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245563"
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="312b1-102">Formato del Portapapeles no válido</span><span class="sxs-lookup"><span data-stu-id="312b1-102">Clipboard format is not valid</span></span>
<span data-ttu-id="312b1-103">El formato de Portapapeles especificado no es compatible con el método que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="312b1-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="312b1-104">Entre las posibles causas de este error son:</span><span class="sxs-lookup"><span data-stu-id="312b1-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="312b1-105">Usar el Portapapeles `GetText` o `SetText` método con un formato de Portapapeles distinto `vbCFText` o `vbCFLink`.</span><span class="sxs-lookup"><span data-stu-id="312b1-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
-   <span data-ttu-id="312b1-106">Usar el Portapapeles `GetData` o `SetData` método con un formato de Portapapeles distinto `vbCFBitmap`, `vbCFDIB`, o `vbCFMetafile`.</span><span class="sxs-lookup"><span data-stu-id="312b1-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
-   <span data-ttu-id="312b1-107">Mediante el `GetData` o `SetData` métodos de un `DataObject` con un formato de Portapapeles en el intervalo reservado por Microsoft Windows para formatos registrados (& HC000 - & HFFFF), cuando ese formato de Portapapeles no se ha registrado con Microsoft Windows .</span><span class="sxs-lookup"><span data-stu-id="312b1-107">Using the `GetData` or `SetData` methods of a `DataObject` with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="312b1-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="312b1-108">To correct this error</span></span>  
  
-   <span data-ttu-id="312b1-109">Quitar el formato no válido y especifique uno válido.</span><span class="sxs-lookup"><span data-stu-id="312b1-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="312b1-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="312b1-110">See Also</span></span>  
 [<span data-ttu-id="312b1-111">Portapapeles: Agregar otros formatos</span><span class="sxs-lookup"><span data-stu-id="312b1-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
