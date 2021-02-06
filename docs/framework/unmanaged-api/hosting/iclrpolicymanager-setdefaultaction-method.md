---
description: 'Más información sobre: ICLRPolicyManager:: SetDefaultAction ((método)'
title: ICLRPolicyManager::SetDefaultAction (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: cedf29f6217660493b151e06220158e931385d79
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637370"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a><span data-ttu-id="506e2-103">ICLRPolicyManager::SetDefaultAction (Método)</span><span class="sxs-lookup"><span data-stu-id="506e2-103">ICLRPolicyManager::SetDefaultAction Method</span></span>

<span data-ttu-id="506e2-104">Especifica la acción de la Directiva que debe realizar el Common Language Runtime (CLR) cuando se produce la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="506e2-104">Specifies the policy action the common language runtime (CLR) should take when the specified operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="506e2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="506e2-105">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="506e2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="506e2-106">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="506e2-107">de Uno de los valores de [EClrOperation](eclroperation-enumeration.md) , que indica la acción para la que se debe personalizar el comportamiento de CLR.</span><span class="sxs-lookup"><span data-stu-id="506e2-107">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the action for which CLR behavior should be customized.</span></span>  
  
 `action`  
 <span data-ttu-id="506e2-108">de Uno de los valores de [EPolicyAction](epolicyaction-enumeration.md) , que indica la acción de la Directiva que el CLR debe realizar cuando `operation` se produce.</span><span class="sxs-lookup"><span data-stu-id="506e2-108">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="506e2-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="506e2-109">Return Value</span></span>  
  
|<span data-ttu-id="506e2-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="506e2-110">HRESULT</span></span>|<span data-ttu-id="506e2-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="506e2-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="506e2-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="506e2-112">S_OK</span></span>|<span data-ttu-id="506e2-113">`SetDefaultAction` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="506e2-113">`SetDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="506e2-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="506e2-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="506e2-115">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="506e2-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="506e2-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="506e2-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="506e2-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="506e2-117">The call timed out.</span></span>|  
|<span data-ttu-id="506e2-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="506e2-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="506e2-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="506e2-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="506e2-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="506e2-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="506e2-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="506e2-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="506e2-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="506e2-122">E_FAIL</span></span>|<span data-ttu-id="506e2-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="506e2-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="506e2-124">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="506e2-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="506e2-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="506e2-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="506e2-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="506e2-126">E_INVALIDARG</span></span>|<span data-ttu-id="506e2-127">`action`Se especificó un valor no válido para `operation` o se proporcionó un valor no válido para `operation` .</span><span class="sxs-lookup"><span data-stu-id="506e2-127">An invalid `action` was specified for the `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="506e2-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="506e2-128">Remarks</span></span>  

 <span data-ttu-id="506e2-129">No todos los valores de acción de Directiva se pueden especificar como el comportamiento predeterminado para las operaciones CLR.</span><span class="sxs-lookup"><span data-stu-id="506e2-129">Not all policy action values can be specified as the default behavior for CLR operations.</span></span> <span data-ttu-id="506e2-130">`SetDefaultAction` Normalmente, solo se puede usar para escalar el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="506e2-130">`SetDefaultAction` can typically be used only to escalate behavior.</span></span> <span data-ttu-id="506e2-131">Por ejemplo, un host puede especificar que las anulaciones de subprocesos se conviertan en anulaciones de subproceso forzada, pero no puede especificar lo contrario.</span><span class="sxs-lookup"><span data-stu-id="506e2-131">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="506e2-132">En la tabla siguiente se describen los valores válidos `action` para cada `operation` valor posible.</span><span class="sxs-lookup"><span data-stu-id="506e2-132">The table below describes the valid `action` values for each possible `operation` value.</span></span>  
  
|<span data-ttu-id="506e2-133">Valor de `operation`</span><span class="sxs-lookup"><span data-stu-id="506e2-133">Value for `operation`</span></span>|<span data-ttu-id="506e2-134">Valores válidos para `action`</span><span class="sxs-lookup"><span data-stu-id="506e2-134">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="506e2-135">OPR_ThreadAbort</span><span class="sxs-lookup"><span data-stu-id="506e2-135">OPR_ThreadAbort</span></span>|<span data-ttu-id="506e2-136">- eAbortThread</span><span class="sxs-lookup"><span data-stu-id="506e2-136">-   eAbortThread</span></span><br /><span data-ttu-id="506e2-137">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="506e2-137">-   eRudeAbortThread</span></span><br /><span data-ttu-id="506e2-138">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="506e2-138">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="506e2-139">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="506e2-139">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="506e2-140">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="506e2-140">-   eExitProcess</span></span><br /><span data-ttu-id="506e2-141">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="506e2-141">-   eFastExitProcess</span></span><br /><span data-ttu-id="506e2-142">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="506e2-142">-   eRudeExitProcess</span></span><br /><span data-ttu-id="506e2-143">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="506e2-143">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="506e2-144">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="506e2-144">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="506e2-145">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="506e2-145">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="506e2-146">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="506e2-146">-   eRudeAbortThread</span></span><br /><span data-ttu-id="506e2-147">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="506e2-147">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="506e2-148">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="506e2-148">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="506e2-149">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="506e2-149">-   eExitProcess</span></span><br /><span data-ttu-id="506e2-150">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="506e2-150">-   eFastExitProcess</span></span><br /><span data-ttu-id="506e2-151">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="506e2-151">-   eRudeExitProcess</span></span><br /><span data-ttu-id="506e2-152">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="506e2-152">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="506e2-153">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="506e2-153">OPR_AppDomainUnload</span></span>|<span data-ttu-id="506e2-154">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="506e2-154">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="506e2-155">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="506e2-155">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="506e2-156">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="506e2-156">-   eExitProcess</span></span><br /><span data-ttu-id="506e2-157">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="506e2-157">-   eFastExitProcess</span></span><br /><span data-ttu-id="506e2-158">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="506e2-158">-   eRudeExitProcess</span></span><br /><span data-ttu-id="506e2-159">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="506e2-159">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="506e2-160">OPR_AppDomainRudeUnload</span><span class="sxs-lookup"><span data-stu-id="506e2-160">OPR_AppDomainRudeUnload</span></span>|<span data-ttu-id="506e2-161">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="506e2-161">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="506e2-162">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="506e2-162">-   eExitProcess</span></span><br /><span data-ttu-id="506e2-163">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="506e2-163">-   eFastExitProcess</span></span><br /><span data-ttu-id="506e2-164">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="506e2-164">-   eRudeExitProcess</span></span><br /><span data-ttu-id="506e2-165">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="506e2-165">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="506e2-166">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="506e2-166">OPR_ProcessExit</span></span>|<span data-ttu-id="506e2-167">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="506e2-167">-   eExitProcess</span></span><br /><span data-ttu-id="506e2-168">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="506e2-168">-   eFastExitProcess</span></span><br /><span data-ttu-id="506e2-169">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="506e2-169">-   eRudeExitProcess</span></span><br /><span data-ttu-id="506e2-170">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="506e2-170">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="506e2-171">OPR_FinalizerRun</span><span class="sxs-lookup"><span data-stu-id="506e2-171">OPR_FinalizerRun</span></span>|<span data-ttu-id="506e2-172">- eNoAction</span><span class="sxs-lookup"><span data-stu-id="506e2-172">-   eNoAction</span></span><br /><span data-ttu-id="506e2-173">- eAbortThread</span><span class="sxs-lookup"><span data-stu-id="506e2-173">-   eAbortThread</span></span><br /><span data-ttu-id="506e2-174">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="506e2-174">-   eRudeAbortThread</span></span><br /><span data-ttu-id="506e2-175">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="506e2-175">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="506e2-176">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="506e2-176">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="506e2-177">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="506e2-177">-   eExitProcess</span></span><br /><span data-ttu-id="506e2-178">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="506e2-178">-   eFastExitProcess</span></span><br /><span data-ttu-id="506e2-179">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="506e2-179">-   eRudeExitProcess</span></span><br /><span data-ttu-id="506e2-180">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="506e2-180">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="506e2-181">Requisitos</span><span class="sxs-lookup"><span data-stu-id="506e2-181">Requirements</span></span>  

 <span data-ttu-id="506e2-182">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="506e2-182">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="506e2-183">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="506e2-183">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="506e2-184">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="506e2-184">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="506e2-185">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="506e2-185">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="506e2-186">Vea también</span><span class="sxs-lookup"><span data-stu-id="506e2-186">See also</span></span>

- [<span data-ttu-id="506e2-187">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="506e2-187">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="506e2-188">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="506e2-188">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="506e2-189">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="506e2-189">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
