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
ms.openlocfilehash: 5274e70c5bead201beb158ee2895415d7ec9e53c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779129"
---
# <a name="clsidresolutionflags-enumeration"></a><span data-ttu-id="74464-102">CLSID_RESOLUTION_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="74464-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>
<span data-ttu-id="74464-103">Contiene valores que indican el modo en que common language runtime (CLR) debe resolver un `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="74464-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74464-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74464-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="74464-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="74464-105">Members</span></span>  
  
|<span data-ttu-id="74464-106">Member</span><span class="sxs-lookup"><span data-stu-id="74464-106">Member</span></span>|<span data-ttu-id="74464-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="74464-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="74464-108">Indica el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="74464-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="74464-109">Indica que el tiempo de ejecución busca en el registro y aplica la directiva de correcciones de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="74464-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="74464-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74464-110">Requirements</span></span>  
 <span data-ttu-id="74464-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74464-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74464-112">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="74464-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74464-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74464-113">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74464-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="74464-114">See also</span></span>

- [<span data-ttu-id="74464-115">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="74464-115">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
