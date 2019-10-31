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
ms.openlocfilehash: d52f9f0bc2ff27d7849a80a424714aa84d3688fe
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136997"
---
# <a name="clsid_resolution_flags-enumeration"></a><span data-ttu-id="db016-102">CLSID_RESOLUTION_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="db016-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>
<span data-ttu-id="db016-103">Contiene valores que indican cómo el Common Language Runtime (CLR) debe resolver un `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="db016-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db016-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db016-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="db016-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="db016-105">Members</span></span>  
  
|<span data-ttu-id="db016-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="db016-106">Member</span></span>|<span data-ttu-id="db016-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="db016-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="db016-108">Indica el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="db016-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="db016-109">Indica que el tiempo de ejecución busca en el registro y aplica la Directiva de correcciones de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="db016-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="db016-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db016-110">Requirements</span></span>  
 <span data-ttu-id="db016-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db016-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db016-112">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="db016-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db016-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db016-113">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db016-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="db016-114">See also</span></span>

- [<span data-ttu-id="db016-115">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="db016-115">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
