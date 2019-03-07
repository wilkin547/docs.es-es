---
title: CertFreeAuthenticodeTimestamperInfo (Función)
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 082ed24eb65de12f337ab4a379b088da0f6eea5a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497384"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="ed3e3-102">CertFreeAuthenticodeTimestamperInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="ed3e3-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="ed3e3-103">Libera recursos asignados para el [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="ed3e3-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed3e3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed3e3-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed3e3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ed3e3-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="ed3e3-106">[in, out] Información sobre la marca de tiempo que se va a publicar.</span><span class="sxs-lookup"><span data-stu-id="ed3e3-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="ed3e3-107">Consulte la [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="ed3e3-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed3e3-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ed3e3-108">Return Value</span></span>  
 <span data-ttu-id="ed3e3-109">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="ed3e3-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="ed3e3-110">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="ed3e3-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed3e3-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed3e3-111">See also</span></span>
- [<span data-ttu-id="ed3e3-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="ed3e3-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
