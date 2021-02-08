---
description: 'Más información acerca de: el formato del portapapeles no es válido'
title: Formato del Portapapeles no válido
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 58ba6197a14b005cf61d0783e19cb3f957dd2fca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796761"
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="60bf8-103">Formato del Portapapeles no válido</span><span class="sxs-lookup"><span data-stu-id="60bf8-103">Clipboard format is not valid</span></span>

<span data-ttu-id="60bf8-104">El formato del portapapeles especificado es incompatible con el método que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="60bf8-104">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="60bf8-105">Entre las posibles causas de este error se encuentran:</span><span class="sxs-lookup"><span data-stu-id="60bf8-105">Among the possible causes for this error are:</span></span>  
  
- <span data-ttu-id="60bf8-106">Usar el método o del portapapeles `GetText` `SetText` con un formato de Portapapeles distinto de `vbCFText` o `vbCFLink` .</span><span class="sxs-lookup"><span data-stu-id="60bf8-106">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
- <span data-ttu-id="60bf8-107">Usar el método o del portapapeles `GetData` `SetData` con un formato de Portapapeles distinto de `vbCFBitmap` , `vbCFDIB` o `vbCFMetafile` .</span><span class="sxs-lookup"><span data-stu-id="60bf8-107">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
- <span data-ttu-id="60bf8-108">Usar los `GetData` `SetData` métodos o de `DataObject` con un formato de Portapapeles en el intervalo reservado por Microsoft Windows para los formatos registrados (&HC000-&HFFFF), cuando el formato del portapapeles no se ha registrado con Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="60bf8-108">Using the `GetData` or `SetData` methods of a `DataObject` with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="60bf8-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="60bf8-109">To correct this error</span></span>  
  
- <span data-ttu-id="60bf8-110">Quite el formato no válido y especifique uno válido.</span><span class="sxs-lookup"><span data-stu-id="60bf8-110">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60bf8-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="60bf8-111">See also</span></span>

- [<span data-ttu-id="60bf8-112">Portapapeles: agregar otros formatos</span><span class="sxs-lookup"><span data-stu-id="60bf8-112">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
