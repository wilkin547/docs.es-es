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
ms.openlocfilehash: 4f0806e0273b111e3398fb8f2884231b96cf1116
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099768"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="958da-102">CertFreeAuthenticodeTimestamperInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="958da-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="958da-103">Libera los recursos asignados para la estructura [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="958da-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="958da-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="958da-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="958da-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="958da-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="958da-106">[in, out] Información sobre la marca de tiempo que se va a publicar.</span><span class="sxs-lookup"><span data-stu-id="958da-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="958da-107">Vea la estructura [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="958da-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="958da-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="958da-108">Return Value</span></span>  
 <span data-ttu-id="958da-109">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="958da-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="958da-110">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="958da-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="958da-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="958da-111">See also</span></span>

- [<span data-ttu-id="958da-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="958da-112">Authenticode</span></span>](index.md)
