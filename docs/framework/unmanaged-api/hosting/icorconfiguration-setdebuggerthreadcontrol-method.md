---
title: ICorConfiguration::SetDebuggerThreadControl (Método)
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetDebuggerThreadControl
helpviewer_keywords:
- SetDebuggerThreadControl method [.NET Framework hosting]
- ICorConfiguration::SetDebuggerThreadControl method [.NET Framework hosting]
ms.assetid: 1ded7639-dacb-4db1-961c-d1ceaec01959
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6fc141cbebe08f8d0974788409d5aef0f68d2878
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763261"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="5f04a-102">ICorConfiguration::SetDebuggerThreadControl (Método)</span><span class="sxs-lookup"><span data-stu-id="5f04a-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>
<span data-ttu-id="5f04a-103">Establece la interfaz de devolución de llamada que se llamará los servicios de depuración como subprocesos de common language runtime (CLR) se bloquea y desbloquea para la depuración.</span><span class="sxs-lookup"><span data-stu-id="5f04a-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f04a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f04a-104">Syntax</span></span>  
  
```  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f04a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5f04a-105">Parameters</span></span>  
 `pDebuggerThreadControl`  
 <span data-ttu-id="5f04a-106">[in] Un puntero a un [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) objeto que notifica al host el bloqueo y desbloqueo de subprocesos por los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="5f04a-106">[in] A pointer to an [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f04a-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f04a-107">Requirements</span></span>  
 <span data-ttu-id="5f04a-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f04a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f04a-109">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5f04a-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5f04a-110">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5f04a-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f04a-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f04a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f04a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f04a-112">See also</span></span>

- [<span data-ttu-id="5f04a-113">ICorConfiguration (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f04a-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
