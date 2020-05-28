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
ms.openlocfilehash: e22b390271a7813dd1d34aecf5f8a62d7eb81005
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007445"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="9fa8f-102">CorEventAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="9fa8f-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="9fa8f-103">Contiene valores que describen los metadatos de un evento.</span><span class="sxs-lookup"><span data-stu-id="9fa8f-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fa8f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9fa8f-104">Syntax</span></span>  
  
```cpp  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="9fa8f-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9fa8f-105">Members</span></span>  
  
|<span data-ttu-id="9fa8f-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9fa8f-106">Member</span></span>|<span data-ttu-id="9fa8f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9fa8f-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="9fa8f-108">Especifica que el evento es especial y que su nombre describe cómo.</span><span class="sxs-lookup"><span data-stu-id="9fa8f-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="9fa8f-109">Reservado para uso interno por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="9fa8f-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="9fa8f-110">Especifica que el Common Language Runtime debe comprobar la codificación del nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="9fa8f-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9fa8f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9fa8f-111">Requirements</span></span>  
 <span data-ttu-id="9fa8f-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fa8f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fa8f-113">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="9fa8f-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9fa8f-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fa8f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fa8f-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9fa8f-115">See also</span></span>

- [<span data-ttu-id="9fa8f-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="9fa8f-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
