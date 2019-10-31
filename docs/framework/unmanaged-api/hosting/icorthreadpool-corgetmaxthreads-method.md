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
ms.openlocfilehash: c3de2a063030d5169c6ff69e8db72e8be3ae22a3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133276"
---
# <a name="icorthreadpoolcorgetmaxthreads-method"></a><span data-ttu-id="cf936-102">ICorThreadpool::CorGetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="cf936-102">ICorThreadpool::CorGetMaxThreads Method</span></span>
<span data-ttu-id="cf936-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="cf936-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf936-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf936-104">Syntax</span></span>  
  
```cpp  
HRESULT CorGetMaxThreads (  
    [out] DWORD *MaxWorkerThreads,  
    [out] DWORD *MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="cf936-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf936-105">Requirements</span></span>  
 <span data-ttu-id="cf936-106">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf936-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf936-107">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cf936-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cf936-108">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cf936-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cf936-109">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf936-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf936-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf936-110">See also</span></span>

- [<span data-ttu-id="cf936-111">ICorThreadpool (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf936-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
