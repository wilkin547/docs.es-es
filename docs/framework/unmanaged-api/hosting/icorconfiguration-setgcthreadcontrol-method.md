---
title: "ICorConfiguration::SetGCThreadControl (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration.SetGCThreadControl
api_location: mscoree.dll
api_type: COM
f1_keywords: SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b6b28b67f924df4d7f587d0364bce2a853f60b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="67033-102">ICorConfiguration::SetGCThreadControl (Método)</span><span class="sxs-lookup"><span data-stu-id="67033-102">ICorConfiguration::SetGCThreadControl Method</span></span>
<span data-ttu-id="67033-103">Establece la interfaz de devolución de llamada para programar los subprocesos para tareas no en tiempo de ejecución que de lo contrario estarían bloqueados para una colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="67033-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67033-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67033-104">Syntax</span></span>  
  
```  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67033-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="67033-105">Parameters</span></span>  
 `pGCThreadControl`  
 <span data-ttu-id="67033-106">[in] Un puntero a un [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) objeto que notifica al host la suspensión de subprocesos para tareas no en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="67033-106">[in] A pointer to an [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67033-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="67033-107">Remarks</span></span>  
 <span data-ttu-id="67033-108">El host puede elegir dentro de la [IGCThreadControl:: ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) devolución de llamada si se debe volver a programar un subproceso.</span><span class="sxs-lookup"><span data-stu-id="67033-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67033-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="67033-109">Requirements</span></span>  
 <span data-ttu-id="67033-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67033-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67033-111">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="67033-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67033-112">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="67033-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67033-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67033-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67033-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="67033-114">See Also</span></span>  
 [<span data-ttu-id="67033-115">ICorConfiguration (interfaz)</span><span class="sxs-lookup"><span data-stu-id="67033-115">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
