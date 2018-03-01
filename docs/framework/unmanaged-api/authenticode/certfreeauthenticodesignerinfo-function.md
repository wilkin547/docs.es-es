---
title: "CertFreeAuthenticodeSignerInfo (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f8b38d30a1323d0d44330b8bb9a006c372ea7780
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="11eeb-102">CertFreeAuthenticodeSignerInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="11eeb-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="11eeb-103">Libera los recursos asignados para la [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="11eeb-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11eeb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11eeb-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11eeb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="11eeb-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="11eeb-106">[in, out] Información sobre el firmante que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="11eeb-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="11eeb-107">Consulte la [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="11eeb-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11eeb-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="11eeb-108">Return Value</span></span>  
 <span data-ttu-id="11eeb-109">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="11eeb-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="11eeb-110">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="11eeb-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11eeb-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="11eeb-111">See Also</span></span>  
 [<span data-ttu-id="11eeb-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="11eeb-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
