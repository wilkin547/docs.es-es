---
title: Formato del Portapapeles no válido
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 429d1e120a0044152a358a87663eb09989f45b0e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874589"
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="f20fc-102">Formato del Portapapeles no válido</span><span class="sxs-lookup"><span data-stu-id="f20fc-102">Clipboard format is not valid</span></span>

<span data-ttu-id="f20fc-103">El formato del portapapeles especificado es incompatible con el método que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="f20fc-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="f20fc-104">Entre las posibles causas de este error se encuentran:</span><span class="sxs-lookup"><span data-stu-id="f20fc-104">Among the possible causes for this error are:</span></span>  
  
- <span data-ttu-id="f20fc-105">Usar el método o del portapapeles `GetText` `SetText` con un formato de Portapapeles distinto de `vbCFText` o `vbCFLink` .</span><span class="sxs-lookup"><span data-stu-id="f20fc-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
- <span data-ttu-id="f20fc-106">Usar el método o del portapapeles `GetData` `SetData` con un formato de Portapapeles distinto de `vbCFBitmap` , `vbCFDIB` o `vbCFMetafile` .</span><span class="sxs-lookup"><span data-stu-id="f20fc-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
- <span data-ttu-id="f20fc-107">Usar los `GetData` `SetData` métodos o de `DataObject` con un formato de Portapapeles en el intervalo reservado por Microsoft Windows para los formatos registrados (&HC000-&HFFFF), cuando el formato del portapapeles no se ha registrado con Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="f20fc-107">Using the `GetData` or `SetData` methods of a `DataObject` with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f20fc-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f20fc-108">To correct this error</span></span>  
  
- <span data-ttu-id="f20fc-109">Quite el formato no válido y especifique uno válido.</span><span class="sxs-lookup"><span data-stu-id="f20fc-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f20fc-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f20fc-110">See also</span></span>

- [<span data-ttu-id="f20fc-111">Portapapeles: agregar otros formatos</span><span class="sxs-lookup"><span data-stu-id="f20fc-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
