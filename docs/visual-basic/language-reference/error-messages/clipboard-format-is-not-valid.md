---
title: Formato del Portapapeles no válido
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 5ec077be30b0afc8917d431dc9bd73c8dd41be89
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817185"
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="05fba-102">Formato del Portapapeles no válido</span><span class="sxs-lookup"><span data-stu-id="05fba-102">Clipboard format is not valid</span></span>
<span data-ttu-id="05fba-103">El formato de Portapapeles especificado no es compatible con el método que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="05fba-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="05fba-104">Entre las posibles causas de este error son:</span><span class="sxs-lookup"><span data-stu-id="05fba-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="05fba-105">Usar el Portapapeles `GetText` o `SetText` método con un formato de Portapapeles distinto `vbCFText` o `vbCFLink`.</span><span class="sxs-lookup"><span data-stu-id="05fba-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
-   <span data-ttu-id="05fba-106">Usar el Portapapeles `GetData` o `SetData` método con un formato de Portapapeles distinto `vbCFBitmap`, `vbCFDIB`, o `vbCFMetafile`.</span><span class="sxs-lookup"><span data-stu-id="05fba-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
-   <span data-ttu-id="05fba-107">Mediante el `GetData` o `SetData` métodos de un `DataObject` con un formato de Portapapeles en el intervalo reservado por Microsoft Windows para formatos registrados (& HC000 - & HFFFF), cuando ese formato de Portapapeles no se ha registrado con Microsoft Windows .</span><span class="sxs-lookup"><span data-stu-id="05fba-107">Using the `GetData` or `SetData` methods of a `DataObject` with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="05fba-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="05fba-108">To correct this error</span></span>  
  
-   <span data-ttu-id="05fba-109">Quitar el formato no válido y especifique uno válido.</span><span class="sxs-lookup"><span data-stu-id="05fba-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05fba-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="05fba-110">See also</span></span>

- [<span data-ttu-id="05fba-111">Portapapeles: Agregar otros formatos</span><span class="sxs-lookup"><span data-stu-id="05fba-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
