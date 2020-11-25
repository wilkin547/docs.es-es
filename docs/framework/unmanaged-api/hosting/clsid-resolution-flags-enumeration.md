---
title: CLSID_RESOLUTION_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- CLSID_RESOLUTION_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLSID_RESOLUTION_FLAGS
helpviewer_keywords:
- CLSID_RESOLUTION_FLAGS enumeration [.NET Framework hosting]
ms.assetid: cd8b9879-962a-4811-aa46-2e2b6bae0d84
topic_type:
- apiref
ms.openlocfilehash: 19731f34d259757e6de62dd4b4f0d4735d1c2e61
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706169"
---
# <a name="clsid_resolution_flags-enumeration"></a><span data-ttu-id="9a0f3-102">CLSID_RESOLUTION_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="9a0f3-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>

<span data-ttu-id="9a0f3-103">Contiene valores que indican cómo debe resolver el Common Language Runtime (CLR) `CLSID` .</span><span class="sxs-lookup"><span data-stu-id="9a0f3-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a0f3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a0f3-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="9a0f3-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9a0f3-105">Members</span></span>  
  
|<span data-ttu-id="9a0f3-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9a0f3-106">Member</span></span>|<span data-ttu-id="9a0f3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a0f3-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="9a0f3-108">Indica el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9a0f3-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="9a0f3-109">Indica que el tiempo de ejecución busca en el registro y aplica la Directiva de correcciones de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="9a0f3-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9a0f3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a0f3-110">Requirements</span></span>  

 <span data-ttu-id="9a0f3-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a0f3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a0f3-112">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9a0f3-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9a0f3-113">**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a0f3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a0f3-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9a0f3-114">See also</span></span>

- [<span data-ttu-id="9a0f3-115">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="9a0f3-115">Hosting Enumerations</span></span>](hosting-enumerations.md)
