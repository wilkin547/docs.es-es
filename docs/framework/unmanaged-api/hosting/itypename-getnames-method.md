---
title: ITypeName::GetNames (Método)
ms.date: 03/30/2017
api_name:
- ITypeName.GetNames
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetNames
helpviewer_keywords:
- ITypeName::GetNames method [.NET Framework hosting]
- GetNames method [.NET Framework hosting]
ms.assetid: e2a3637b-d1e9-4d93-9e9b-0555fbff793d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28076a36880febad20d457ff5a6b290de3d6f173
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121555"
---
# <a name="itypenamegetnames-method"></a><span data-ttu-id="8b5c5-102">ITypeName::GetNames (Método)</span><span class="sxs-lookup"><span data-stu-id="8b5c5-102">ITypeName::GetNames Method</span></span>
<span data-ttu-id="8b5c5-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="8b5c5-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b5c5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8b5c5-104">Syntax</span></span>  
  
```  
HRESULT GetNames (  
    [in] DWORD           count,  
    [out] BSTR*          rgbszNames,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="8b5c5-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8b5c5-105">Requirements</span></span>  
 <span data-ttu-id="8b5c5-106">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b5c5-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b5c5-107">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8b5c5-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8b5c5-108">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8b5c5-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="8b5c5-109">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8b5c5-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8b5c5-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b5c5-110">See also</span></span>

- [<span data-ttu-id="8b5c5-111">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="8b5c5-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
