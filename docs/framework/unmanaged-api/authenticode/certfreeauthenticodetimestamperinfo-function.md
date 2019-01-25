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
ms.openlocfilehash: 27c16cb5d85ddffc1646bee893c5644682812025
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560586"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="35204-102">CertFreeAuthenticodeTimestamperInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="35204-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="35204-103">Libera recursos asignados para el [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="35204-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35204-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35204-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35204-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="35204-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="35204-106">[in, out] Información sobre la marca de tiempo que se va a publicar.</span><span class="sxs-lookup"><span data-stu-id="35204-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="35204-107">Consulte la [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="35204-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35204-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="35204-108">Return Value</span></span>  
 <span data-ttu-id="35204-109">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="35204-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="35204-110">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="35204-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35204-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="35204-111">See also</span></span>
- [<span data-ttu-id="35204-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="35204-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
