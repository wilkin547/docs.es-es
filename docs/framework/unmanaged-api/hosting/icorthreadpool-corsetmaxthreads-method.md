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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198249"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="15bf7-102">ICorThreadpool::CorSetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="15bf7-102">ICorThreadpool::CorSetMaxThreads Method</span></span>
<span data-ttu-id="15bf7-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="15bf7-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15bf7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15bf7-104">Syntax</span></span>  
  
```  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="15bf7-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15bf7-105">Requirements</span></span>  
 <span data-ttu-id="15bf7-106">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15bf7-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15bf7-107">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="15bf7-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15bf7-108">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="15bf7-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="15bf7-109">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="15bf7-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="15bf7-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="15bf7-110">See also</span></span>

- [<span data-ttu-id="15bf7-111">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="15bf7-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
