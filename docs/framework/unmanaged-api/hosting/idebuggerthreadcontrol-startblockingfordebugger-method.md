---
description: 'Más información sobre: IDebuggerThreadControl:: Startblockingfordebugger ((método)'
title: IDebuggerThreadControl::StartBlockingForDebugger (Método)
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.StartBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type:
- apiref
ms.openlocfilehash: 3e19817c4adbefd1dd70be047656b3fea261c389
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709686"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="246c7-103">IDebuggerThreadControl::StartBlockingForDebugger (Método)</span><span class="sxs-lookup"><span data-stu-id="246c7-103">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>

<span data-ttu-id="246c7-104">Notifica al host que los servicios de depuración están a punto de iniciar el bloqueo de todos los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="246c7-104">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="246c7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="246c7-105">Syntax</span></span>  
  
```cpp  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="246c7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="246c7-106">Parameters</span></span>  

 `dwUnused`  
 <span data-ttu-id="246c7-107">[in] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="246c7-107">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="246c7-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="246c7-108">Remarks</span></span>  

 <span data-ttu-id="246c7-109">`StartBlockingForDebugger`Se podría llamar al método en un subproceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="246c7-109">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="246c7-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="246c7-110">Requirements</span></span>  

 <span data-ttu-id="246c7-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="246c7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="246c7-112">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="246c7-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="246c7-113">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="246c7-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="246c7-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="246c7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="246c7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="246c7-115">See also</span></span>

- [<span data-ttu-id="246c7-116">IDebuggerThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="246c7-116">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
