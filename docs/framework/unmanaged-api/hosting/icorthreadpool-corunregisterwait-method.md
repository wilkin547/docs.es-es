---
title: ICorThreadpool::CorUnregisterWait (Método)
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorUnregisterWait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnregisterWait
helpviewer_keywords:
- CorUnregisterWait method [.NET Framework hosting]
- ICorThreadpool::CorUnregisterWait method [.NET Framework hosting]
ms.assetid: 42c933f1-30a8-4011-bdea-e117f3c3265e
topic_type:
- apiref
ms.openlocfilehash: 431b90f8c5db5f40bf50be0b03fa315c6ea15ef7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133202"
---
# <a name="icorthreadpoolcorunregisterwait-method"></a><span data-ttu-id="e4b09-102">ICorThreadpool::CorUnregisterWait (Método)</span><span class="sxs-lookup"><span data-stu-id="e4b09-102">ICorThreadpool::CorUnregisterWait Method</span></span>
<span data-ttu-id="e4b09-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="e4b09-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4b09-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4b09-104">Syntax</span></span>  
  
```cpp  
HRESULT CorUnregisterWait (  
    [in] HANDLE hWaitObject,  
    [in] HANDLE CompletionEvent,  
    [out] BOOL* result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e4b09-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e4b09-105">Requirements</span></span>  
 <span data-ttu-id="e4b09-106">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4b09-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4b09-107">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e4b09-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e4b09-108">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e4b09-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e4b09-109">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4b09-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4b09-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4b09-110">See also</span></span>

- [<span data-ttu-id="e4b09-111">ICorThreadpool (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e4b09-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
