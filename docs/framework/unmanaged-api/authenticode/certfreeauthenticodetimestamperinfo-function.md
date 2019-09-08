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
ms.openlocfilehash: a8ecada29528b065ddad0abc80a850ee0f347f6b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786993"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="d60ed-102">CertFreeAuthenticodeTimestamperInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="d60ed-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="d60ed-103">Libera los recursos asignados para la estructura [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="d60ed-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d60ed-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d60ed-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d60ed-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d60ed-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="d60ed-106">[in, out] Información sobre la marca de tiempo que se va a publicar.</span><span class="sxs-lookup"><span data-stu-id="d60ed-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="d60ed-107">Vea la estructura [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="d60ed-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d60ed-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d60ed-108">Return Value</span></span>  
 <span data-ttu-id="d60ed-109">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="d60ed-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="d60ed-110">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="d60ed-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d60ed-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d60ed-111">See also</span></span>

- [<span data-ttu-id="d60ed-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="d60ed-112">Authenticode</span></span>](index.md)
