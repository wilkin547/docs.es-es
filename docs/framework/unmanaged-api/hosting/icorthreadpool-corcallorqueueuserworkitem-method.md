---
title: ICorThreadpool::CorCallOrQueueUserWorkItem (Método)
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorCallOrQueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCallOrQueueUserWorkItem
helpviewer_keywords:
- ICorThreadpool::CorCallOrQueueUserWorkItem method [.NET Framework hosting]
- CorCallOrQueueUserWorkItem method [.NET Framework hosting]
ms.assetid: a2081223-84ca-4331-a8d3-9352f422f3e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7dd4589da9b59d7e701ac641c8d45be3735d0b2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700155"
---
# <a name="icorthreadpoolcorcallorqueueuserworkitem-method"></a><span data-ttu-id="dc539-102">ICorThreadpool::CorCallOrQueueUserWorkItem (Método)</span><span class="sxs-lookup"><span data-stu-id="dc539-102">ICorThreadpool::CorCallOrQueueUserWorkItem Method</span></span>
<span data-ttu-id="dc539-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="dc539-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc539-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc539-104">Syntax</span></span>  
  
```  
HRESULT CorCallOrQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="dc539-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc539-105">Requirements</span></span>  
 <span data-ttu-id="dc539-106">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc539-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc539-107">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dc539-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dc539-108">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dc539-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc539-109">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc539-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc539-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc539-110">See also</span></span>

- [<span data-ttu-id="dc539-111">ICorThreadpool (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc539-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
