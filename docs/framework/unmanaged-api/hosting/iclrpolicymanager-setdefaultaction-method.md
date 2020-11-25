---
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
ms.openlocfilehash: 93070690ea6b30b22949953f1ed0b8c5b1e92764
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732489"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a><span data-ttu-id="afa30-102">ICLRPolicyManager::SetDefaultAction (Método)</span><span class="sxs-lookup"><span data-stu-id="afa30-102">ICLRPolicyManager::SetDefaultAction Method</span></span>

<span data-ttu-id="afa30-103">Especifica la acción de la Directiva que debe realizar el Common Language Runtime (CLR) cuando se produce la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="afa30-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afa30-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="afa30-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="afa30-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="afa30-105">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="afa30-106">de Uno de los valores de [EClrOperation](eclroperation-enumeration.md) , que indica la acción para la que se debe personalizar el comportamiento de CLR.</span><span class="sxs-lookup"><span data-stu-id="afa30-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the action for which CLR behavior should be customized.</span></span>  
  
 `action`  
 <span data-ttu-id="afa30-107">de Uno de los valores de [EPolicyAction](epolicyaction-enumeration.md) , que indica la acción de la Directiva que el CLR debe realizar cuando `operation` se produce.</span><span class="sxs-lookup"><span data-stu-id="afa30-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="afa30-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="afa30-108">Return Value</span></span>  
  
|<span data-ttu-id="afa30-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="afa30-109">HRESULT</span></span>|<span data-ttu-id="afa30-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="afa30-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="afa30-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="afa30-111">S_OK</span></span>|<span data-ttu-id="afa30-112">`SetDefaultAction` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="afa30-112">`SetDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="afa30-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="afa30-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="afa30-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="afa30-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="afa30-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="afa30-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="afa30-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="afa30-116">The call timed out.</span></span>|  
|<span data-ttu-id="afa30-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="afa30-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="afa30-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="afa30-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="afa30-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="afa30-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="afa30-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="afa30-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="afa30-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="afa30-121">E_FAIL</span></span>|<span data-ttu-id="afa30-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="afa30-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="afa30-123">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="afa30-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="afa30-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="afa30-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="afa30-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="afa30-125">E_INVALIDARG</span></span>|<span data-ttu-id="afa30-126">`action`Se especificó un valor no válido para `operation` o se proporcionó un valor no válido para `operation` .</span><span class="sxs-lookup"><span data-stu-id="afa30-126">An invalid `action` was specified for the `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afa30-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="afa30-127">Remarks</span></span>  

 <span data-ttu-id="afa30-128">No todos los valores de acción de Directiva se pueden especificar como el comportamiento predeterminado para las operaciones CLR.</span><span class="sxs-lookup"><span data-stu-id="afa30-128">Not all policy action values can be specified as the default behavior for CLR operations.</span></span> <span data-ttu-id="afa30-129">`SetDefaultAction` Normalmente, solo se puede usar para escalar el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="afa30-129">`SetDefaultAction` can typically be used only to escalate behavior.</span></span> <span data-ttu-id="afa30-130">Por ejemplo, un host puede especificar que las anulaciones de subprocesos se conviertan en anulaciones de subproceso forzada, pero no puede especificar lo contrario.</span><span class="sxs-lookup"><span data-stu-id="afa30-130">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="afa30-131">En la tabla siguiente se describen los valores válidos `action` para cada `operation` valor posible.</span><span class="sxs-lookup"><span data-stu-id="afa30-131">The table below describes the valid `action` values for each possible `operation` value.</span></span>  
  
