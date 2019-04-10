---
title: IDebuggerThreadControl::ReleaseAllRuntimeThreads (Método)
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ReleaseAllRuntimeThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ReleaseAllRuntimeThreads
helpviewer_keywords:
- ReleaseAllRuntimeThreads method [.NET Framework hosting]
- IDebuggerThreadControl::ReleaseAllRuntimeThreads method [.NET Framework hosting]
ms.assetid: 1a2995ff-5f02-4b49-84dc-3a5f9cfd7d55
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 136dab5c05c310d85a5e18bcdc6da0de901d3ace
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227475"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="b2a02-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="b2a02-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="b2a02-103">Notifica al host que los servicios de depuración están a punto de liberar todos los subprocesos que están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="b2a02-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2a02-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2a02-104">Syntax</span></span>  
  
```  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="b2a02-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b2a02-105">Remarks</span></span>  
 <span data-ttu-id="b2a02-106">El `ReleaseAllRuntimeThreads` nunca se llamará el método en un subproceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b2a02-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="b2a02-107">Si el host tiene un subproceso en tiempo de ejecución bloqueado, debe liberar ahora.</span><span class="sxs-lookup"><span data-stu-id="b2a02-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2a02-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2a02-108">Requirements</span></span>  
 <span data-ttu-id="b2a02-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2a02-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2a02-110">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b2a02-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b2a02-111">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b2a02-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b2a02-112">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b2a02-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b2a02-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2a02-113">See also</span></span>

- [<span data-ttu-id="b2a02-114">IDebuggerThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2a02-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
