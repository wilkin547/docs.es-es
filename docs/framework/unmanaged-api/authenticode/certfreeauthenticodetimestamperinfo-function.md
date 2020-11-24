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
ms.openlocfilehash: 1ef71b14faf66c179030dff2a7d953e27463c1f7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674169"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="d7ec6-102">CertFreeAuthenticodeTimestamperInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="d7ec6-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>

<span data-ttu-id="d7ec6-103">Libera los recursos asignados para la estructura de [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="d7ec6-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7ec6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d7ec6-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7ec6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d7ec6-105">Parameters</span></span>  

 `pTimestamperInfo`  
 <span data-ttu-id="d7ec6-106">[in, out] Información sobre la marca de tiempo que se va a publicar.</span><span class="sxs-lookup"><span data-stu-id="d7ec6-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="d7ec6-107">Vea la estructura [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="d7ec6-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7ec6-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d7ec6-108">Return Value</span></span>  

 <span data-ttu-id="d7ec6-109">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="d7ec6-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="d7ec6-110">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="d7ec6-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7ec6-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d7ec6-111">See also</span></span>

- [<span data-ttu-id="d7ec6-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="d7ec6-112">Authenticode</span></span>](index.md)
