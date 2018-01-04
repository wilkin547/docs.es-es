---
title: "IDebuggerThreadControl::StartBlockingForDebugger (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDebuggerThreadControl.StartBlockingForDebugger
api_location: mscoree.dll
api_type: COM
f1_keywords: StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 99c0bc78705fa07883d92bf0cc1d90300c5ac549
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="68ec4-102">IDebuggerThreadControl::StartBlockingForDebugger (Método)</span><span class="sxs-lookup"><span data-stu-id="68ec4-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="68ec4-103">Notifica al host que los servicios de depuración están a punto de iniciarse bloqueando todos los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="68ec4-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68ec4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68ec4-104">Syntax</span></span>  
  
```  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="68ec4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="68ec4-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="68ec4-106">[in] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="68ec4-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68ec4-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="68ec4-107">Remarks</span></span>  
 <span data-ttu-id="68ec4-108">El `StartBlockingForDebugger` se podría llamar el método en un subproceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="68ec4-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68ec4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="68ec4-109">Requirements</span></span>  
 <span data-ttu-id="68ec4-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68ec4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68ec4-111">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="68ec4-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="68ec4-112">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="68ec4-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68ec4-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68ec4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68ec4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="68ec4-114">See Also</span></span>  
 [<span data-ttu-id="68ec4-115">IDebuggerThreadControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="68ec4-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
