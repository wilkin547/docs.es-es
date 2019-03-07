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
ms.openlocfilehash: cbed2ece8b10c6385341c0af44a81dfa16b6f60c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497488"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="1bdb9-102">CertFreeAuthenticodeSignerInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="1bdb9-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="1bdb9-103">Libera recursos asignados para el [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="1bdb9-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bdb9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1bdb9-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bdb9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1bdb9-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="1bdb9-106">[in, out] Información sobre el firmante que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="1bdb9-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="1bdb9-107">Consulte la [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="1bdb9-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1bdb9-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1bdb9-108">Return Value</span></span>  
 <span data-ttu-id="1bdb9-109">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="1bdb9-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="1bdb9-110">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="1bdb9-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bdb9-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bdb9-111">See also</span></span>
- [<span data-ttu-id="1bdb9-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="1bdb9-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
