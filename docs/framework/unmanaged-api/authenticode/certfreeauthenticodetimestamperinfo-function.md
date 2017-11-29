---
title: "CertFreeAuthenticodeTimestamperInfo (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CertFreeAuthenticodeTimestamperInfo
api_location: clr.dll
api_type: DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b8b6392e57e641d25d07580fcb6bf630f8d983be
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="d0c00-102">CertFreeAuthenticodeTimestamperInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="d0c00-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="d0c00-103">Libera los recursos asignados para la [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="d0c00-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0c00-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0c00-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d0c00-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d0c00-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="d0c00-106">[in, out] Información sobre la marca de tiempo que se va a publicar.</span><span class="sxs-lookup"><span data-stu-id="d0c00-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="d0c00-107">Consulte la [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="d0c00-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0c00-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d0c00-108">Return Value</span></span>  
 <span data-ttu-id="d0c00-109">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="d0c00-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="d0c00-110">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="d0c00-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0c00-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0c00-111">See Also</span></span>  
 [<span data-ttu-id="d0c00-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="d0c00-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
