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
ms.openlocfilehash: 355e6c7b1cd77936d5ccfa5ccff7312c8e35ac63
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220409"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="2fb77-102">CertFreeAuthenticodeTimestamperInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="2fb77-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="2fb77-103">Libera recursos asignados para el [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="2fb77-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fb77-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2fb77-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fb77-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2fb77-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="2fb77-106">[in, out] Información sobre la marca de tiempo que se va a publicar.</span><span class="sxs-lookup"><span data-stu-id="2fb77-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="2fb77-107">Consulte la [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="2fb77-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2fb77-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2fb77-108">Return Value</span></span>  
 `S_OK` <span data-ttu-id="2fb77-109">Si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="2fb77-109">if the function succeeds.</span></span> <span data-ttu-id="2fb77-110">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="2fb77-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fb77-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="2fb77-111">See also</span></span>

- [<span data-ttu-id="2fb77-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="2fb77-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
