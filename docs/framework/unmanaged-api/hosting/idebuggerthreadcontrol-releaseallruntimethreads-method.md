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
ms.openlocfilehash: 490648ab8883b1dba257b82c0d0fa3c8e4783814
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684166"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="43e64-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="43e64-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>

<span data-ttu-id="43e64-103">Notifica al host que los servicios de depuración están a punto de liberar todos los subprocesos que están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="43e64-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43e64-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43e64-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="43e64-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="43e64-105">Remarks</span></span>  

 <span data-ttu-id="43e64-106">`ReleaseAllRuntimeThreads`Nunca se llamará al método en un subproceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="43e64-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="43e64-107">Si el host tiene un subproceso en tiempo de ejecución bloqueado, debería liberarlo ahora.</span><span class="sxs-lookup"><span data-stu-id="43e64-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43e64-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43e64-108">Requirements</span></span>  

 <span data-ttu-id="43e64-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43e64-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43e64-110">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="43e64-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43e64-111">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="43e64-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43e64-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43e64-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43e64-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="43e64-113">See also</span></span>

- [<span data-ttu-id="43e64-114">IDebuggerThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="43e64-114">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
