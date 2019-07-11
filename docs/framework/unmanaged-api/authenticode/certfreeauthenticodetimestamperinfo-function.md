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
ms.openlocfilehash: 680d9c959c57620ff38f8e785c670b451e5805b0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741225"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="951ef-102">CertFreeAuthenticodeTimestamperInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="951ef-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="951ef-103">Libera recursos asignados para el [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="951ef-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="951ef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="951ef-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="951ef-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="951ef-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="951ef-106">[in, out] Información sobre la marca de tiempo que se va a publicar.</span><span class="sxs-lookup"><span data-stu-id="951ef-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="951ef-107">Consulte la [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="951ef-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="951ef-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="951ef-108">Return Value</span></span>  
 <span data-ttu-id="951ef-109">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="951ef-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="951ef-110">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="951ef-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="951ef-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="951ef-111">See also</span></span>

- [<span data-ttu-id="951ef-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="951ef-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
