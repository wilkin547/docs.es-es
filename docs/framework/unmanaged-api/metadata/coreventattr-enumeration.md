---
title: CorEventAttr (Enumeración)
ms.date: 03/30/2017
api_name:
- CorEventAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorEventAttr
helpviewer_keywords:
- CorEventAttr enumeration [.NET Framework metadata]
ms.assetid: dc2b3281-3820-487e-930d-350b66dc6417
topic_type:
- apiref
ms.openlocfilehash: 554f47cc4bd948e2b6106c1d71a2a4b7968d43f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718870"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="cd8fc-102">CorEventAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="cd8fc-102">CorEventAttr Enumeration</span></span>

<span data-ttu-id="cd8fc-103">Contiene valores que describen los metadatos de un evento.</span><span class="sxs-lookup"><span data-stu-id="cd8fc-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd8fc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd8fc-104">Syntax</span></span>  
  
```cpp  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="cd8fc-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="cd8fc-105">Members</span></span>  
  
|<span data-ttu-id="cd8fc-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="cd8fc-106">Member</span></span>|<span data-ttu-id="cd8fc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="cd8fc-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="cd8fc-108">Especifica que el evento es especial y que su nombre describe cómo.</span><span class="sxs-lookup"><span data-stu-id="cd8fc-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="cd8fc-109">Reservado para uso interno por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="cd8fc-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="cd8fc-110">Especifica que el Common Language Runtime debe comprobar la codificación del nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="cd8fc-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cd8fc-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd8fc-111">Requirements</span></span>  

 <span data-ttu-id="cd8fc-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd8fc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd8fc-113">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="cd8fc-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="cd8fc-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd8fc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd8fc-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd8fc-115">See also</span></span>

- [<span data-ttu-id="cd8fc-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="cd8fc-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
