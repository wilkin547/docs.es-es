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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36792d01ebdad72271a8b0597a33d83cab34780e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59114035"
---
# <a name="clsidresolutionflags-enumeration"></a><span data-ttu-id="1b3c8-102">CLSID_RESOLUTION_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="1b3c8-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>
<span data-ttu-id="1b3c8-103">Contiene valores que indican el modo en que common language runtime (CLR) debe resolver un `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="1b3c8-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b3c8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b3c8-104">Syntax</span></span>  
  
```  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="1b3c8-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="1b3c8-105">Members</span></span>  
  
|<span data-ttu-id="1b3c8-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="1b3c8-106">Member</span></span>|<span data-ttu-id="1b3c8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b3c8-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="1b3c8-108">Indica el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1b3c8-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="1b3c8-109">Indica que el tiempo de ejecución busca en el registro y aplica la directiva de correcciones de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="1b3c8-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1b3c8-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1b3c8-110">Requirements</span></span>  
 <span data-ttu-id="1b3c8-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b3c8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b3c8-112">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1b3c8-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1b3c8-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b3c8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b3c8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b3c8-114">See also</span></span>

- [<span data-ttu-id="1b3c8-115">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="1b3c8-115">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
