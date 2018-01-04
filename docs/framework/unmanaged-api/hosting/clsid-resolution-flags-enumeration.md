---
title: "CLSID_RESOLUTION_FLAGS (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLSID_RESOLUTION_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: CLSID_RESOLUTION_FLAGS
helpviewer_keywords: CLSID_RESOLUTION_FLAGS enumeration [.NET Framework hosting]
ms.assetid: cd8b9879-962a-4811-aa46-2e2b6bae0d84
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 840e3c3c155a383f94051940b6d63dea3412bf63
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="clsidresolutionflags-enumeration"></a><span data-ttu-id="c1030-102">CLSID_RESOLUTION_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c1030-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>
<span data-ttu-id="c1030-103">Contiene valores que indican el modo en que common language runtime (CLR) debe resolver un `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="c1030-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1030-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1030-104">Syntax</span></span>  
  
```  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="c1030-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c1030-105">Members</span></span>  
  
|<span data-ttu-id="c1030-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="c1030-106">Member</span></span>|<span data-ttu-id="c1030-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1030-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="c1030-108">Indica el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c1030-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="c1030-109">Indica que el tiempo de ejecución busca en el registro y aplica la directiva de corrección de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="c1030-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c1030-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1030-110">Requirements</span></span>  
 <span data-ttu-id="c1030-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1030-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1030-112">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c1030-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c1030-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1030-113">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1030-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1030-114">See Also</span></span>  
 [<span data-ttu-id="c1030-115">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="c1030-115">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
