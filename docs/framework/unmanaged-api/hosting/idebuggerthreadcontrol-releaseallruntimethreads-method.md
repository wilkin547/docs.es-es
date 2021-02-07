---
description: 'Más información sobre: IDebuggerThreadControl:: Releaseallruntimethreads ((método)'
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
ms.openlocfilehash: bf551ccc2ae5bde3333dc8e3957099590a494dd3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709794"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="2ff98-103">IDebuggerThreadControl::ReleaseAllRuntimeThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="2ff98-103">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>

<span data-ttu-id="2ff98-104">Notifica al host que los servicios de depuración están a punto de liberar todos los subprocesos que están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="2ff98-104">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ff98-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ff98-105">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="2ff98-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2ff98-106">Remarks</span></span>  

 <span data-ttu-id="2ff98-107">`ReleaseAllRuntimeThreads`Nunca se llamará al método en un subproceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2ff98-107">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="2ff98-108">Si el host tiene un subproceso en tiempo de ejecución bloqueado, debería liberarlo ahora.</span><span class="sxs-lookup"><span data-stu-id="2ff98-108">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ff98-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ff98-109">Requirements</span></span>  

 <span data-ttu-id="2ff98-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ff98-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ff98-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2ff98-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2ff98-112">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2ff98-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ff98-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ff98-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ff98-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ff98-114">See also</span></span>

- [<span data-ttu-id="2ff98-115">IDebuggerThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ff98-115">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
