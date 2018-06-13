---
title: CertFreeAuthenticodeSignerInfo (Función)
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84f15dc49d14e781f69d0f9da8f314eb71d8c034
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401621"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="64c14-102">CertFreeAuthenticodeSignerInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="64c14-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="64c14-103">Libera los recursos asignados para la [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="64c14-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64c14-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64c14-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64c14-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="64c14-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="64c14-106">[in, out] Información sobre el firmante que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="64c14-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="64c14-107">Consulte la [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="64c14-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64c14-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="64c14-108">Return Value</span></span>  
 <span data-ttu-id="64c14-109">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="64c14-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="64c14-110">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="64c14-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64c14-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="64c14-111">See Also</span></span>  
 [<span data-ttu-id="64c14-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="64c14-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
