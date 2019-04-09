---
title: ICorThreadpool::CorGetMaxThreads (Método)
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorGetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGetMaxThreads
helpviewer_keywords:
- CorGetMaxThreads method [.NET Framework hosting]
- ICorThreadpool::CorGetMaxThreads method [.NET Framework hosting]
ms.assetid: 2861533a-cda0-47b3-b716-0d363505289b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bbf5c02972a8331b3dd5e35ffcc4213e094e532d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175739"
---
# <a name="icorthreadpoolcorgetmaxthreads-method"></a><span data-ttu-id="2ab57-102">ICorThreadpool::CorGetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="2ab57-102">ICorThreadpool::CorGetMaxThreads Method</span></span>
<span data-ttu-id="2ab57-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="2ab57-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ab57-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ab57-104">Syntax</span></span>  
  
```  
HRESULT CorGetMaxThreads (  
    [out] DWORD *MaxWorkerThreads,  
    [out] DWORD *MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="2ab57-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ab57-105">Requirements</span></span>  
 <span data-ttu-id="2ab57-106">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ab57-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ab57-107">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2ab57-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2ab57-108">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2ab57-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="2ab57-109">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2ab57-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2ab57-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ab57-110">See also</span></span>

- [<span data-ttu-id="2ab57-111">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ab57-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
