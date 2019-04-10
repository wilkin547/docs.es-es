---
title: ITypeName::GetModifiers (Método)
ms.date: 03/30/2017
api_name:
- ITypeName.GetModifiers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetModifiers
helpviewer_keywords:
- ITypeName::GetModifiers method [.NET Framework hosting]
- GetModifiers method [.NET Framework hosting]
ms.assetid: 75508c55-3e09-4135-80da-cc811003fa82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 78d86aff385bbff479c57d8902fbd0973a6ad1bc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226422"
---
# <a name="itypenamegetmodifiers-method"></a><span data-ttu-id="07e1e-102">ITypeName::GetModifiers (Método)</span><span class="sxs-lookup"><span data-stu-id="07e1e-102">ITypeName::GetModifiers Method</span></span>
<span data-ttu-id="07e1e-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="07e1e-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07e1e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07e1e-104">Syntax</span></span>  
  
```  
HRESULT GetModifiers (  
    [in] DWORD           count,  
    [out] DWORD*         rgModifiers,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="07e1e-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="07e1e-105">Requirements</span></span>  
 <span data-ttu-id="07e1e-106">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07e1e-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07e1e-107">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="07e1e-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="07e1e-108">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="07e1e-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="07e1e-109">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="07e1e-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="07e1e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="07e1e-110">See also</span></span>

- [<span data-ttu-id="07e1e-111">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="07e1e-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
