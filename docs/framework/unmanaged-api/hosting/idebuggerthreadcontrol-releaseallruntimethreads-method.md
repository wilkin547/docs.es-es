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
ms.openlocfilehash: 50ffb33456f942a71089f9bc44daa07f6b77ab21
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805297"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="0e850-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="0e850-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="0e850-103">Notifica al host que los servicios de depuración están a punto de liberar todos los subprocesos que están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="0e850-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e850-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e850-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="0e850-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0e850-105">Remarks</span></span>  
 <span data-ttu-id="0e850-106">`ReleaseAllRuntimeThreads`Nunca se llamará al método en un subproceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0e850-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="0e850-107">Si el host tiene un subproceso en tiempo de ejecución bloqueado, debería liberarlo ahora.</span><span class="sxs-lookup"><span data-stu-id="0e850-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e850-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e850-108">Requirements</span></span>  
 <span data-ttu-id="0e850-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e850-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e850-110">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0e850-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0e850-111">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0e850-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0e850-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e850-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e850-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e850-113">See also</span></span>

- [<span data-ttu-id="0e850-114">IDebuggerThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0e850-114">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
