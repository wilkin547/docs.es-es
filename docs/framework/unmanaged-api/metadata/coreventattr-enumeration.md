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
ms.openlocfilehash: ec2972605c40f4ba292f5a5f58d6d3efed53f966
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443564"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="c8dc3-102">CorEventAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c8dc3-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="c8dc3-103">Contiene valores que describen los metadatos de un evento.</span><span class="sxs-lookup"><span data-stu-id="c8dc3-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8dc3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8dc3-104">Syntax</span></span>  
  
```cpp  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="c8dc3-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c8dc3-105">Members</span></span>  
  
|<span data-ttu-id="c8dc3-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="c8dc3-106">Member</span></span>|<span data-ttu-id="c8dc3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8dc3-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="c8dc3-108">Especifica que el evento es especial y que su nombre describe cómo.</span><span class="sxs-lookup"><span data-stu-id="c8dc3-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="c8dc3-109">Reservado para uso interno por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="c8dc3-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="c8dc3-110">Especifica que el Common Language Runtime debe comprobar la codificación del nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="c8dc3-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c8dc3-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8dc3-111">Requirements</span></span>  
 <span data-ttu-id="c8dc3-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8dc3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8dc3-113">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="c8dc3-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c8dc3-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8dc3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8dc3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8dc3-115">See also</span></span>

- [<span data-ttu-id="c8dc3-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="c8dc3-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
