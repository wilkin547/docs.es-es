---
title: ICorThreadpool::CorSetMaxThreads (Método)
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorSetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetMaxThreads
helpviewer_keywords:
- ICorThreadpool::CorSetMaxThreads method [.NET Framework hosting]
- CorSetMaxThreads method [.NET Framework hosting]
ms.assetid: 4a846238-df4e-4060-ba3b-5173f6a51e85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48d84d5c45ea8e1af1da44480410692d46162810
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198249"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="3d07c-102">ICorThreadpool::CorSetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="3d07c-102">ICorThreadpool::CorSetMaxThreads Method</span></span>
<span data-ttu-id="3d07c-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="3d07c-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d07c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d07c-104">Syntax</span></span>  
  
```  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="3d07c-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d07c-105">Requirements</span></span>  
 <span data-ttu-id="3d07c-106">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d07c-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d07c-107">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3d07c-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3d07c-108">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3d07c-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d07c-109">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d07c-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d07c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d07c-110">See also</span></span>

- [<span data-ttu-id="3d07c-111">ICorThreadpool (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3d07c-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
