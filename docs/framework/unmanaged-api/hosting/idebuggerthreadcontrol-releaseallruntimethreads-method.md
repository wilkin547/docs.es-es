---
title: "IDebuggerThreadControl::ReleaseAllRuntimeThreads (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8e6e2c4032a0765083177df9a6d7d5206448f566
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="ac504-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="ac504-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="ac504-103">Notifica al host que los servicios de depuración están a punto de liberar todos los subprocesos que están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="ac504-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac504-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac504-104">Syntax</span></span>  
  
```  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="ac504-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac504-105">Remarks</span></span>  
 <span data-ttu-id="ac504-106">El `ReleaseAllRuntimeThreads` nunca se llamará el método en un subproceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ac504-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="ac504-107">Si el host tiene un subproceso en tiempo de ejecución bloqueado, debe liberarlo ahora.</span><span class="sxs-lookup"><span data-stu-id="ac504-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac504-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac504-108">Requirements</span></span>  
 <span data-ttu-id="ac504-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac504-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac504-110">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ac504-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac504-111">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac504-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac504-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac504-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac504-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac504-113">See Also</span></span>  
 [<span data-ttu-id="ac504-114">IDebuggerThreadControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac504-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
