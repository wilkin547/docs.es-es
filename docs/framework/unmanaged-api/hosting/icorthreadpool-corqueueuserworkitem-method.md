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
ms.openlocfilehash: 6b13a2342510b48e72c7fd535cd085d0f50ca474
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534662"
---
# <a name="icorthreadpoolcorqueueuserworkitem-method"></a><span data-ttu-id="a8cc6-102">ICorThreadpool::CorQueueUserWorkItem (Método)</span><span class="sxs-lookup"><span data-stu-id="a8cc6-102">ICorThreadpool::CorQueueUserWorkItem Method</span></span>
<span data-ttu-id="a8cc6-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="a8cc6-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8cc6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8cc6-104">Syntax</span></span>  
  
```  
HRESULT CorQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [in] BOOL                   executeOnlyOnce,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="a8cc6-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8cc6-105">Requirements</span></span>  
 <span data-ttu-id="a8cc6-106">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8cc6-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8cc6-107">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a8cc6-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a8cc6-108">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a8cc6-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8cc6-109">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8cc6-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8cc6-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8cc6-110">See also</span></span>
- [<span data-ttu-id="a8cc6-111">ICorThreadpool (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8cc6-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