|<span data-ttu-id="afa30-132">Valor de `operation`</span><span class="sxs-lookup"><span data-stu-id="afa30-132">Value for `operation`</span></span>|<span data-ttu-id="afa30-133">Valores válidos para `action`</span><span class="sxs-lookup"><span data-stu-id="afa30-133">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="afa30-134">OPR_ThreadAbort</span><span class="sxs-lookup"><span data-stu-id="afa30-134">OPR_ThreadAbort</span></span>|<span data-ttu-id="afa30-135">- eAbortThread</span><span class="sxs-lookup"><span data-stu-id="afa30-135">-   eAbortThread</span></span><br /><span data-ttu-id="afa30-136">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="afa30-136">-   eRudeAbortThread</span></span><br /><span data-ttu-id="afa30-137">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="afa30-137">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="afa30-138">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="afa30-138">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="afa30-139">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="afa30-139">-   eExitProcess</span></span><br /><span data-ttu-id="afa30-140">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="afa30-140">-   eFastExitProcess</span></span><br /><span data-ttu-id="afa30-141">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="afa30-141">-   eRudeExitProcess</span></span><br /><span data-ttu-id="afa30-142">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="afa30-142">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="afa30-143">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="afa30-143">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="afa30-144">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="afa30-144">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="afa30-145">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="afa30-145">-   eRudeAbortThread</span></span><br /><span data-ttu-id="afa30-146">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="afa30-146">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="afa30-147">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="afa30-147">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="afa30-148">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="afa30-148">-   eExitProcess</span></span><br /><span data-ttu-id="afa30-149">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="afa30-149">-   eFastExitProcess</span></span><br /><span data-ttu-id="afa30-150">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="afa30-150">-   eRudeExitProcess</span></span><br /><span data-ttu-id="afa30-151">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="afa30-151">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="afa30-152">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="afa30-152">OPR_AppDomainUnload</span></span>|<span data-ttu-id="afa30-153">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="afa30-153">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="afa30-154">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="afa30-154">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="afa30-155">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="afa30-155">-   eExitProcess</span></span><br /><span data-ttu-id="afa30-156">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="afa30-156">-   eFastExitProcess</span></span><br /><span data-ttu-id="afa30-157">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="afa30-157">-   eRudeExitProcess</span></span><br /><span data-ttu-id="afa30-158">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="afa30-158">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="afa30-159">OPR_AppDomainRudeUnload</span><span class="sxs-lookup"><span data-stu-id="afa30-159">OPR_AppDomainRudeUnload</span></span>|<span data-ttu-id="afa30-160">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="afa30-160">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="afa30-161">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="afa30-161">-   eExitProcess</span></span><br /><span data-ttu-id="afa30-162">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="afa30-162">-   eFastExitProcess</span></span><br /><span data-ttu-id="afa30-163">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="afa30-163">-   eRudeExitProcess</span></span><br /><span data-ttu-id="afa30-164">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="afa30-164">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="afa30-165">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="afa30-165">OPR_ProcessExit</span></span>|<span data-ttu-id="afa30-166">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="afa30-166">-   eExitProcess</span></span><br /><span data-ttu-id="afa30-167">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="afa30-167">-   eFastExitProcess</span></span><br /><span data-ttu-id="afa30-168">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="afa30-168">-   eRudeExitProcess</span></span><br /><span data-ttu-id="afa30-169">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="afa30-169">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="afa30-170">OPR_FinalizerRun</span><span class="sxs-lookup"><span data-stu-id="afa30-170">OPR_FinalizerRun</span></span>|<span data-ttu-id="afa30-171">- eNoAction</span><span class="sxs-lookup"><span data-stu-id="afa30-171">-   eNoAction</span></span><br /><span data-ttu-id="afa30-172">- eAbortThread</span><span class="sxs-lookup"><span data-stu-id="afa30-172">-   eAbortThread</span></span><br /><span data-ttu-id="afa30-173">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="afa30-173">-   eRudeAbortThread</span></span><br /><span data-ttu-id="afa30-174">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="afa30-174">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="afa30-175">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="afa30-175">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="afa30-176">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="afa30-176">-   eExitProcess</span></span><br /><span data-ttu-id="afa30-177">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="afa30-177">-   eFastExitProcess</span></span><br /><span data-ttu-id="afa30-178">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="afa30-178">-   eRudeExitProcess</span></span><br /><span data-ttu-id="afa30-179">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="afa30-179">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="afa30-180">Requisitos</span><span class="sxs-lookup"><span data-stu-id="afa30-180">Requirements</span></span>  

 <span data-ttu-id="afa30-181">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afa30-181">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afa30-182">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="afa30-182">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="afa30-183">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="afa30-183">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="afa30-184">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afa30-184">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afa30-185">Consulte también</span><span class="sxs-lookup"><span data-stu-id="afa30-185">See also</span></span>

- [<span data-ttu-id="afa30-186">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="afa30-186">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="afa30-187">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="afa30-187">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="afa30-188">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="afa30-188">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
