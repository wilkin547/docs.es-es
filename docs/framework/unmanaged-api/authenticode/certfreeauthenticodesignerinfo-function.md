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
ms.openlocfilehash: bdb764417b757cd7388c49d7e5cac9a960074820
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941638"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="e5b4c-102">CertFreeAuthenticodeSignerInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="e5b4c-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="e5b4c-103">Libera recursos asignados para el [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="e5b4c-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5b4c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5b4c-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5b4c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e5b4c-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="e5b4c-106">[in, out] Información sobre el firmante que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="e5b4c-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="e5b4c-107">Consulte la [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="e5b4c-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5b4c-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e5b4c-108">Return Value</span></span>  
 <span data-ttu-id="e5b4c-109">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="e5b4c-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="e5b4c-110">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="e5b4c-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5b4c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5b4c-111">See also</span></span>

- [<span data-ttu-id="e5b4c-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="e5b4c-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
