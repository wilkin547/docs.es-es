---
title: "ICLRPolicyManager::SetDefaultAction (Método)"
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
- ICLRPolicyManager.SetDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetDefaultAction
helpviewer_keywords:
- SetDefaultAction method [.NET Framework hosting]
- ICLRPolicyManager::SetDefaultAction method [.NET Framework hosting]
ms.assetid: f9411e7a-27df-451f-9f6c-d643d6a7a7ce
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 751853aaf4322c15b44bb9b912d293a081c24ba8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a><span data-ttu-id="ed544-102">ICLRPolicyManager::SetDefaultAction (Método)</span><span class="sxs-lookup"><span data-stu-id="ed544-102">ICLRPolicyManager::SetDefaultAction Method</span></span>
<span data-ttu-id="ed544-103">Especifica la acción de directiva que common language runtime (CLR) debe realizar cuando se produzca la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="ed544-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed544-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed544-104">Syntax</span></span>  
  
```  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed544-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ed544-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="ed544-106">[in] Uno de los [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valores, que indica la acción para que CLR se debe personalizar el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="ed544-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the action for which CLR behavior should be customized.</span></span>  
  
 `action`  
 <span data-ttu-id="ed544-107">[in] Uno de los [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valores, que indica la acción de directiva que el CLR debe tomar cuando `operation` se produce.</span><span class="sxs-lookup"><span data-stu-id="ed544-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed544-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ed544-108">Return Value</span></span>  
  
|<span data-ttu-id="ed544-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ed544-109">HRESULT</span></span>|<span data-ttu-id="ed544-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed544-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ed544-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed544-111">S_OK</span></span>|<span data-ttu-id="ed544-112">`SetDefaultAction`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ed544-112">`SetDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="ed544-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ed544-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ed544-114">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ed544-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ed544-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ed544-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ed544-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ed544-116">The call timed out.</span></span>|  
|<span data-ttu-id="ed544-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ed544-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ed544-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ed544-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ed544-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ed544-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ed544-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="ed544-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ed544-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ed544-121">E_FAIL</span></span>|<span data-ttu-id="ed544-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="ed544-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ed544-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="ed544-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ed544-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ed544-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ed544-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ed544-125">E_INVALIDARG</span></span>|<span data-ttu-id="ed544-126">No es válida `action` no se especificó para el `operation`, o se ha proporcionado un valor no válido para `operation`.</span><span class="sxs-lookup"><span data-stu-id="ed544-126">An invalid `action` was specified for the `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed544-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ed544-127">Remarks</span></span>  
 <span data-ttu-id="ed544-128">No todos los valores de acción de directiva se pueden especificar como el comportamiento predeterminado para las operaciones de CLR.</span><span class="sxs-lookup"><span data-stu-id="ed544-128">Not all policy action values can be specified as the default behavior for CLR operations.</span></span> <span data-ttu-id="ed544-129">`SetDefaultAction`Normalmente se usa solo para intensificar el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="ed544-129">`SetDefaultAction` can typically be used only to escalate behavior.</span></span> <span data-ttu-id="ed544-130">Por ejemplo, un host puede especificar que las anulaciones de subprocesos se conviertan en anulaciones anulaciones de subprocesos, pero no se especifique lo contrario.</span><span class="sxs-lookup"><span data-stu-id="ed544-130">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="ed544-131">La siguiente tabla describe los válido `action` valores para cada posible `operation` valor.</span><span class="sxs-lookup"><span data-stu-id="ed544-131">The table below describes the valid `action` values for each possible `operation` value.</span></span>  
  
