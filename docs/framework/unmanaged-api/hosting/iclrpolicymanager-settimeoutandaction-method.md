---
title: "ICLRPolicyManager::SetTimeoutAndAction (Método)"
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
- ICLRPolicyManager.SetTimeoutAndAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeoutAndAction
helpviewer_keywords:
- ICLRPolicyManager::SetTimeoutAndAction method [.NET Framework hosting]
- SetTimeoutAndAction method [.NET Framework hosting]
ms.assetid: 60454f91-d855-4ddf-bb6d-60a02f5eabab
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b67150b7544f1d8d25532c564800404b634cae99
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a><span data-ttu-id="1817f-102">ICLRPolicyManager::SetTimeoutAndAction (Método)</span><span class="sxs-lookup"><span data-stu-id="1817f-102">ICLRPolicyManager::SetTimeoutAndAction Method</span></span>
<span data-ttu-id="1817f-103">Establece un valor de tiempo de espera para la operación especificada y especifica la acción de directiva que common language runtime (CLR) debe realizar cuando se produce la operación.</span><span class="sxs-lookup"><span data-stu-id="1817f-103">Sets a timeout value for the specified operation, and specifies the policy action the common language runtime (CLR) should take when the operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1817f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1817f-104">Syntax</span></span>  
  
```  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1817f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1817f-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="1817f-106">[in] Uno de los [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valores, que indica la operación para la que se va a establecer el tiempo de espera y la directiva `action`.</span><span class="sxs-lookup"><span data-stu-id="1817f-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to set the timeout and policy `action`.</span></span> <span data-ttu-id="1817f-107">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="1817f-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="1817f-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="1817f-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="1817f-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="1817f-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="1817f-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="1817f-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="1817f-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="1817f-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="1817f-112">[in] El nuevo valor de tiempo de espera, en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="1817f-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="1817f-113">Un valor de infinito hace `operation` nunca al tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="1817f-113">A value of INFINITE causes `operation` never to time out.</span></span>  
  
 `action`  
 <span data-ttu-id="1817f-114">[in] Uno de los [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valores, que indica la acción de directiva que debe realizar cuando el CLR `operation` se produce.</span><span class="sxs-lookup"><span data-stu-id="1817f-114">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action that the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1817f-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1817f-115">Return Value</span></span>  
  
|<span data-ttu-id="1817f-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1817f-116">HRESULT</span></span>|<span data-ttu-id="1817f-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="1817f-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1817f-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="1817f-118">S_OK</span></span>|<span data-ttu-id="1817f-119">`SetTimeoutAndAction`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1817f-119">`SetTimeoutAndAction` returned successfully.</span></span>|  
|<span data-ttu-id="1817f-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1817f-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1817f-121">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="1817f-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1817f-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1817f-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1817f-123">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="1817f-123">The call timed out.</span></span>|  
|<span data-ttu-id="1817f-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1817f-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1817f-125">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1817f-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1817f-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1817f-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1817f-127">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="1817f-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1817f-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1817f-128">E_FAIL</span></span>|<span data-ttu-id="1817f-129">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="1817f-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1817f-130">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="1817f-130">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1817f-131">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1817f-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1817f-132">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1817f-132">E_INVALIDARG</span></span>|<span data-ttu-id="1817f-133">No se puede establecer un tiempo de espera para el elemento especificado `operation`, o se ha proporcionado un valor no válido para `action`.</span><span class="sxs-lookup"><span data-stu-id="1817f-133">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `action`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1817f-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1817f-134">Remarks</span></span>  
 <span data-ttu-id="1817f-135">`SetTimeoutAndAction`encapsula las capacidades de la [ICLRPolicyManager:: SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) y [ICLRPolicyManager:: SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) métodos y se puede llamar en lugar de utilizar llamadas secuenciales a estos dos métodos.</span><span class="sxs-lookup"><span data-stu-id="1817f-135">`SetTimeoutAndAction` encapsulates the capabilities of the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) and [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) methods, and can be called in place of sequential calls to these two methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1817f-136">No todos los valores de acción de directiva se pueden especificar como el comportamiento de tiempo de espera para las operaciones de CLR.</span><span class="sxs-lookup"><span data-stu-id="1817f-136">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="1817f-137">Vea las secciones de comentarios de los temas de estos dos métodos para los valores válidos.</span><span class="sxs-lookup"><span data-stu-id="1817f-137">See the Remarks sections of the topics for these two methods for valid values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1817f-138">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1817f-138">Requirements</span></span>  
 <span data-ttu-id="1817f-139">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1817f-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1817f-140">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1817f-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1817f-141">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1817f-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1817f-142">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1817f-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1817f-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="1817f-143">See Also</span></span>  
 [<span data-ttu-id="1817f-144">EClrOperation (enumeración)</span><span class="sxs-lookup"><span data-stu-id="1817f-144">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="1817f-145">EPolicyAction (enumeración)</span><span class="sxs-lookup"><span data-stu-id="1817f-145">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="1817f-146">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1817f-146">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="1817f-147">SetActionOnTimeout (método)</span><span class="sxs-lookup"><span data-stu-id="1817f-147">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)  
 [<span data-ttu-id="1817f-148">ICLRPolicyManager:: SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="1817f-148">ICLRPolicyManager::SetTimeoutAndAction</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)
