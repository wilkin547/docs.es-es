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
ms.openlocfilehash: dc6bb5a137a50ec07f89f292e5d9beac4349c3c7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674182"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="ac830-102">CertFreeAuthenticodeSignerInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="ac830-102">CertFreeAuthenticodeSignerInfo Function</span></span>

<span data-ttu-id="ac830-103">Libera los recursos asignados para la estructura de [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="ac830-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac830-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac830-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac830-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac830-105">Parameters</span></span>  

 `pSignerInfo`  
 <span data-ttu-id="ac830-106">[in, out] Información sobre el firmante que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="ac830-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="ac830-107">Vea la estructura [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="ac830-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac830-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ac830-108">Return Value</span></span>  

 <span data-ttu-id="ac830-109">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="ac830-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="ac830-110">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="ac830-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac830-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac830-111">See also</span></span>

- [<span data-ttu-id="ac830-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="ac830-112">Authenticode</span></span>](index.md)
