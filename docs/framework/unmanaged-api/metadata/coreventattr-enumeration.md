---
description: 'Más información sobre: enumeración Coreventattr ('
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
ms.openlocfilehash: 70f05eacf2cc7c7975b9b52d402cceb60bbea426
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784514"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="da670-103">CorEventAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="da670-103">CorEventAttr Enumeration</span></span>

<span data-ttu-id="da670-104">Contiene valores que describen los metadatos de un evento.</span><span class="sxs-lookup"><span data-stu-id="da670-104">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da670-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da670-105">Syntax</span></span>  
  
```cpp  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="da670-106">Members</span><span class="sxs-lookup"><span data-stu-id="da670-106">Members</span></span>  
  
|<span data-ttu-id="da670-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="da670-107">Member</span></span>|<span data-ttu-id="da670-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="da670-108">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="da670-109">Especifica que el evento es especial y que su nombre describe cómo.</span><span class="sxs-lookup"><span data-stu-id="da670-109">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="da670-110">Reservado para uso interno por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="da670-110">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="da670-111">Especifica que el Common Language Runtime debe comprobar la codificación del nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="da670-111">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="da670-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da670-112">Requirements</span></span>  

 <span data-ttu-id="da670-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da670-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da670-114">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="da670-114">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="da670-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da670-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da670-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="da670-116">See also</span></span>

- [<span data-ttu-id="da670-117">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="da670-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
