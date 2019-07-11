---
title: ICorThreadpool::CorQueueUserWorkItem (Método)
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorQueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorQueueUserWorkItem
helpviewer_keywords:
- ICorThreadpool::CorQueueUserWorkItem method [.NET Framework hosting]
- CorQueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 29ac7898-a7c7-433e-8f79-cd5237e0bab8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b421825c7a1f0a42d9b54e36a8e8c1dce2c1fd76
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751170"
---
# <a name="icorthreadpoolcorqueueuserworkitem-method"></a><span data-ttu-id="7473a-102">ICorThreadpool::CorQueueUserWorkItem (Método)</span><span class="sxs-lookup"><span data-stu-id="7473a-102">ICorThreadpool::CorQueueUserWorkItem Method</span></span>
<span data-ttu-id="7473a-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="7473a-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7473a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7473a-104">Syntax</span></span>  
  
```cpp  
HRESULT CorQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [in] BOOL                   executeOnlyOnce,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="7473a-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7473a-105">Requirements</span></span>  
 <span data-ttu-id="7473a-106">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7473a-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7473a-107">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7473a-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7473a-108">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7473a-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7473a-109">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7473a-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7473a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="7473a-110">See also</span></span>

- [<span data-ttu-id="7473a-111">ICorThreadpool (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7473a-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
