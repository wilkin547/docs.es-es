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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941653"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="c7263-102">CertFreeAuthenticodeTimestamperInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="c7263-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="c7263-103">Libera recursos asignados para el [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="c7263-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7263-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c7263-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7263-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c7263-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="c7263-106">[in, out] Información sobre la marca de tiempo que se va a publicar.</span><span class="sxs-lookup"><span data-stu-id="c7263-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="c7263-107">Consulte la [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="c7263-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7263-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c7263-108">Return Value</span></span>  
 <span data-ttu-id="c7263-109">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="c7263-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="c7263-110">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="c7263-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7263-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7263-111">See also</span></span>

- [<span data-ttu-id="c7263-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="c7263-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
