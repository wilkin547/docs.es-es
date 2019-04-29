---
title: ICorThreadpool::CorBindIoCompletionCallback (Método)
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorBindIoCompletionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorBindIoCompletionCallback
helpviewer_keywords:
- CorBindIoCompletionCallback method [.NET Framework hosting]
- ICorThreadpool::CorBindIoCompletionCallback method [.NET Framework hosting]
ms.assetid: 2b159225-f09c-42f1-aa7c-44087e121249
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b3faffbf9dc85c563dac84fc2e4e4d849db5d42d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700766"
---
# <a name="icorthreadpoolcorbindiocompletioncallback-method"></a><span data-ttu-id="64736-102">ICorThreadpool::CorBindIoCompletionCallback (Método)</span><span class="sxs-lookup"><span data-stu-id="64736-102">ICorThreadpool::CorBindIoCompletionCallback Method</span></span>
<span data-ttu-id="64736-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="64736-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64736-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64736-104">Syntax</span></span>  
  
```  
HRESULT CorBindIoCompletionCallback (  
    [in] HANDLE                          fileHandle,  
    [in] LPOVERLAPPED_COMPLETION_ROUTINE callback  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="64736-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64736-105">Requirements</span></span>  
 <span data-ttu-id="64736-106">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64736-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64736-107">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="64736-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="64736-108">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="64736-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64736-109">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64736-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64736-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="64736-110">See also</span></span>

- [<span data-ttu-id="64736-111">ICorThreadpool (interfaz)</span><span class="sxs-lookup"><span data-stu-id="64736-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