|<span data-ttu-id="ed544-132">Valor de`operation`</span><span class="sxs-lookup"><span data-stu-id="ed544-132">Value for `operation`</span></span>|<span data-ttu-id="ed544-133">Valores válidos para`action`</span><span class="sxs-lookup"><span data-stu-id="ed544-133">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="ed544-134">OPR_ThreadAbort</span><span class="sxs-lookup"><span data-stu-id="ed544-134">OPR_ThreadAbort</span></span>|<span data-ttu-id="ed544-135">-eAbortThread</span><span class="sxs-lookup"><span data-stu-id="ed544-135">-   eAbortThread</span></span><br /><span data-ttu-id="ed544-136">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="ed544-136">-   eRudeAbortThread</span></span><br /><span data-ttu-id="ed544-137">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ed544-137">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="ed544-138">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ed544-138">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="ed544-139">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="ed544-139">-   eExitProcess</span></span><br /><span data-ttu-id="ed544-140">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="ed544-140">-   eFastExitProcess</span></span><br /><span data-ttu-id="ed544-141">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="ed544-141">-   eRudeExitProcess</span></span><br /><span data-ttu-id="ed544-142">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="ed544-142">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="ed544-143">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="ed544-143">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="ed544-144">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="ed544-144">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="ed544-145">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="ed544-145">-   eRudeAbortThread</span></span><br /><span data-ttu-id="ed544-146">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ed544-146">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="ed544-147">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ed544-147">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="ed544-148">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="ed544-148">-   eExitProcess</span></span><br /><span data-ttu-id="ed544-149">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="ed544-149">-   eFastExitProcess</span></span><br /><span data-ttu-id="ed544-150">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="ed544-150">-   eRudeExitProcess</span></span><br /><span data-ttu-id="ed544-151">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="ed544-151">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="ed544-152">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="ed544-152">OPR_AppDomainUnload</span></span>|<span data-ttu-id="ed544-153">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ed544-153">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="ed544-154">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ed544-154">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="ed544-155">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="ed544-155">-   eExitProcess</span></span><br /><span data-ttu-id="ed544-156">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="ed544-156">-   eFastExitProcess</span></span><br /><span data-ttu-id="ed544-157">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="ed544-157">-   eRudeExitProcess</span></span><br /><span data-ttu-id="ed544-158">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="ed544-158">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="ed544-159">OPR_AppDomainRudeUnload</span><span class="sxs-lookup"><span data-stu-id="ed544-159">OPR_AppDomainRudeUnload</span></span>|<span data-ttu-id="ed544-160">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ed544-160">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="ed544-161">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="ed544-161">-   eExitProcess</span></span><br /><span data-ttu-id="ed544-162">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="ed544-162">-   eFastExitProcess</span></span><br /><span data-ttu-id="ed544-163">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="ed544-163">-   eRudeExitProcess</span></span><br /><span data-ttu-id="ed544-164">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="ed544-164">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="ed544-165">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="ed544-165">OPR_ProcessExit</span></span>|<span data-ttu-id="ed544-166">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="ed544-166">-   eExitProcess</span></span><br /><span data-ttu-id="ed544-167">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="ed544-167">-   eFastExitProcess</span></span><br /><span data-ttu-id="ed544-168">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="ed544-168">-   eRudeExitProcess</span></span><br /><span data-ttu-id="ed544-169">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="ed544-169">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="ed544-170">OPR_FinalizerRun</span><span class="sxs-lookup"><span data-stu-id="ed544-170">OPR_FinalizerRun</span></span>|<span data-ttu-id="ed544-171">-eNoAction</span><span class="sxs-lookup"><span data-stu-id="ed544-171">-   eNoAction</span></span><br /><span data-ttu-id="ed544-172">-eAbortThread</span><span class="sxs-lookup"><span data-stu-id="ed544-172">-   eAbortThread</span></span><br /><span data-ttu-id="ed544-173">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="ed544-173">-   eRudeAbortThread</span></span><br /><span data-ttu-id="ed544-174">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ed544-174">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="ed544-175">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ed544-175">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="ed544-176">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="ed544-176">-   eExitProcess</span></span><br /><span data-ttu-id="ed544-177">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="ed544-177">-   eFastExitProcess</span></span><br /><span data-ttu-id="ed544-178">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="ed544-178">-   eRudeExitProcess</span></span><br /><span data-ttu-id="ed544-179">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="ed544-179">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ed544-180">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed544-180">Requirements</span></span>  
 <span data-ttu-id="ed544-181">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed544-181">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed544-182">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ed544-182">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ed544-183">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ed544-183">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed544-184">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed544-184">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed544-185">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed544-185">See Also</span></span>  
 [<span data-ttu-id="ed544-186">EClrOperation (enumeración)</span><span class="sxs-lookup"><span data-stu-id="ed544-186">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="ed544-187">EPolicyAction (enumeración)</span><span class="sxs-lookup"><span data-stu-id="ed544-187">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="ed544-188">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed544-188">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
